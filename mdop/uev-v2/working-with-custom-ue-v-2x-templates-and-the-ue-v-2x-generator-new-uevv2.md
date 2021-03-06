---
title: Работа с пользовательскими шаблонами UE-V 2. x и генератором UE-V 2. x
description: Работа с пользовательскими шаблонами UE-V 2. x и генератором UE-V 2. x
author: dansimp
ms.assetid: f0bb4920-0132-472c-a564-abf06a884275
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8d863896e4ccfa92161f8a8f5e2b8955f139872
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819292"
---
# Работа с пользовательскими шаблонами UE-V 2. x и генератором UE-V 2. x


Чтобы синхронизировать параметры приложения между компьютерами пользователей, Microsoft User Experience Virtualization (UE-V) 2,0, 2,1 и 2,1 SP1 использует *шаблоны расположений параметров*. Некоторые шаблоны расположений параметров включены в виртуализацию взаимодействия с пользователем. Вы также можете создавать, изменять и проверять шаблоны расположений настраиваемых параметров с помощью генератора UE-V.

Генератор UE-V наблюдает за классом приложений Windows, чтобы найти и захватить расположения, в которых приложение хранит параметры. Отслеживаемое приложение должно быть классического приложения. Генератор UE-V не может создать шаблон расположения параметров для следующих типов приложений:

-   Виртуализированные приложения

-   Приложения, которые предлагаются в службах терминалов

-   Приложения Java

-   Приложения для Windows  

Эта статья

**Расположение стандартных и нестандартных параметров.** Генератор UE-V помогает определить, где приложения должны искать файлы параметров и параметры реестра, которые используются приложениями для хранения сведений о параметрах. Генератор обнаружит только те параметры, которые доступны для обычного пользователя. Параметры, которые хранятся в других папках, исключаются. Обнаруженные параметры сгруппированы в две категории: **Standard** и **non-Standard**. Для синхронизации рекомендуются стандартные параметры, и UE-V может легко захватить и применить их. Нестандартные параметры могут синхронизировать параметры, но в соответствии с правилами, которые использует UE-V, эти параметры могут быть несогласованными или не синхронизировать параметры. Эти параметры могут зависеть от временных файлов, привести к ненадежной синхронизации или может быть нецелесообразным. Эти расположения параметров представлены в генераторе UE-V. Вы можете включить или исключить их для каждого случая.

Генератор UE-V открывает приложение как часть процесса обнаружения. Генератор может собирать параметры в указанных ниже папках.

-   **Параметры реестра** — расположение в реестре в разделе **hKey \ _CURRENT \ _USER**

-   **Файлы параметров приложения** : файлы, сохраненные в разделе \ \ **Пользователи** \ \ \ [имя пользователя \] \ \ **AppData**  \\  **роуминг**

Генератор UE-V исключает расположения, которые обычно хранят файлы программного обеспечения приложения, но не синхронизированы между компьютерами или средами пользователей. Генератор UE-V исключает указанные ниже места. Исключенные расположения описаны ниже.

-   Раздел HKEY \ _CURRENT \ _USER разделы реестра и файлы, к которым пользователь, выполнивший вход, не может записать значения

-   Раздел HKEY \ _CURRENT \ _USER разделы реестра и файлы, связанные с основными функциями операционной системы Windows.

-   Все разделы реестра, которые находятся в кусте HKEY \ _LOCAL \ _MACHINE, для которого требуются права администратора, и может потребоваться установка соглашения о контроле учетных записей.

-   Файлы, расположенные в каталогах программных файлов, для которых требуются права администратора, и может потребоваться настройка соглашения UAC

-   Файлы, расположенные в разделе Пользователи \ \ \ [имя пользователя \] \ \ AppData \ \ LocalLow

-   Файлы операционной системы Windows, которые находятся в папке "% SystemRoot%", для которой требуются права администратора, и может потребоваться настройка соглашения UAC

Если разделы и файлы реестра, хранящиеся в этих расположениях, необходимы для синхронизации параметров приложения, вы можете вручную добавить Исключенные расположения в шаблон расположения параметров в процессе создания шаблона (кроме записей реестра в кусте HKEY \ _LOCAL \ _MACHINE).

