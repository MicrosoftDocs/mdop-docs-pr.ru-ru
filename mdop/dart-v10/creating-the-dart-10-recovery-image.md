---
title: Создание образа для восстановления DaRT 10
description: Создание образа для восстановления DaRT 10
author: dansimp
ms.assetid: 173556de-2f20-4ea6-9e29-fc5ccc71ebd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebb48ee140a6e3f70e05acd3f6affc6e3b71ff37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813208"
---
# Создание образа для восстановления DaRT 10


После установки набора средств диагностики и восстановления Microsoft (DaRT) 10 вы создадите изображение для восстановления DaRT 10. Образ восстановления запускает Windows RE, из которого можно запускать инструменты DaRT. Вы можете создавать файлы международной организации по стандартизации (ISO) и изображения в формате Windows Imaging (WIM). Кроме того, вы можете использовать PowerShell для создания сценариев, использующих параметры, выбранные в мастере создания изображений для восстановления DaRT. Вы можете использовать этот сценарий позже для повторной сборки образов восстановления с использованием одинаковых параметров. Образ восстановления предоставляет множество средств восстановления. Описание инструментов можно найти в статье [Обзор средств на DART 10](overview-of-the-tools-in-dart-10.md).

После загрузки компьютера на DaRT вы можете использовать различные инструменты DaRT для диагностики и восстановления компьютера. В этом разделе описывается процесс создания изображения для восстановления DaRT и вы можете выбрать инструменты и компоненты, которые нужно включить в состав изображения.

Вы можете создать изображение для восстановления DaRT одним из двух способов:

-   Использование мастера создания изображений для восстановления с помощью DaRT, который работает в среде Windows.

-   Измените пример сценария PowerShell на нужные значения. Дополнительные сведения можно найти в разделе [Использование сценария PowerShell для создания образа восстановления](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-10.md).

Вы можете записать ISO на записываемый компакт-диск или DVD-диски, сохранить его на USB-накопитель или сохранить в формате, который можно использовать для загрузки DaRT из удаленной секции или из раздела восстановления.

Создав ISO-образ, вы можете записать его на чистую дискету или DVD-диск (если на вашем компьютере есть компакт-или дисковод). Если на вашем компьютере нет диска для этой цели, вы можете использовать большинство обычных программ, которые используются для записи компакт-дисков или DVD-дисков.

## Выбор архитектуры изображения и указание пути


На странице Media в Windows 10 вы можете выбрать, нужно ли создавать изображение для восстановления с помощью 32 или 64-разрядной версии DaRT. Используйте 32-разрядную версию Windows для создания изображений для восстановления с 32-разрядной DaRT и 64-разрядная версия Windows для создания 64-разрядных изображений для восстановления с помощью DaRT. Вы можете использовать один компьютер для создания изображений восстановления для обоих типов архитектуры, но вы не можете создать одно изображение, работающее как в 32-, так и в 64-разрядных архитектурах. Вы также указываете путь к установочному носителю Windows 10. Выберите архитектуру, совпадающую с одним из создаваемого образа восстановления.

**Выбор архитектуры изображения и указание пути**

1.  На странице **Windows 10 мультимедиа** выберите один из указанных ниже вариантов.

    -   Если вы создаете образ восстановления для компьютеров с 64, выберите команду **создать изображение DART для 64 64-разрядной версии**.

    -   Если вы создаете образ для восстановления на компьютерах с 32-разрядными компьютерами, выберите команду **создать изображение DART для x86 (32-разр.)**.

2.  В поле введите путь к корневому каталогу для установочного файла **Windows 10 &lt; (64 &gt; -разрядная версия) или 32-bit** (для Windows 10). Используйте путь, соответствующий архитектуре создаваемого образа восстановления.

3.  Нажмите кнопку **Далее**.

## Выбор средств для включения в образ восстановления


На странице "Инструменты" можно выбрать многочисленные инструменты, которые нужно включить в образ восстановления. Эти средства будут доступны для конечных пользователей при загрузке изображения DaRT. Тем не менее, если при создании изображения DaRT вы подключаетесь к удаленному подключению, все эти средства будут доступны, когда сотрудник службы поддержки подключается к компьютеру конечного пользователя, независимо от того, какие инструменты вы выбрали для включения в изображение.

