---
title: Восстановление локальных компьютеров с помощью образа для восстановления DaRT
description: Восстановление локальных компьютеров с помощью образа для восстановления DaRT
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823762"
---
# Восстановление локальных компьютеров с помощью образа для восстановления DaRT


Чтобы восстановить локальный компьютер с помощью набора средств диагностики и восстановления Microsoft (DaRT) 7, вы должны быть физически представлены на компьютере конечного пользователя, на котором возникают проблемы, требующие DaRT. Вы также можете выполнить DaRT удаленно, следуя инструкциям, [чтобы восстановить удаленные компьютеры с помощью DaRT](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).

**Восстановление локального компьютера с помощью DaRT**

1.  При загрузке на изображение для восстановления DaRT на экране появится диалоговое окно " **NetStart** ". Вам будет предложено указать, нужно ли инициализировать сетевые службы. Если нажать кнопку **Да**, предполагается, что в сети есть DHCP-сервер и сделана попытка получить IP-адрес с сервера. Если в сети вместо DHCP используются статические IP-адреса, вы можете позже воспользоваться средством **настройки TCP/IP** в DART, чтобы указать статический IP-адрес.

    Чтобы пропустить процесс инициализации сети, нажмите кнопку **нет**.

2.  В диалоговом окне "инициализация сети" появится вопрос о том, нужно ли переназначить буквы дисков. При запуске Windows Online системный том обычно отображается на диске C. Однако при запуске Windows в автономном режиме в среде WinRE исходный системный том может быть сопоставлен с другим диском, и это может привести к путанице. Если вы решили выполнить повторное сопоставление, DaRT попытается сопоставить буквы для автономного диска с буквами, заданными в сети. Повторное сопоставление выполняется только в том случае, если в процессе запуска выбрана автономная операционная система.

3.  В диалоговом окне Изменение сопоставления в диалоговом окне **Параметры восстановления системы** появляется запрос на выбор раскладки клавиатуры. Затем отображается корневой каталог системы, вариант установленной операционной системы и размер раздела. Если вы не видите указанную в списке операционную систему и подозреваете, что причиной сбоя является нехватка драйверов, нажмите **загрузить драйверы** , чтобы загрузить подозрительные драйверы. В этом случае вам будет предложено вставить установочный носитель для устройства и выбрать драйвер. Выберите установку, которую вы хотите восстановить или диагностировать, и нажмите кнопку **Далее**.

    **Примечание.**  
    Если среда восстановления Windows (WinRE) обнаруживает или подозреваете, что Windows 7 не запускается надлежащим образом в последний раз, программа **восстановления запуска** может начать выполняться автоматически.



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. В окне " **Параметры восстановления системы** " выберите **набор средств диагностики и восстановления Microsoft**.

   Откроется окно **инструментов Диагностика и восстановление** . Теперь вы можете запускать любые инструменты или мастера, которые были включены при создании изображения для восстановления DaRT.

Вы можете нажать кнопку **Справка** в окне " **набор инструментов диагностики и восстановления** ", чтобы открыть файл справки, который содержит подробные инструкции и сведения, необходимые для запуска отдельных инструментов DaRT. Вы также можете нажать кнопку **Мастер решений** в окне **инструментов Диагностика и восстановление** , чтобы выбрать оптимальное средство для ситуации на основе короткого собеседования, предоставленного мастером.

Общие сведения о любом из инструментов DaRT можно найти в статье [Обзор инструментов dart 7,0](overview-of-the-tools-in-dart-70-new-ia.md).

**Запуск DaRT в командной строке**

1. Вы можете запустить DaRT из командной строки, указав команду **netstart.exe** и используя любые из указанных ниже параметров.

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">Параметр</th>
   <th align="left">Описание</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>-Network (сеть)</p></td>
   <td align="left"><p>Инициализирует сетевые службы.</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>-Повторное подключение</p></td>
   <td align="left"><p>Повторное сопоставление букв дисков.</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>-Prompt</p></td>
   <td align="left"><p>Отображение сообщений с просьбой подтвердить, инициализировать ли сеть и переназначить диски.</p>
   <div class="alert">
   <strong>Важно.</strong><br/><p>Ответ конечного пользователя на запросы переопределяет параметры-сетевой и-повторное подключение.</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. Вы можете настроить DaRT так, чтобы на компьютере с функцией DaRT автоматически открывалось средство **удаленного подключения** , которое используется для подключения к службе поддержки.

## Статьи по теме


[Восстановление компьютеров с помощью DaRT 7.0](recovering-computers-using-dart-70-dart-7.md)









