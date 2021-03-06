---
title: Планирование миграции с предыдущих версий
description: Планирование миграции с предыдущих версий
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815929"
---
# Планирование миграции с предыдущих версий


Перед переходом на Microsoft Application Virtualization 4.5 или более поздней версии все версии 4.1 должны быть обновлены до версии 4.1. Прежде чем обновлять серверные компоненты, необходимо предварительно запланировать обновление ваших клиентов. Клиенты, которые были обновлены до версии 4.5, продолжат работу с серверами Application Virtualization, которые еще не были обновлены. Более ранние версии клиента не поддерживаются на серверах, которые были обновлены до версии 4.5. Дополнительные сведения об обновлении компонентов системы можно найти в разделе [рекомендации по развертыванию и обновлению Application Virtualization](application-virtualization-deployment-and-upgrade-considerations.md).

Для обеспечения успешной миграции компоненты системы Application Virtualization следует обновлять в указанном ниже порядке.

1.  **Клиенты Microsoft Application Virtualization.** Пошаговые инструкции по обновлению можно найти в статье [обновление клиента Application Virtualization](how-to-upgrade-the-application-virtualization-client.md).

2.  **Серверы и база данных Microsoft Application Virtualization.** Пошаговые инструкции по обновлению можно найти в статье [как обновить серверы и компоненты системы](how-to-upgrade-the-servers-and-system-components.md).

    **Примечание**  Если к базе данных Application Virtualization подключено больше одного сервера, то во время обновления базы данных все эти серверы должны быть переведены в автономный режим. Вы должны следовать обычным бизнес-рекомендациям по обновлению базы данных, но настоятельно рекомендуется протестировать обновление базы данных с помощью резервной копии базы данных на тестовом сервере. Затем необходимо выбрать один из серверов для первого обновления, который обновит схему базы данных. После успешного обновления рабочей базы данных вы можете обновить другие серверы.

     

3.  **Веб-служба управления виртуализацией приложений Microsoft.** Это действие применимо только в том случае, если веб-служба управления находится на отдельном сервере, для обновления веб-службы которой требуется запустить программу установщика сервера на отдельном сервере. В противном случае Предыдущая операция обновления сервера будет автоматически обновлять веб-службу управления.

4.  **Консоль управления виртуализацией приложений Microsoft.** Это действие применимо только в том случае, если консоль управления находится на отдельном компьютере, для обновления консоли которого требуется запустить программу установщика сервера на отдельном компьютере. В противном случае предыдущий шаг обновления сервера обновит консоль управления.

5.  **Microsoft Application Virtualization Sequencer.** Пошаговые инструкции можно найти [в статье Установка Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md). Любые пакеты виртуальных приложений, упорядоченные в версии 4.2, не нужно будет повторно обрабатывать для использования с версией 4.5. Однако рекомендуется обновить виртуальные пакеты до формата Microsoft Application Virtualization 4.5, если вы хотите применить стандартные списки управления доступом (ACL) или создать файл установщика Windows. Это простой процесс, и необходимо, чтобы только существующий виртуальный пакет приложения был открыт и сохранен с помощью средства Sequencer 4.5. Это можно автоматизировать с помощью интерфейса командной строки Application Virtualization Sequencer.

## <a href="" id="app-v-4-6-client-package-support-"></a>Поддержка клиентского пакета App-V 4.6


Вы можете развертывать пакеты, созданные в предыдущих версиях App-V для клиентов App-V 4.6. Тем не менее, необходимо изменить связанный **OSD** файл, чтобы он включал соответствующую информацию об операционной системе и архитектуре микросхем. Используйте указанные ниже значения.

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Значение ОС</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win2003TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win2003TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win2008TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win2008TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win2008R2TS64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win7"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "Win764"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "WinVista"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "WinVista64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "WinXP"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;ЗНАЧЕНИЕ ОС = "WinXP64"/&gt;</p></td>
</tr>
</tbody>
</table>

 

Чтобы запустить созданный 32-разрядный пакет, необходимо последовательное пошаговое выполнение приложения на компьютере с 32-разрядной операционной системой с установленным секвенсором App-V 4.6. После упорядочения приложения в консоли секвенсор выберите вкладку **развертывание** и укажите нужную архитектуру операционной системы и микросхемы.