Чтобы ограничить доступ конечных пользователей к этим средствам, но по-прежнему сохранять полный доступ к средствам с помощью средства просмотра удаленных подключений, не выбирайте эти средства на странице инструменты. Конечные пользователи смогут использовать только удаленное подключение и смогут просматривать, но не Access, любые инструменты, исключаемые из образа восстановления.

**Выбор средств для включения в образ восстановления**

1.  На странице " **инструменты** " установите флажок рядом с каждым инструментом, который вы хотите включить в изображение.

2.  Нажмите кнопку **Далее**.

## Выберите, разрешено ли удаленное подключение через службу поддержки


На странице Remote Connection (удаленное подключение) вы можете разрешить сотрудникам службы поддержки удаленно подключать и запускать инструменты DaRT на компьютере конечного пользователя. Параметр Remote Connectivity затем отображается как доступный параметр в окне инструментов Диагностика и восстановление. После того как сотрудники службы поддержки смогут установить удаленное подключение, они могут запускать инструменты DaRT на компьютере конечного пользователя, находясь в удаленном расположении.

**Разрешение удаленной связи между сотрудниками службы поддержки**

1.  На странице " **удаленное подключение** " установите флажок **Разрешить удаленные** соединения, чтобы разрешить удаленные подключения, или снимите этот флажок, чтобы запретить удаленные подключения.

2.  Если флажок **Разрешить удаленные подключения** снят, нажмите кнопку **Далее**. В противном случае перейдите к следующему действию, чтобы продолжить настройку удаленного подключения.

3.  Выберите один из следующих вариантов:

    -   Позвольте Windows выбрать открытый номер порта.

    -   Укажите номер порта. Если выбрать этот параметр, введите номер порта в диапазоне от 1 до 65535 в поле ниже параметра. Этот номер порта будет использоваться при установке удаленного подключения. Чтобы свести к минимуму вероятность конфликта, мы рекомендуем использовать номер порта 1024 или выше.

4.  (Необязательно) в поле **приветственное сообщение удаленного подключения** создайте настраиваемое сообщение, которое конечные пользователи получат при установке удаленного подключения. Сообщение не может содержать более 2048 символов.

5.  Нажмите кнопку **Далее**.

    Дополнительные сведения об удаленном запуске средств DaRT можно найти [в разделе Восстановление удаленных компьютеров с помощью DaRT для восстановления](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-10.md).

## Добавление драйверов в образ восстановления


На вкладке "драйверы" на странице "Дополнительные параметры" можно добавить дополнительные драйверы устройств, которые могут потребоваться при восстановлении компьютера. Сюда обычно относятся устройства хранения данных или сетевые контроллеры, которые не поддерживаются в Windows 10. Драйверы устанавливаются при создании образа.

**Важно!**  Если вы выбрали драйвер для включения, имейте в виду, что в DaRT не поддерживается беспроводная связь (например, Bluetooth или 802.11 a/b/g/n).

 

**Добавление драйверов в образ восстановления**

1.  На странице " **Дополнительные параметры** " откройте вкладку " **драйверы** ".

2.  Щелкните **Добавить**.

3.  Перейдите к файлу, который нужно добавить для драйвера, и нажмите кнопку **Открыть**.

    **Примечание**  Файл драйвера предоставляется производителем устройства хранения или сетевого контроллера.

     

4.  Повторите действия 2 и 3 для каждого драйвера, который вы хотите включить.

5.  Нажмите кнопку **Далее**.

## Добавление дополнительных пакетов WinPE в образ восстановления


На вкладке WinPE на странице "Дополнительные параметры" вы можете добавить дополнительные пакеты WinPE к изображению DaRT. Эти пакеты входят в состав Windows ADK, который является обязательным компонентом установки для мастера изображений для восстановления DaRT. Все доступные для выбора инструменты необязательны. Все необходимые пакеты добавляются автоматически на основе средств, выбранных на странице инструменты.

