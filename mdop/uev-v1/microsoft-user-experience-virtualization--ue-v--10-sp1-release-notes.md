---
title: Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 1.0 с пакетом обновления 1 (SP1)
description: Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 1.0 с пакетом обновления 1 (SP1)
author: dansimp
ms.assetid: 447fae0c-fe87-4d1c-b616-6f92fbdaf6d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8584999d9fdbdfccc3e9b2b1486cb97635475747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812485"
---
# Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 1.0 с пакетом обновления 1 (SP1)


Чтобы выполнить поиск заметок о выпуске пакета обновления 1 (SP1) для Microsoft User Experience Virtualization (UE-V) 1,0, нажмите клавиши CTRL + F.

Перед установкой UE-V вы должны внимательно прочитать эти заметки о выпуске. Заметки о выпуске содержат сведения, необходимые для успешной установки виртуализации взаимодействия с пользователем, и содержат дополнительные сведения, недоступные в документации по продукту. Если между этими заметками о выпуске и другой документацией UE-V есть различия, Последнее изменение должно считаться полномочным. Эти заметки о выпуске заменяют содержимое, которое входит в состав этого продукта.

## Известные проблемы UE-V


В этом разделе содержатся заметки о выпуске для функции User Experience Virtualization 1,0 SP1.

### Не удается синхронизировать параметры реестра между приложением App-V и собственными приложениями на одном компьютере

Если на компьютере установлено приложение, доступное как в приложении Application Virtualization (App-V), так и в исходном приложении, установленном с помощью установщика Windows (MSI-файла), параметры, основанные на реестре, не синхронизируются между этими технологиями.

ВРЕМЕННОе решение: чтобы устранить эту проблему, запустите приложение, выбрав одну из двух технологий, но не то, и другое.

### <a href="" id="windows-8-setting-synchronization-fails-when-network-share-is-outside-user-s-domain"></a>Синхронизация параметров Windows 8 завершается сбоем, если сетевая доля выходит за пределы домена пользователя

Если Windows® 8 пытается синхронизировать параметры операционной системы, synchrnization завершает работу со следующим сообщением об ошибке: **"Boost:: FileSystem:: EXISTS": неверное имя пользователя или пароль**. Эта ошибка может указывать на то, что сетевой общий доступ выходит за пределы домена пользователя. Чтобы проверить работоспособность журнала событий, откройте **средство просмотра событий** и перейдите в раздел " **приложения и службы**", которые регистрируются в журнале  /  **Microsoft**  /  **виртуализации Microsoft User Experience**  /  **Logging**  /  **Operational**. Общие сетевые ресурсы, используемые для расположений хранилищ параметров UE-V, должны располагаться в том же домене Active Directory, что и пользователь.

ВРЕМЕННОе решение: используйте общие сетевые ресурсы из того же домена Active Directory, что и пользователь. .

### Перемещение подписей электронной почты в Outlook 2010

UE-V перемещает файлы подписей Outlook 2010 между устройствами. Однако параметры подписи по умолчанию для новых сообщений, ответов и пересылаемых писем не перемещаются. Эти два параметра хранятся в профиле Outlook, который UE-V не перемещается.

ВРЕМЕННОе решение: нет.

### Параметры синхронизации не синхронизируются с ожидаемым интервалом при работе в режиме медленного канала

В нормальных условиях места хранения параметров должны быть доступны через сетевое подключение Fast Link. В режиме медленной связи синхронизация будет выполняться периодически на периодической основе. По умолчанию расписание синхронизации режима медленного соединения задается каждые 360 минут.

ВРЕМЕННОе решение: чтобы изменить частоту фоновой синхронизации на компьютерах в режиме медленной связи, вы можете настроить групповую политику для политики фоновой синхронизации для **автономных файлов**.

### Специальные символы не синхронизируются

Некоторые символы, такие как символы денежных единиц, не синхронизируются между компьютерами с Windows 7 и Windows 8, на которых запущен агент UE-V Agent.

ВРЕМЕННОе решение: нет.

### UE-V не поддерживает перемещаемые параметры между 32-битным и 64-разрядными версиями Microsoft Office