**Важно!**  Приложения, упорядоченные на компьютере под управлением 64-разрядной операционной системы, должны развертываться на компьютерах с 64-разрядной операционной системой. Новые 32-разрядные пакеты, созданные с помощью программы Sequencer App-V 4.6, не будут работать на компьютерах, на которых запущен клиент App-V 4,5.

 

Для выполнения новых 64-разрядных пакетов в клиенте App-V 4.6 необходимо последовательное приложение на компьютере с Windows App-V 4.6 и работающем с 64-разрядной операционной системой. После упорядочения приложения в консоли секвенсор выберите вкладку **развертывание** и укажите нужную архитектуру операционной системы и микросхемы.

В следующей таблице перечислены клиентские версии, которые будут запускать пакеты, созданные с использованием различных версий секвенсора.

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Упорядочение с помощью секвенсора App-V 4,2</th>
<th align="left">Упорядочение с помощью секвенсора App-V 4,5</th>
<th align="left">Последовательное использование 32-разрядного приложения Sequencer-V 4,6</th>
<th align="left">Последовательное использование 64-разрядного приложения Sequencer-V 4,6</th>
<th align="left">Последовательное использование 32-разрядного приложения Sequencer-V 4,6 SP1</th>
<th align="left">Последовательное использование 64-разрядного приложения Sequencer-V 4,6 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>клиент 4,2</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
</tr>
<tr class="even">
<td align="left"><p>клиент 4,5 ¹</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Нет</p></td>
</tr>
<tr class="odd">
<td align="left"><p>клиент 4,6 (32-разр.)</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
</tr>
<tr class="even">
<td align="left"><p>клиент 4,6 (64-разр.)</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Клиент 4,6 SP1</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Нет</p></td>
</tr>
<tr class="even">
<td align="left"><p>Клиент 4,6 SP1 (64-разрядная версия)</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
</tr>
</tbody>
</table>

 

¹ применяется ко всем версиям клиента App-V 4.5, включая App-V 4.5, App-v 4.5 CU1 и App-V 4.5 SP1.

## Дополнительные вопросы миграции


Одной из функций приложения App-V 4.5 является возможность создания файлов установщика Windows (MSI) в качестве контрольных точек для обеспечения взаимодействия виртуальных пакетов приложений с помощью встроенных в электронную систему программного обеспечения (например, Microsoft Endpoint Configuration Manager). Предыдущие файлы установщика Windows, созданные с помощью средства. msi для виртуализации приложений, которые были установлены в клиенте App-V 4.1 или 4.2, которые впоследствии обновлены до версии 4.5, продолжают работать, но не могут быть установлены на клиенте 4.5. Однако они не могут быть удалены или обновлены до тех пор, пока они не будут обновлены в секвенсоре 4.5. Первоначальный виртуальный пакет приложения до 4,5 должен быть открыт в секвенсоре 4.5 и сохранен как файл установщика Windows.

**Примечание**  Если клиент App-V 4.2 уже обновлен до версии 4.5, вы можете использовать сценарии для решения проблем с сохранением пакетов 4.2 на 4,5 клиентах и предоставления им возможности управления. Этот сценарий должен скопировать два файла, msvcp71.dll и msvcr71.dll в папку установки App-V и установить следующие значения в разделе реестра \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:

"ClientVersion" = "4.2.1.20"

"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (доступное для записи глобальное расположение)

 

Файлы установщика Windows, созданные с помощью секвенсора App-V 4,5, выводят сообщение об ошибке "Этот пакет требует клиента Microsoft Application Virtualization 4,5 или более поздней версии" при попытке запустить их в клиенте App-V 4,6. Откройте старый пакет с помощью секвенсора App-V 4,5 с пакетом обновления 1 (SP1) или секвенсор App-V 4,6, а затем создайте новый MSI-пакет.

Созданные и сохраненные отчеты 4.2 будут перезаписаны, когда сервер будет обновлен до версии 4.5. Если вы хотите сохранить эти отчеты, необходимо сохранить резервную копию файла SftMMC. msc, расположенную в папке консоли управления SoftGrid на сервере, и использовать эту копию для замены нового SftMMC. msc, установленного во время обновления.

Дополнительные сведения об обновлении предыдущей версии [можно найти в статье обновление до Microsoft Application Virtualization 4,5 (вопросы и ответы](https://go.microsoft.com/fwlink/?LinkId=120358) ) https://go.microsoft.com/fwlink/?LinkId=120358) .

## Статьи по теме


[Планирование развертывания системы виртуализации приложений](planning-for-application-virtualization-system-deployment.md)

 

 