## <a href="" id="edit"></a>Изменение шаблонов расположений параметров с помощью UE-V Generator


Используйте генератор UE-V для редактирования шаблонов расположений параметров. Когда измененные параметры добавляются в шаблоны с помощью генератора UE-V, сведения о версии в шаблоне автоматически обновляются, чтобы убедиться, что все существующие шаблоны, развернутые в корпоративной среде, обновлены правильно.

**Примечание**  Если вы изменяете шаблон UE-V 1,0 с помощью генератора UE-V 2, шаблон автоматически преобразуется в шаблон UE-V 2. Агенты UE-V 1,0 больше не могут использовать отредактированный шаблон.

 

**Изменение шаблона расположения параметров UE-V с помощью UE-V Generator**

1.  Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft User Experience Virtualization**и выберите **генератор Microsoft Experience Virtualization**.

2.  Щелкните **изменить шаблон расположения параметров**.

3.  В списке последних использованных шаблонов выберите шаблон, который нужно изменить. Кроме того, можно нажать кнопку **Обзор** , чтобы найти файл шаблона параметров. Чтобы продолжить, нажмите **Далее**.

4.  Проверьте **Свойства**, расположения в **реестре** и расположение **файлов** для шаблона параметров. Внесите необходимые изменения.

    -   На вкладке **Свойства** можно просматривать и изменять следующие свойства:

        -   **Имя приложения**: имя приложения, которое написано в описании свойств файла программы.

        -   **Имя программы**: имя программы, которая берется из свойств файла программы. Обычно это имя имеет расширение имени файла. exe.

        -   **Версия продукта**: номер версии файла exe приложения. Это свойство вместе с **версией файла**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположения параметров применяется ко всем версиям продукта.

        -   **Версия файла**: номер версии файла exe приложения. Это свойство вместе с **версией продукта**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположения параметров применяется ко всем версиям программы.

        -   **Имя автора шаблона** (необязательно): имя автора шаблона параметров.

        -   **Электронная почта автора шаблона** (необязательно): адрес электронной почты автора шаблона расположения параметров.

    -   На вкладке " **Реестр** " перечислены разделы **реестра и их** **область** , которые включены в шаблон расположения параметров. Вы можете изменить расположение реестра с помощью раскрывающегося меню **Tasks (задачи** ). В меню "задачи" можно добавить новые ключи, изменить имя или область существующих разделов, удалить разделы и просмотреть реестр, в котором находятся ключи. Когда вы определяете область для реестра, вы можете использовать область " **все параметры** ", чтобы включить все параметры реестра в указанном разделе. Используйте **все параметры** и **подразделы** для включения всех параметров реестра в заданные раздел, подразделы и параметры подраздела.

    -   На вкладке " **файлы** " перечислены путь к файлу и его маска для расположения файлов, которые включены в шаблон расположения параметров. Расположение файлов можно изменить с помощью раскрывающегося меню **Tasks (задачи** ). В меню " **задачи** " для расположений файлов можно добавлять новые файлы или папки, изменять область существующих файлов и папок, удалять файлы и папки, а также открывать выбранное расположение в проводнике Windows. Чтобы включить все файлы в указанную папку, оставьте маску файла пустой.

5.  Нажмите кнопку **сохранить** , чтобы сохранить изменения в шаблоне расположение параметров.

6.  Нажмите кнопку **Закрыть** , чтобы закрыть окно мастера шаблонов параметров. Выйдите из приложения генератора UE-V.

    После изменения шаблона расположения параметров для приложения необходимо протестировать этот шаблон. Разверните пересмотренный шаблон расположений параметров в лабораторной среде, прежде чем его можно будет перевести в производственную среду компании.

**Редактирование шаблона расположений параметров вручную**

1.  Создайте локальную копию файла шаблона расположения параметров. XML. Параметры UE-V Template Location содержат XML-файлы, которые определяют расположение значений параметров в магазине приложений.

    **Примечание**  Шаблон расположения параметров является уникальным из-за **идентификатора**шаблона. Если вы копируете шаблон и переименовываете XML-файл, регистрация шаблона завершается сбоем, так как UE-V считывает тег **идентификатора** шаблона в XML-файле для определения имени, а не имени файла XML-файла. UE-V также считывает номер **версии** , чтобы узнать, изменилось ли что-либо. Если номер версии более высокий, шаблон будет обновлен UE-V.

     