Вы также можете указать размер рабочей области. Рабочую область — это объем дискового пространства, выделяемого для использования DaRT. Рабочая область полезна в том случае, если жесткий диск конечного пользователя недоступен. Если вы используете дополнительные инструменты и драйверы, вам может потребоваться расширить рабочую область.

**Добавление дополнительных пакетов WinPE в образ восстановления**

1.  На странице " **Дополнительные параметры** " откройте вкладку **WinPE** .

2.  Установите флажки рядом с каждым пакетом, который вы хотите включить в изображение, или щелкните флажок **имя** , чтобы выбрать все пакеты.

3.  В поле **Рабочая область** выберите объем дискового пространства, выделяемого для использования DART в случае недоступности жесткого диска конечного пользователя.

4.  Нажмите кнопку **Далее**.

## Добавление средств отладки для анализатора сбоев


Если в образ ISO включено средство анализа сбоев, необходимо также включить средства отладки для Windows. На вкладке анализатора сбоев на странице "Дополнительные параметры" введите путь к средствам отладки Windows 10, которые анализатор аварийного анализа использует при анализе файлов дампа памяти. Вы можете использовать инструменты, которые находятся на компьютере, на котором запущен мастер создания изображений для восстановления DaRT, или использовать инструменты, которые находятся на компьютере конечного пользователя. Если вы решили использовать инструменты на компьютере конечного пользователя, помните, что на каждом компьютере, который вы хотите диагностировать, должны быть установлены средства отладки.

Если вы установили пакет средств разработки программного обеспечения для Microsoft Windows (SDK) или пакет средств разработки для Microsoft Windows (WDK), средства отладки Windows 10 добавляются в образ восстановления по умолчанию, и путь к средствам отладки автоматически заполняется. Вы можете изменить путь к средствам отладки Windows 10, если файлы находятся не там, где указан путь к файлу по умолчанию. Ссылка в мастере позволяет загрузить и установить инструменты отладки для Windows, если они еще не установлены.

Для загрузки средств отладки Windows ознакомьтесь со [средствами отладки для Windows](https://go.microsoft.com/fwlink/?LinkId=266248). Установка средств отладки в расположение по умолчанию.

**Примечание**  Мастер DaRT проверяет наличие средств в разделе `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` реестра. Если значение в реестре отсутствует, мастер выполняет поиск в одном из следующих расположений в зависимости от архитектуры системы:

`%ProgramFilesX86%\Windows Kits\10.0\Debuggers\x64`

`%ProgramFilesX86%\Windows Kits\10.0\Debuggers\x86`

 

**Добавление средств отладки для анализатора сбоев**

1.  На странице " **Дополнительные параметры** " откройте вкладку **анализатора сбоев** .

2.  Необязательно Нажмите **загрузить инструменты отладки** , чтобы скачать инструменты отладки для Windows.

3.  Выберите один из следующих вариантов:

    -   **Включите &lt; &gt; средства отладки Windows 10 64-bit или 32-bit**. Если вы выберете этот параметр, найдите и выберите расположение инструментов, если путь еще не отображается.

    -   **Используйте инструменты отладки из отлаживаемой системы**. Если вы выберете этот параметр, анализатор сбоев не будет работать, если средства отладки для Windows не будут найдены на компьютере с неполадками.

4.  Нажмите кнопку **Далее**.

## Выбор типов файлов образа восстановления для создания


На странице "Создание изображения" вы выбираете папку выходных данных для образа восстановления, введите имя изображения и выберите типы файлов изображений для восстановления DaRT, которые нужно создать. В процессе создания образа восстановления исходные файлы Windows представляют собой распакованные файлы DaRT, и на нем копируется в форматы файлов, которые вы выбираете на этой странице.

Доступные типы файлов изображений:

-   **Файл образов Windows (WIM)** — используется для развертывания DART в среде предзагрузочной среды (PXE) или локальной секции).

-   **Международная организация по стандартизации (ISO)** — используется для развертывания на компакт-диск или DVD-диск или для использования на виртуальных машинах (ВМ) s). Для мастера требуется, чтобы ISO-образ имел расширение ISO, так как в большинстве программ, которые занимают компакт – диски или DVD-диски требуют этого расширения. Если вы не укажете другое расположение, на рабочем столе создается образ ISO с именем DaRT10. ISO.

