---
title: Сценарии использования серверов с выходом в Интернет в сети периметра
description: Сценарии использования серверов с выходом в Интернет в сети периметра
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816282"
---
# Сценарии использования серверов с выходом в Интернет в сети периметра


Приложение App-V 4.5 поддерживает сценарии сервера в Интернете, в которых пользователи, не подключенные к корпоративной сети или отключенные от сети, по-прежнему могут использовать App-V. Как показано на приведенном ниже рисунке, поддерживаются только безопасные протоколы в Интернете (RTSP и HTTPS).

![Схема расположения брандмауэра App-v](images/appvfirewalls.gif)

Вы можете настроить Интернет-решение с помощью сервера ISA Server, где инфраструктура App-V находится во внутренней сети следующими способами:

-   Создайте правило веб-публикации для сервера IIS, на котором размещаются файлы ICO и OSD, и (необязательно) пакеты для потоковой передачи данных, расположенные во внутренней сети. Подробное руководство представлено ниже <https://go.microsoft.com/fwlink/?LinkId=151982> .

-   Создайте правило публикации сервера для веб-сервера App-V (RTSP). Подробное руководство представлено ниже [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) .

Как показано на приведенном ниже рисунке, если инфраструктура реализовала другие брандмауэры между клиентом и сервером ISA, а также между сервером ISA и внутренней сетью, для поддержки потока трафика должны быть созданы правила брандмауэра для протоколов RTSP (TCP 322) и HTTPS (TCP 443). Кроме того, если вы реализовали брандмауэры между сервером ISA и внутренней сетью, для участников домена необходимо разрешить туннелирование через брандмауэр (DNS, LDAP, Kerberos, SMB/CIFS).

![Схема брандмауэра пограничной сети для App-v](images/appvperimeternetworkfirewall.gif)

Так как решения брандмауэра отличаются от среды к среде, в руководстве, описанном в этом разделе, описывается трафик, который требуется для настройки среды App-V в сети периметра. Эти сведения также относятся к рекомендуемым серверам внутренней сети.

Поместите в демилитаризованную сеть следующие серверы:

-   Сервер управления App-V

-   Сервер IIS для публикации и потоковая передача

**Примечание**  Рекомендуется размещать сервер управления и сервер IIS на разных компьютерах.

 

Поместите в внутреннюю сеть следующие серверы:

-   Сервер содержимого

-   Хранилище данных (SQL Server)

-   Контроллер домена Active Directory

## Требования к трафику


В приведенных ниже таблицах перечислены требования к трафику для обмена данными через Интернет и демилитаризованную сеть и от демилитаризованной зоны к внутренней сети.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Требования к трафику из Интернета в демилитаризованную сеть</th>
<th align="left">Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>RTSP (обновление публикации и потоковые пакеты)</p></td>
<td align="left"><p>TCP 322 по умолчанию; Это можно изменить на сервере управления App-V.</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS (файлы ICO и OSD и потоковые пакеты)</p></td>
<td align="left"><p>TCP 443 по умолчанию; Это можно изменить в конфигурации IIS.</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Требования к трафику из периметра внутренней сети</th>
<th align="left">Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server</p></td>
<td align="left"><p>TCP 1433 является значением по умолчанию, но может быть настроено в SQL Server.</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>Если каталог содержимого удален с серверов управления (-ов) или сервера IIS (рекомендуется).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP и UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>LDAP</p></td>
<td align="left"><p>TCP и UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>Разрешение имен внутренних ресурсов (может быть удалено с использованием файла узла на серверах сети периметра)</p></td>
</tr>
</tbody>
</table>

 

 

 