2.  Откройте файл шаблона расположения параметров с помощью редактора XML.

3.  Измените файл шаблона расположения параметров. Все изменения должны соответствовать файлу схемы UE-V, определенному в [SettingsLocationTempate. xsd](https://technet.microsoft.com/library/dn763947.aspx). Копия XSD-файла по умолчанию находится в \\ProgramData\\Microsoft\\UEV\\Templates.

4.  Увеличение номера **версии** для шаблона расположения параметров.

5.  Сохраните файл шаблона расположения параметров, а затем закройте редактор XML.

6.  Проверка измененного файла шаблона расположения параметров с помощью генератора UE-V.

7.  Для синхронизации параметров между клиентскими компьютерами необходимо зарегистрировать шаблон расположения измененных параметров UE-V. Чтобы зарегистрировать шаблон, откройте Windows PowerShell, а затем выполните следующий командлет: `update-uevtemplate [templatefilename]` . Затем вы можете скопировать файл в каталог хранилища параметров. Агент UE-V на компьютерах пользователей должен обновляться по расписанию в запланированной задаче.

## <a href="" id="validate"></a>Проверка шаблонов расположений параметров с помощью генератора UE-V


Вы можете создавать и изменять шаблоны расположений параметров в XML-редакторе без использования UE-V Generator. В этом случае вы можете использовать генератор UE-V для проверки соответствия нового или пересмотренного XML схеме, определенной для шаблона.

**Проверка шаблона расположения параметров UE-V с помощью UE-V Generator**

1.  Нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **виртуализация взаимодействия с пользователем**(Майкрософт) и выберите **генератор виртуализации взаимодействия с пользователем (Майкрософт**).

2.  Нажмите кнопку **проверить шаблон расположения параметров**.

3.  В списке последних использованных шаблонов выберите шаблон, который нужно изменить. Кроме того, вы можете **Перейти** к файлу шаблона параметров. Чтобы продолжить, нажмите **Далее**.

4.  Нажмите кнопку **проверить** , чтобы продолжить.

5.  Нажмите кнопку **Закрыть** , чтобы закрыть окно мастера шаблонов параметров. Выйдите из приложения генератора UE-V.

    После проверки шаблона расположения параметров для приложения необходимо протестировать этот шаблон. Разверните шаблон в лабораторной среде, прежде чем его можно будет перевести в производственную среду предприятия.

## <a href="" id="share"></a>Общий доступ к шаблонам расположения параметров с помощью коллекции шаблонов


Коллекция шаблонов Microsoft User Experience Virtualization (UE-V) 2,0 позволяет администраторам совместно использовать шаблоны расположений параметров UE-V. В коллекции вы можете добавить шаблоны расположения параметров для других пользователей, а также загрузить шаблоны, созданные другими пользователями. Коллекция шаблонов UE-V находится [на сайте Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=246589)TechNet.

Перед предоставлением общего доступа к шаблону расположению параметров в галерее шаблонов UE-V убедитесь, что он не содержит личных сведений о компании. Вы можете использовать любое средство просмотра XML для открытия и просмотра содержимого файла шаблона расположения параметров. Перед предоставлением общего доступа к шаблону пользователям за пределами вашей компании необходимо проверить следующие значения шаблона.

-   Имя автора шаблона: укажите общее неидентифицирующее имя для имени автора шаблона или исключите эти данные из шаблона.

-   Сообщение об авторе шаблона: укажите общее, не идентифицирующее сообщение об авторе шаблона или исключите эти данные из шаблона.

Перед развертыванием шаблона расположений параметров, скачанного из галереи UE-V, необходимо сначала проверить шаблон, чтобы убедиться, что параметры приложения правильно синхронизируют параметры в тестовой среде.






## Статьи по теме


[Администрирование UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

[Развертывание UE-V 2. x для настраиваемых приложений](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