-   **Сценарий PowerShell** — создает изображение для восстановления DaRT с командами, которые предоставляют те же параметры, которые можно выбрать с помощью мастера создания изображений для восстановления DART. Кроме того, сценарий позволяет добавлять или изменять файлы в образе для DaRT.

Если вы установите флажок Изменить изображение на этой странице, вы можете настроить его в процессе создания образа. Например, вы можете изменить файл "winpeshl.ini", чтобы создать настраиваемый заказ на запуск или добавить сторонние инструменты.

**Выбор типов создаваемых файлов образа для восстановления**

1.  На странице **Создание изображения** нажмите кнопку **Обзор** , чтобы выбрать папку вывода для файла изображения.

    **Примечание**  Размер изображения изменяется в зависимости от выбранных вами инструментов и файлов, которые вы добавляете в мастере.

     

2.  В поле **имя изображения** введите имя для образа восстановления DaRT или подтвердите имя по умолчанию, которое является DaRT10.

    Мастер создаст вложенную папку в пути вывода с этим именем.

3.  Выберите типы файлов изображений, которые вы хотите создать.

4.  Выберите один из указанных ниже вариантов.

    -   Чтобы изменить файлы в образе восстановления перед созданием файлов изображений, установите флажок **изменить изображение** и нажмите кнопку **подготовить**.

    -   Чтобы создать образ восстановления, не изменяя файлы, нажмите кнопку **создать**.

5.  

    Нажмите кнопку **Далее**.

## Изменение файлов образа для восстановления


Изменить изображение восстановления можно только в том случае, если на странице "Создание изображения" установлен флажок "изменить изображение". После подготовки образа восстановления для редактирования вы можете добавить и изменить файлы образа для восстановления, прежде чем создавать загрузочный носитель. Например, вы можете создать настраиваемый заказ на запуск, добавить другие сторонние инструменты и другие.

**Редактирование файлов образа восстановления**

1.  На странице **изменение изображения** нажмите кнопку **Открыть** в проводнике Windows.

2.  Создайте вложенную папку в папке, которая указана в диалоговом окне.

3.  Скопируйте файлы, которые вы хотите добавить в новую вложенную папку, или удалите ненужные файлы.

4.  Нажмите кнопку **создать** , чтобы начать создание образа восстановления.

## Создание файлов образа для восстановления


На странице Создание файлов для типов файлов, выбранных на странице Создание образа, создается изображение для восстановления DaRT.

**Создание файлов образа для восстановления**

-   На странице **Создание файлов** нажмите кнопку **Далее** , чтобы создать файлы образа для восстановления.

## Копирование образа для восстановления на компакт-диск, DVD-диск или USB-порт


На странице Создание загрузочного носителя вы можете при необходимости скопировать файл изображения на компакт-диск, DVD-или USB-накопитель (UFD). Вы также можете создать дополнительные загрузочные носители на этой странице, перезапустите мастер.

**Примечание**  Это средство не поддерживает среду удаленной загрузки (PXE) и локальное развертывание образа, поскольку для них требуются дополнительные корпоративные инструменты, такие как сервер System Center Configuration Manager и Microsoft Development Toolkit.

 

**Копирование образа восстановления на компакт-диск, DVD-диск или USB-порт**

1.  На странице **Создание загрузочного носителя** выберите ISO-файл, который вы хотите скопировать.

2.  Вставьте компакт-диск, DVD-диск или USB-устройство, а затем выберите диск.

    **Примечание**  Если диск не распознается и вы устанавливаете новый диск, вы можете нажать кнопку **Обновить** , чтобы заставить мастер обновить список доступных дисков.

     

3.  Нажмите кнопку " **создать загрузочный носитель** ".

4.  Чтобы создать еще один образ восстановления, нажмите кнопку перезапустить или нажмите кнопку **Закрыть** , если вы закончите создание всех нужных файлов.

## Статьи по теме


[Обзор средств в DaRT 10](overview-of-the-tools-in-dart-10.md)

[Развертывание DaRT 10](deploying-dart-10.md)

 

 