Мы рекомендуем установить 32-разрядную версию Microsoft Office для 32-и 64-разрядных операционных систем. Для выбора нужной версии Microsoft Office щелкните здесь ( [http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623) ). UE-V поддерживает перемещаемые параметры между идентичными версиями Office. Например, 32-разрядные параметры Office будут перемещаться между всеми 32-разрядными экземплярами Office. UE-V не поддерживает перемещаемые параметры между 32-битным и 64-разрядными версиями Office.

ВРЕМЕННОе решение: нет

### <a href="" id="msi-s-are-not-localized"></a>MSI не локализованы

UE-V 1,0 SP1 включает локализованную программу установки для агента UE-V и генератора UE-V. Эти файлы MSI по-прежнему доступны, но пользовательский интерфейс минимизирован и отображается только на английском языке. Несмотря на то, что файл находится на английском языке, во время установки программа установки устанавливает все поддерживаемые языки.

ВРЕМЕННОе решение: нет

### Другие папки в общем доступе с расположением хранилища параметров недоступны в режиме медленного подключения

Общие ресурсы хранилища параметров не должны располагаться в сетевой папке, которая используется для других папок, которые должны быть всегда доступны. Когда сетевая папка, в которой размещено место хранения параметров, переходит в режим медленного подключения, единственным доступным является папка "Параметры хранилища". Другие папки в общем доступе недоступны в режиме медленного подключения.

Временное решение: нет

### Favicons, связанные с браузером Internet Explorer 9, не перемещаются

Favicons, связанные с браузером Internet Explorer 9, не перемещаются с помощью виртуализации взаимодействия с пользователем и не отображаются при первом появлении этого списка на новом компьютере.

ВРЕМЕННОе решение: при использовании закладки и кэшировании в браузере Internet Explorer 9 появится Favicons с соответствующими избранными.

### Пути к параметрам файла хранятся в реестре

Некоторые параметры приложения хранят пути файлов конфигурации и параметров в виде значений в реестре. Файлы, на которые указывают ссылки в реестре, должны быть синхронизированы при перемещении параметров между компьютерами.

ВРЕМЕННОе решение: используйте перенаправление папок или другие технологии, чтобы убедиться в том, что файлы, на которые указывают ссылки, находятся в том же расположении на всех компьютерах, где параметры перемещаются.

### Путь к хранилищу с длинными параметрами может вызвать ошибку

Храните пути к хранилищу параметров как можно короче. Длинные пути могут не допускать разрешения и синхронизацию. UE-V использует путь к хранилищу параметров как часть расчетного пути для хранения параметров. Этот путь вычисляется следующим образом: параметры путь к хранилищу и "settingspackages" + Dir (ИД шаблона) + имя пакета (ИД шаблона). Если размер вычисляемого пути превышает 260 символов, в журнале событий UE-V память пакета завершается сбоем и генерируется следующее сообщение об ошибке:

`[boost::filesystem::copy_file: The system cannot find the path specified]`

Для проверки событий журнала в журнале откройте средство просмотра событий и перейдите в раздел Журналы приложений и служб/Microsoft/пользовательский интерфейс, виртуализация и ведение журнала.

ВРЕМЕННОе решение: нет.

### Задержка агента UE-V при выходе или входе

Если при входе в систему или выходе из нее происходит подключение к сети, то, возможно, вы задерживаете, выход из системы или вход в сеть. Функция автономных файлов может занять до трех минут, чтобы определить текущее состояние сети. Если вход или завершение работы не выполняется до тех пор, пока автономные файлы не определили, что компьютер подключен к медленной ссылке, пакет параметров UE-V будет отправлен на сервер, а не в локальный кэш.

ВРЕМЕННОе решение: нет.

### Конфликт параметров при попытке перемещения параметров операционной системы в Windows 8

Если в Windows 8 включена синхронизация учетных записей Майкрософт вместе с UE-V для параметров операционной системы, примененные параметры могут быть несогласованными.

ВРЕМЕННОе решение выполните одно из указанных ниже действий.

-   Отключение синхронизации учетной записи Майкрософт, если вы используете UE-V для перемещения параметров операционной системы

-   Отключение UE-V для параметров операционной системы

### Некоторые параметры операционной системы перемещаются только в том случае, если они есть в версиях операционной системы

Параметры операционной системы для экранного диктора и символов денежных единиц, относящихся к национальной настройке, будут перемещаться только в версиях операционной системы Windows. Например, для обозначения денежных единиц вы можете перемещаться только с Windows 7 на Windows 7.

ВРЕМЕННОе решение: нет

 

 




