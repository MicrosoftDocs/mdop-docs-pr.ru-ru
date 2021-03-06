---
title: Описание команд SFTTRAY
description: Описание команд SFTTRAY
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815352"
---
# Описание команд SFTTRAY


Приложение клиентской панели Microsoft Application Virtualization (App-V), sfttray.exe, — это основной элемент пользовательского интерфейса клиента App-V, с которым пользователи будут взаимодействовать при обычном использовании. Эта программа контролирует потоковую передачу и запуск всех виртуальных приложений и доступ к ним можно получить, щелкнув правой кнопкой мыши значок, который отображается в области уведомлений, чтобы отобразить меню клиентских функций. Это меню позволяет загрузить приложения, начать обновление публикации, отменить запрос или перевести клиент в автономный режим. Пользователь также может закрыть приложение клиентской панели приложения Application Virtualization и все активные приложения, нажав кнопку **выход**.

По умолчанию значок отображается каждый раз, когда запускается виртуальное приложение, несмотря на то что вы можете управлять этим поведением с помощью команд SFTTRAY. Приложение клиентской панели Application Virtualization также отображает индикатор выполнения для каждого запускаемого приложения, а также сообщения о состоянии активных приложений. При нажатии на индикатор выполнения отображается сообщение, позволяющее отменить загрузку или запуск приложения.

## Команды SFTTRAY


Список команд и переключателей командной строки можно отобразить, выполнив следующую команду в командном окне.

**Примечание.**  
Для каждого контекста пользователя существует только один экземпляр Application Virtualization, поэтому при запуске новой команды SFTTRAY она будет передана в уже запущенную программу.



`Sfttray.exe /?`

### Использование команд

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### Переключатели командной строки

Параметры командной строки SFTTRAY описаны в приведенной ниже таблице.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Переключатель</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/HIDE</p></td>
<td align="left"><p>Скрывает значок SFTTRAY в области уведомлений Windows.</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOW</p></td>
<td align="left"><p>Отображение значка SFTTRAY в области уведомлений Windows.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Параметрами</p></td>
<td align="left"><p>Поддерживает автоматическое использование, предотвращая ошибки при отображении полей сообщений, требующих подтверждения пользователей.</p></td>
</tr>
<tr class="even">
<td align="left"><p>/EXE &lt; альтернативный exe-файл&gt;</p></td>
<td align="left"><p>Используется с/LAUNCH, чтобы указать, что исполняемая программа должна запускаться в виртуальной среде при запуске виртуального приложения вместо целевого файла, указанного в OSD.</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Например, с помощью команды "SFTTRAY.EXE/EXE REGEDIT.EXE &lt; приложение/Launch &gt; " можно просмотреть реестр виртуальной среды, в которой работает приложение.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;Приложение/Launch &gt; [ &lt; args &gt; ]</p></td>
<td align="left"><p>Запускает виртуальное приложение. Укажите имя и версию приложения или путь к OSD – файлу. Кроме того, аргументы командной строки можно передать в виртуальное приложение.</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Используйте команду "SFTMIME.EXE/QUERY OBJ: APP/SHORT", чтобы получить список имен и версий доступных виртуальных приложений.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>/LOAD</p></td>
<td align="left"><p>Загружает или импортирует виртуальное приложение.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOADALL</p></td>
<td align="left"><p>Загружает все приложения в кэш.</p></td>
</tr>
<tr class="even">
<td align="left"><p>/REFRESHALL</p></td>
<td align="left"><p>Запускает обновление публикации для всех приложений.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;уникальный идентификатор/LAUNCHRESULT&gt;</p></td>
<td align="left"><p>Возвращает код результата запуска для процесса, который запускается sfttray.exe с помощью глобального события и файла, отображенного в памяти, на основе указанного корневого имени для УНИКАЛЬного идентификатора. ¹</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SFTFILE &lt; SFT&gt;</p></td>
<td align="left"><p>Необязательный параметр, используемый с/LOAD, для указания пути к SFT-файлу приложения. Если задано, приложение импортируется, а не загружается.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/EXIT</p></td>
<td align="left"><p>Закрытие программы SFTTRAY и всех активных виртуальных приложений и удаление значка из области уведомлений Windows.</p></td>
</tr>
</tbody>
</table>



**Примечание.**  
¹ параметр командной строки */LAUNCHRESULT* предоставляет возможность для процесса, запускающего sfttray.exe, для указания корневого имени глобального события и отображенного в памяти файла, который используется для возврата кода результата запуска в процесс. Имя уникального идентификатора должно начинаться с "SFT-", чтобы не допустить, чтобы имя события изнутри, когда запускается процесс запуска в виртуальной среде. Область сопоставленных в памяти размеров будет 64 бит.

Чтобы использовать этот параметр, процесс запуска создает событие с именем " &lt; уникальный идентификатор &gt; -результат \ _Event", сопоставленный файл в памяти с именем "уникальный идентификатор — &lt; &gt; результат \ _Value", а также событие с именем " &lt; уникальный идентификатор &gt; — Завершение \" _Event ", а затем запускается процесс запуска sfttray.exe и ждет, пока событие не будет сигнальным. После того как событие " &lt; уникальный идентификатор &gt; — результат \ _Event" будет сигнальным, процесс запуска извлекает код возврата 64-bit из сопоставленной области памяти.

Если необязательное событие " &lt; уникальный идентификатор &gt; — Завершение" — "не_event", когда виртуальное приложение завершает работу, sfttray.exe открывает и сигнализирует о событии. Процесс запуска ожидает на этом событии завершения работы, если ему нужно определить, когда завершается виртуальное приложение.











