---
title: Развертывание UE-V 2. x для настраиваемых приложений
description: Развертывание UE-V 2. x для настраиваемых приложений
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824402"
---
# Развертывание UE-V 2. x для настраиваемых приложений


Microsoft User Experience Virtualization (UE-V) 2,0. 2,1 и 2,1 SP1 используют XML-файлы, которые называются **шаблонами расположения параметров** для отслеживания и синхронизации параметров классического приложения и рабочего стола Windows между компьютерами пользователя. По умолчанию в состав UE-V входит несколько шаблонов расположения параметров. Но если вы хотите синхронизировать параметры для классических приложений, отличных от тех, что используются в шаблонах по умолчанию, вы можете создать собственные шаблоны расположения пользовательских параметров с помощью генератора UE-V.

После того как вы прочитали материал по планированию для [подготовки к развертыванию UE-V 2. x](prepare-a-ue-v-2x-deployment-new-uevv2.md) и решили синхронизировать параметры для настраиваемых приложений (сторонние, строчные и т. д.), вы будете развертывать компоненты UE-V, как описано в этой статье. Ниже приведены основные действия, которые необходимо выполнить, чтобы синхронизировать параметры для настраиваемых приложений.

-   [Установка генератора UEV](#uevgen)

    Использование генератора UEV для создания настраиваемых шаблонов расположения параметров XML.

-   [Настройка каталога шаблонов параметров UE-V](#deploycatalogue)

    Вы можете указать этот путь, где хранятся пользовательские шаблоны расположений параметров.

-   [Создание настраиваемых шаблонов расположений параметров](#createcustomtemplates)

    Эти пользовательские шаблоны позволяют пользователям синхронизировать параметры пользовательских приложений.

-   [Развертывание шаблонов расположений настраиваемых параметров](#deploycustomtemplates)

    После того как вы протестируете настраиваемый шаблон, чтобы убедиться, что параметры синхронизированы правильно, вы можете развернуть эти шаблоны одним из указанных ниже способов.

    -   С помощью существующей инфраструктуры развертывания, например Configuration Manager

    -   С помощью настроек групповой политики

    -   [Развертывание каталога шаблонов параметров UE-V](#deploycatalogue)

    **Примечание**  Шаблоны, развернутые с помощью ESD или групповой политики, должны быть зарегистрированы в Windows Management Instrumentation (WMI) или Windows PowerShell с UE-V.

     

## Подготовка к развертыванию UE-V 2. x для настраиваемых приложений


Прежде чем приступить к развертыванию UE-V Features, обрабатывающего пользовательские приложения, вы можете просмотреть только несколько моментов.

### Генератор UE-V

Генератор UE-V наблюдает за приложением для выяснения и захвата расположений, в которых приложение сохраняет параметры. Отслеживаемое приложение должно быть традиционным приложением. Вы используете UE-V Generator для создания шаблонов расположений параметров, но не может создать шаблон расположения параметров из этих типов приложений:

-   Виртуализированные приложения

-   Приложения, которые предлагаются в службах терминалов

-   Приложения Java

-   Приложения для Windows  

**Примечание**  Шаблоны расположений параметров UE-V нельзя создавать из виртуализированных приложений и приложений служб терминалов. Однако параметры, синхронизированные с помощью шаблонов, можно применять к этим приложениям. Для создания шаблонов, поддерживающих инфраструктуру виртуальных рабочих столов (VDI) и приложений служб терминалов, откройте версию пакета установщика Windows (MSI) для приложения с помощью генератора UE-V. Дополнительные сведения о синхронизации параметров для виртуальных приложений можно найти в разделе [использование UE-V 2. x с приложениями Application Virtualization](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md).

 

**Исключенные расположения:** В процессе обнаружения не учитываются места, в которых обычно хранятся файлы программного обеспечения приложения, которые не синхронизируют параметры между компьютерами пользователя или средой. По умолчанию эти параметры исключены.

-   Раздел HKEY \ _CURRENT \ _USER разделы реестра и файлы, к которым пользователь, выполнивший вход, не может записать значения

-   Раздел HKEY \ _CURRENT \ _USER разделы реестра и файлы, связанные с основными функциями операционной системы Windows.

-   Все разделы реестра, которые находятся в кусте HKEY \ _LOCAL \ _MACHINE

-   Файлы, расположенные в каталогах программных файлов

-   Файлы, расположенные в списке Пользователи \ \ \ [имя пользователя \] \ \ AppData \ \ LocalLow

-   Файлы операционной системы Windows, расположенные в папке% systemroot%

Если для синхронизации параметров приложения требуются разделы реестра и файлы, которые хранятся в исключенных расположениях, вы можете вручную добавить их в шаблон расположения параметров в процессе создания шаблона.
Однако только изменения куста HKEY \ _CURRENT \ _USER будут синхронизироваться (ED).

### Замена шаблонов Microsoft по умолчанию

Агент UE-V добавляет стандартную группу шаблонов расположения параметров для распространенных приложений Майкрософт и параметров Windows. Если вы настраиваете эти шаблоны или создаете шаблоны расположений параметров для синхронизации параметров для настраиваемых приложений, агент UE-V Agent можно настроить на использование каталога шаблонов параметров для хранения шаблонов. В этом случае вам потребуется включить шаблоны по умолчанию вместе с пользовательскими шаблонами в каталоге шаблонов параметров.

При [развертывании агента UE-V](https://technet.microsoft.com/library/dn458891.aspx#agent)вы можете использовать параметр командной строки, `RegisterMSTemplates` чтобы отключить регистрацию шаблонов Microsoft по умолчанию.

Если вы используете групповую политику для настройки пути к каталогу шаблонов параметров, вы можете заменить стандартные шаблоны Microsoft. Если вы настроили параметры политики для замены шаблонов Майкрософт по умолчанию, удаляются все шаблоны Microsoft, установленные по умолчанию агентом UE-V, и используются только шаблоны, которые находятся в каталоге шаблонов параметров. Параметр конфигурации агента UE-V `RegisterMSTemplates` должен иметь значение *true* , чтобы переопределить шаблон Microsoft по умолчанию.

**Примечание**  Если отключить этот параметр политики после включения, агент UE-V Agent не восстановит шаблоны Microsoft по умолчанию.

 

Если в каталоге шаблонов параметров есть настроенные шаблоны, которые используют тот же идентификатор, что и в шаблонах Microsoft по умолчанию, а агент UE-V не настроен для замены шаблонов Microsoft по умолчанию, шаблоны Microsoft будут игнорироваться.

Вы также можете заменить шаблоны по умолчанию с помощью UE-V Windows PowerShell. Чтобы заменить шаблон Microsoft по умолчанию с помощью Windows PowerShell, отмените регистрацию всех шаблонов Microsoft по умолчанию, а затем зарегистрируйте пользовательские шаблоны.

**Примечание**  Старые пакеты параметров остаются в местоположении хранения параметров, даже если вы развертываете новые шаблоны расположений параметров для приложения. Эти пакеты не прочтены агентом, но ни один из них не удаляется автоматически.

 

## <a href="" id="uevgen"></a>Установка генератора UEV 2. x


На компьютере, на котором можно создать настраиваемый шаблон расположения параметров, установите для него генератор 2,0 Microsoft Experience Virtualization (UE-V). На этом компьютере должны быть установлены приложения, для которых нужно создать шаблоны расположений с пользовательскими параметрами.

**Установка генератора UE-V**

1.  Как пользователь с правами локального администратора найдите установочный файл генератора UE-V **ToolSetup.exe** , поставляемый с программным обеспечением UE-v. Кроме того, если известна архитектура компьютера, вы можете запустить соответствующий файл установщика Windows (MSI), **ToolsSetupx64.msi** или **ToolsSetupx86.msi**.

2.  Дважды щелкните файл установки. Откроется мастер настройки генератора виртуализации взаимодействия с пользователем. Чтобы продолжить, нажмите **Далее**.

3.  Приняв условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт, а затем нажмите кнопку **Далее**.

4.  Выберите параметры обновлений Майкрософт и программы улучшения качества программного обеспечения.

5.  Выберите конечную папку, в которую нужно установить генератор UE-V, и нажмите кнопку **Далее**.

6.  Нажмите кнопку " **установить** ", чтобы начать установку.

    **Примечание**  Перед установкой приложения появится запрос на **контроль учетной записи пользователя** . Требуется разрешение на установку UE-V Generator.

     

7.  Нажмите кнопку **Готово** , чтобы закрыть окно мастера после завершения установки. Для запуска UE-V Generator необходимо перезагрузить компьютер.

    Чтобы убедиться, что установка прошла успешно, нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft User Experience Virtualization**и выберите **генератор виртуализации взаимодействия с пользователем Microsoft**.

    **Примечание**  Генератор UE-V 2 можно использовать только для создания шаблонов для агентов UE-V 2. В смешанном развертывании агентов UE-V 1,0 и UE-V 2 вы должны продолжать использовать генератор UE-V 1,0, пока не обновите все агенты UE-V.

     

## <a href="" id="deploycatalogue"></a>Развертывание каталога шаблонов параметров


Каталог шаблонов параметров виртуализации пользователей — это путь к папке на компьютерах UE-V или сетевая папка SMB, в которой хранятся все пользовательские шаблоны расположения параметров. Запланированная задача в агенте UE-V проверяет это расположение один раз в день и обновляет параметры синхронизации в соответствии с шаблонами в этой папке.

Агент UE-V регистрирует шаблоны, добавленные или обновленные в этой папке после последнего установления и отмены регистрации шаблонов. По умолчанию шаблоны регистрируются и отменяются один раз в день в 3:30 утра. Локальное время планировщиком задач и при запуске системы. Чтобы настроить частоту выполнения запланированной задачи, ознакомьтесь [со сведениями об изменении частоты запланированных задач UE-V 2. x](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).

Путь к каталогу шаблонов параметров можно настроить с помощью параметров командной строки для установки, групповой политики, WMI или Windows PowerShell. Шаблоны, которые хранятся в пути к каталогу шаблонов, автоматически регистрируются и отменяются с помощью запланированной задачи.

**Настройка каталога шаблонов параметров для UE-V 2. x**

1.  Создайте новую папку на компьютере, в которой хранится каталог шаблонов параметров UE-V.

2.  Установите следующие разрешения на уровне общего доступа (SMB) для папки каталога шаблонов параметров.

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>Учетная запись пользователя</strong></th>
    <th align="left"><strong>Рекомендуемые разрешения</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Все пользователи</p></td>
    <td align="left"><p>Нет разрешений</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Компьютеры домена</p></td>
    <td align="left"><p>Уровни разрешений "чтение"</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Администраторы</p></td>
    <td align="left"><p>Уровни разрешений на чтение и запись</p></td>
    </tr>
    </tbody>
    </table>

     

3.  Установите следующие разрешения файловой системы NTFS для папки каталога шаблонов параметров.

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Учетная запись пользователя</th>
    <th align="left">Рекомендуемые разрешения</th>
    <th align="left">Применить к</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Создатель/владелец</p></td>
    <td align="left"><p>Полный доступ</p></td>
    <td align="left"><p>Эта папка, вложенные папки и файлы</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Компьютеры домена</p></td>
    <td align="left"><p>Просмотр содержимого папки и чтение</p></td>
    <td align="left"><p>Эта папка, вложенные папки и файлы</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Все пользователи</p></td>
    <td align="left"><p>Нет разрешений</p></td>
    <td align="left"><p>Нет разрешений</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Администраторы</p></td>
    <td align="left"><p>Полный доступ</p></td>
    <td align="left"><p>Эта папка, вложенные папки и файлы</p></td>
    </tr>
    </tbody>
    </table>

     

4.  Нажмите кнопку **ОК** , чтобы закрыть диалоговые окна.

Как минимум, в сетевом общем доступе должны быть предоставлены разрешения для группы Domain Computers. Кроме того, предоставьте разрешения на доступ к папке "сетевая папка" для администраторов, которые могут управлять сохраненными шаблонами.

## <a href="" id="createcustomtemplates"></a>Создание настраиваемых шаблонов расположений параметров


Использование генератора UE-V для создания шаблонов расположений параметров для бизнес-приложений или других настраиваемых приложений. После создания шаблона для приложения его можно развернуть на компьютерах, чтобы синхронизировать параметры для этого приложения.

**Создание шаблона расположения параметров UE-V с помощью UE-V Generator**

1.  Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft User Experience Virtualization**и выберите **генератор Microsoft Experience Virtualization**.

2.  Нажмите кнопку **создать шаблон расположения параметров**.

3.  Укажите приложение. Перейдите к файлу приложения (exe) или ярлыку приложения (. lnk), для которого вы хотите создать шаблон расположения параметров. Укажите аргументы командной строки, если таковые имеются, и рабочий каталог, если таковые имеются. Чтобы продолжить, нажмите **Далее**.

    **Примечание**  Перед запуском приложения система отображает запрос на **контроль учетной записи пользователя**. Для мониторинга параметров реестра и файлов, используемых приложением, требуется разрешение на их хранение.

     

4.  После запуска приложения закройте приложение. Генератор UE-V записывает места, в которых приложение хранит параметры.

5.  После завершения процесса нажмите кнопку **Далее** , чтобы продолжить.

6.  Просмотрите и установите флажки рядом с соответствующими параметрами реестра и расположениями файлов параметров для синхронизации с этим приложением. Список содержит две следующие категории для расположения параметров.

    -   **Стандартные**: параметры приложения, хранящиеся в реестре в разделах hKey \ _CURRENT \ _USER или в папках с файлами в разделе \ \ **Пользователи** \ \ \ [имя пользователя \] \ \ **AppData**  \\  **роуминг**. Генератор UE-V включает эти параметры по умолчанию.

    -   **Нестандартные**: параметры приложения, которые хранятся за пределами расположений, указаны в разделе Советы и рекомендации по хранению данных параметров (необязательно). Сюда входят файлы и папки в разделе **Пользователи** \ \ \ [имя пользователя \] \ \ **AppData**  \\  **Local**. Проверьте эти расположения, чтобы определить, нужно ли включать их в шаблон расположений параметров. Установите флажки расположения, чтобы включить их.

    Чтобы продолжить, нажмите **Далее**.

7.  Просмотр и изменение **свойств**, расположений в **реестре** и расположений **файлов** для шаблона расположения параметров.

    -   Измените следующие свойства на вкладке **Свойства** :

        -   **Имя приложения**: имя приложения, которое написано в описании свойств файлов программы.

        -   **Имя программы**: имя программы, которая берется из свойств файла программы. Обычно это имя имеет расширение имени файла. exe.

        -   **Версия продукта**: номер версии файла exe приложения. Это свойство в сочетании с **версией файла**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположения параметров применяется ко всем версиям продукта.

        -   **Версия файла**: номер версии файла exe приложения. Это свойство в сочетании с **версией продукта**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположения параметров применяется ко всем версиям программы.

        -   **Имя автора шаблона** (необязательно): имя автора шаблона расположения параметров.

        -   **Электронная почта автора шаблона** (необязательно): адрес электронной почты автора шаблона расположения параметров.

    -   На вкладке " **Реестр** " перечислены разделы **реестра и их** **область** , которые включены в шаблон расположения параметров. Измените расположение реестра с помощью раскрывающегося меню **Tasks (задачи** ). С помощью задач вы можете добавлять новые ключи, изменять имена или области существующих клавиш, удалять разделы и просматривать реестр, в котором находятся ключи. Используйте область " **все параметры** ", чтобы включить все параметры реестра в указанном разделе. Используйте **все параметры и подразделы** для включения всех параметров реестра в заданные раздел, подразделы и параметры подраздела.

    -   На вкладке " **файлы** " перечислены путь к файлу и его маска для расположения файлов, которые включены в шаблон расположения параметров. Измените расположение файлов с помощью раскрывающегося меню **Tasks (задачи** ). Задачи для расположений файлов позволяют добавлять новые файлы или папки, изменять область существующих файлов и папок, удалять файлы и папки, а также открывать выбранное расположение в проводнике. Чтобы включить все файлы в указанную папку, оставьте пустую маску файла.

8.  Нажмите кнопку **создать**и выберите команду **сохранить** , чтобы сохранить шаблон расположения параметров на компьютере.

9.  Нажмите кнопку **Закрыть** , чтобы закрыть окно мастера шаблонов параметров. Выйдите из приложения генератора UE-V.

    После создания шаблона расположения параметров для приложения необходимо протестировать этот шаблон. Разверните шаблон в лабораторной среде перед тем, как перевести его в производственную среду на предприятии.

[Справочник по схемам шаблонов приложений для UE-v —](https://technet.microsoft.com/library/dn763947.aspx) структура XML для шаблона расположения параметров ue-v и руководство по редактированию этих файлов.

## <a href="" id="deploycustomtemplates"></a>Развертывание шаблонов расположений настраиваемых параметров


После создания шаблона расположения параметров с помощью генератора UE-V необходимо проверить его, чтобы убедиться, что параметры приложения синхронизированы правильно. Затем вы можете безопасно развернуть шаблон расположения параметров на компьютерах в предприятии.

Шаблоны расположений параметров можно развернуть с помощью одного из следующих способов:

-   Система распространения корпоративного программного обеспечения (ESD), например System Center Configuration Manager

-   Предпочтения групповой политики

-   Каталог шаблонов параметров UE-V

Шаблоны, развернутые с использованием системы ESD или объектов групповой политики, должны быть зарегистрированы с помощью Windows Management Instrumentation (WMI) или PowerShell для UE-V. Шаблоны, которые хранятся в расположении каталога шаблонов параметров, автоматически регистрируются агентом UE-V.

**Использование пути к каталогу шаблонов параметров для развертывания шаблонов расположений параметров UE-V**

1.  Перейдите к папке "сетевая папка", которая определена как каталог шаблонов параметров.

2.  Добавьте, удалите или обновите шаблоны расположений параметров в каталоге шаблонов параметров в соответствии с конфигурацией шаблона агента UE-V, которую вы хотите использовать для компьютеров UE-V.

    **Примечание**  Шаблоны на компьютерах обновляются ежедневно. Обновление основано на изменениях в каталоге шаблонов параметров.

     

3.  Чтобы вручную обновить шаблоны на компьютере, на котором запущен агент UE-V, откройте командную команду с повышенными привилегиями и перейдите в **% Program Files%\\Microsoft User Experience Virtualization \ \ &lt; x86 или x64 &gt; **и запустите **ApplySettingsTemplateCatalog.exe**.

    **Примечание**  Эта программа запускается автоматически во время запуска компьютера и ежедневно в 3:30 A. M. для сбора новых шаблонов, которые были недавно добавлены в каталог.

     






## Статьи по теме


[Подготовка к развертыванию UE-V 2. x](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Развертывание необходимых компонентов для UE-v 2.x](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





