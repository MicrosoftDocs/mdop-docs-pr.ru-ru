---
title: Планирование развертывания сервера App-V 5.1
description: Планирование развертывания сервера App-V 5.1
author: dansimp
ms.assetid: eedd97c9-bee0-4749-9d1e-ab9528fba398
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31e3a116eb511356b061e6ccb18c7e25c060a66e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813437"
---
# Планирование развертывания сервера App-V 5.1


Серверная инфраструктура Microsoft Application Virtualization (App-V) 5,1 состоит из набора специализированных функций, которые можно установить на одном или нескольких серверных компьютерах в зависимости от требований предприятия.

## Планирование развертывания сервера App-V 5,1


Сервер App-V 5,1 состоит из следующих компонентов:

-   Сервер управления — предоставляет общую функциональность управления для инфраструктуры App-V 5,1.

-   База данных управления — упрощает предварительное развертывание баз данных для управления App-V 5,1.

-   Сервер публикации — предоставляет функции размещения и потоковой передачи для виртуальных приложений.

-   Сервер отчетов — предоставляет службы отчетов App-V 5,1.

-   База данных отчетов — упрощает предварительное развертывание баз данных для отчетов App-V 5,1.

В списке ниже приведены рекомендуемые методы для установки инфраструктуры сервера App-V 5,1.

-   Установите сервер App-V 5,1. Дополнительные сведения можно найти в разделе [развертывание сервера App-V 5,1](how-to-deploy-the-app-v-51-server.md).

-   Установите на отдельных компьютерах базу данных, отчеты и функции управления. Дополнительные сведения можно найти в разделе [Установка баз данных управления и отчетов на разных компьютерах из служб управления и отчетов](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md).

-   Используй электронную рассылку программного обеспечения (ESD). Дополнительные сведения [можно найти в разделе Развертывание пакетов приложения App-V 5,1 с помощью электронного распространения программного обеспечения](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md).

-   Установите все компоненты сервера на одном компьютере.

## <a href="" id="---------app-v-5-1-server-interaction"></a> Взаимодействие с сервером App-V 5,1


В этом разделе содержатся сведения о том, как взаимодействуют различные роли сервера App-V 5,1.

Сервер управления App-V 5,1 включает в себя репозиторий пакетов и их назначенные конфигурации. Для серверов публикаций, которые зарегистрированы на сервере управления, связанные метаданные предоставляются на серверы публикаций, которые будут использоваться при получении запросов на обновление публикации с компьютеров, на которых запущен клиент App-V 5,1. Серверы публикации App-V 5,1, управляемые с помощью одного сервера управления, могут поддерживать различные клиенты и могут иметь разные имена веб-сайтов и привязки портов. Кроме того, все серверы публикаций, управляемые одним сервером управления, являются репликами друг друга.

**Примечание**  Сервер управления не выполняет балансировку нагрузки. Связанные метаданные просто передаются на сервер публикаций для использования при обработке запросов клиентов.

 

## Протоколы, связанные с сервером, и внешние возможности


Ниже отображаются сведения о серверных протоколах, используемых серверами App-V 5,1. В таблице также есть механизм составления отчетов для каждого типа сервера.

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Тип сервера</th>
<th align="left">Протоколы</th>
<th align="left">Необходимые внешние функции</th>
<th align="left">Отчеты</th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Сервер IIS</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>Для этой комбинации протоколов сервера требуется механизм синхронизации содержимого между сервером управления и потоковым сервером. При использовании HTTP или HTTPS используйте сервер IIS и брандмауэр, чтобы защитить сервер от доступа к Интернету.</p></td>
<td align="left"><p>внутренний</p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p>Файл</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>Эта комбинация протоколов сервера должна поддерживать синхронизацию содержимого между сервером управления и потоковым сервером. Используйте клиентский компьютер с функцией обмена файлами или потоковой передачи.</p></td>
<td align="left"><p>внутренний</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## Статьи по теме


[Планирование развертывания App-V](planning-to-deploy-app-v51.md)

[Развертывание сервера App-V 5.1](deploying-the-app-v-51-server.md)

 

 





