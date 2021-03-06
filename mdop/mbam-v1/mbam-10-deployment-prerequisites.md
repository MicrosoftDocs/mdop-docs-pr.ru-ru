---
title: Необходимые компоненты развертывания MBAM 1.0
description: Необходимые компоненты развертывания MBAM 1.0
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822662"
---
# Необходимые компоненты развертывания MBAM 1.0


Прежде чем приступить к установке Microsoft BitLocker Administration и Monitoring (MBAM), убедитесь в том, что вы отвечаете необходимым предварительным требованиям для установки продукта. В этом разделе содержится информация, которая поможет вам успешно подготовить рабочую среду перед развертыванием клиентов MBAM и функций сервера.

## Требования для установки функций сервера MBAM


Каждый из функций сервера MBAM имеет определенные предварительные требования, которые должны быть выполнены, прежде чем их можно будет успешно установить. Программа установки MBAM проверяет, выполнены ли все необходимые условия перед началом установки.

### Необходимые условия для установки на сервере администрирования и мониторинга

В следующей таблице приведены требования к установке сервера администрирования и мониторинга MBAM.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Предварительные</th>
<th align="left">Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Роль сервера Windows ServerWeb</strong></p></td>
<td align="left"><p>Эту роль необходимо добавить в серверную операционную систему, поддерживаемую компонентом сервера администрирования и мониторинга MBAM.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Средства управления веб-сервером (IIS)</strong></p></td>
<td align="left"><p><strong>Сценарии и инструменты управления IIS</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Службы ролей веб-сервера</strong></p></td>
<td align="left"><p><strong>Основные возможности HTTP:</strong></p>
<ul>
<li><p>Статическое содержимое</p></li>
<li><p>Документ по умолчанию</p></li>
</ul>
<p><strong>Разработка приложений.</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>Расширяемость .NET</p></li>
<li><p>Расширения ISAPI</p></li>
<li><p>Фильтры ISAPI</p></li>
</ul>
<p><strong>Разрешения</strong></p>
<ul>
<li><p>Проверка подлинности Windows</p></li>
<li><p>Фильтрация запросов</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Возможности Windows Server</strong></p></td>
<td align="left"><p><strong>Компоненты Microsoft .NET Framework 3.5.1:</strong></p>
<ul>
<li><p>.NET Framework 3.5.1</p></li>
<li><p>Активация WCF</p>
<ul>
<li><p>Активация по HTTP</p></li>
<li><p>Активация не по протоколу HTTP</p></li>
</ul></li>
</ul>
<p><strong>Служба активации процессов Windows</strong></p>
<ul>
<li><p>Модель процесса</p></li>
<li><p>Среда .NET</p></li>
<li><p>API конфигурации</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**Примечание**  Список поддерживаемых операционных систем можно найти в разделе [Поддерживаемые конфигурации MBAM 1,0](mbam-10-supported-configurations.md).

 

### Требования для установки для отчетов о соответствии и аудите

Отчеты о соответствии и аудите должны устанавливаться в поддерживаемой версии SQLServer. Предварительные требования к установке для этой функции включают службы SQL Server Reporting Services (SSRS).

Службы SSRS должны быть установлены и запущены во время установки сервера MBAM. Кроме того, службы SSRS следует настроить в режиме "машинный", а не в режиме "не настроено" или "SharePoint".

**Примечание**  Список поддерживаемых операционных систем и версий SQLServer можно найти в разделе [Поддерживаемые конфигурации MBAM 1,0](mbam-10-supported-configurations.md).

 

### Предварительные требования к установке для базы данных восстановления и оборудования

База данных восстановления и оборудования должна быть установлена в поддерживаемой версии SQLServer.

При установке сервера MBAM на сервере SQL Server должны быть установлены и запущены службы ядра СУБД. Функция шифрования прозрачных данных (TDE) должна быть включена.

**Примечание**  Список поддерживаемых операционных систем и версий SQLServer можно найти в разделе [Поддерживаемые конфигурации MBAM 1,0](mbam-10-supported-configurations.md).

 

Функция SQLServer TDE выполняет шифрование и расшифровку данных и файлов журнала в режиме реального времени (I/O). TDE защищает данные, которые находятся в разных частях, включая данные и файлы журнала. Она обеспечивает соответствие множеству законов, нормативных актов и руководств, которые устанавливаются в различных отраслях.

**Примечание**  Поскольку TDE выполняет расшифровку сведений о базе данных в режиме реального времени, сведения о ключе восстановления будут видны, если учетная запись, в которой вы вошли в систему, имеет разрешения на доступ к базе данных при просмотре таблиц SQL для данных ключа восстановления.

 

### Требования для установки базы данных соответствия требованиям и аудита

База данных соответствия требованиям и аудита должна быть установлена в поддерживаемой версии SQLServer.

При установке сервера MBAM на сервере SQL Server должны быть установлены и запущены службы ядра СУБД.

**Примечание**  Список поддерживаемых операционных систем и версий SQLServer можно найти в разделе [Поддерживаемые конфигурации MBAM 1,0](mbam-10-supported-configurations.md).

 

## Требования для установки для клиентов MBAM


Прежде чем приступить к установке клиента MBAM, необходимо выполнить следующие требования:

-   Возможность доверенного платформенного модуля (TPM) версии 1.2

-   Микросхема TPM должна быть включена в BIOS и должна быть переустановлена из операционной системы. Дополнительные сведения можно найти в документации по BIOS.

**Предупреждение**  Убедитесь, что клавиатура, мышь и видео прямо подключены к компьютеру, а не коммутатор клавиатуры, видео, мыши (KVM). КВМ-коммутатор может взаимодействовать с возможностями компьютера, чтобы обнаружить физическое присутствие оборудования.

 

## Статьи по теме


[Планирование развертывания MBAM 1.0](planning-to-deploy-mbam-10.md)

[Поддерживаемые конфигурации MBAM 1.0](mbam-10-supported-configurations.md)

 

 





