---
title: Обновление с предыдущих версий до MBAM 2.5 или MBAM 2.5 с пакетом обновления 1 (SP1)
description: Обновление с предыдущих версий до MBAM 2.5 или MBAM 2.5 с пакетом обновления 1 (SP1)
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812752"
---
# Обновление с предыдущих версий до MBAM 2.5 или MBAM 2.5 с пакетом обновления 1 (SP1)


В этом разделе описывается процесс обновления сервера администрирования и мониторинга Microsoft BitLocker (MBAM) и клиента MBAM из более ранних версий MBAM.

**Примечание**  Вы можете перейти непосредственно к MBAM 2,5 или MBAM 2,5 SP1 из любой предыдущей версии MBAM.

 

## Перед началом обновления


Прежде чем приступить к обновлению, ознакомьтесь с приведенными ниже сведениями.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Что нужно знать перед началом работы</th>
<th align="left">Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Если вы устанавливаете веб-сайты MBAM на одном сервере и веб-службах на другом сервере, вы должны использовать командлеты Windows PowerShell для их настройки.</p></td>
<td align="left"><p>Мастер настройки сервера MBAM не поддерживает настройку сайтов на одном сервере и веб-службах на другом сервере.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Если вы выполняете обновление до MBAM 2.5 или 2,5 SP1 из MBAM 2.0 или 2,0 SP1 в Windows Server2008 R2, выполните указанные ниже действия.</p>
<p>На веб-сайте администрирования и мониторинга и на портале самообслуживания не будет работать, если вы установите необходимое программное обеспечение .NET Framework 4.5 после того, как на компьютере уже установлены службы Internet Information Services (IIS).</p>
<p>Эта проблема возникает из-за того, что ASP.NET не удается правильно зарегистрировать в службах IIS, если платформа .NET Framework установлена после установки IIS.</p></td>
<td align="left"><p><strong>Чтобы устранить эту проблему, выполните указанные ниже действия.</strong></p>
<p>Запустите <strong> Aspnet_regiis — i </strong> из следующего местоположения:</p>
<p>C:\windows\microsoft.net\Framework\v4.0.30319</p>
<p>Дополнительные сведения можно найти в статье: <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET средства регистрации IIS </a> .</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Зарегистрируйте SPN в учетной записи пула приложений, если выполняются все указанные ниже условия.</p>
<ul>
<li><p>Вы обновляете предыдущую версию MBAM.</p></li>
<li><p>В настоящее время вы не работаете с веб-сайтами MBAM в конфигурации с балансировкой нагрузки, но вы хотите сделать это, когда вы обновите систему до MBAM 2.5 или 2,5 с пакетом обновления 1 (SP1).</p></li>
</ul></td>
<td align="left"><p>Инструкции можно найти <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> в разделе Планирование безопасности веб-сайтов MBAM </a> .</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Что мы рекомендуем</strong></p></td>
<td align="left"><p>Зарегистрируйте имя субъекта-службы (SPN) для учетной записи пула приложений, несмотря на то, что для учетной записи компьютера уже могут быть зарегистрированы SPN.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Зачем мы рекомендуем</strong></p></td>
<td align="left"><p>Регистрация SPN в учетной записи пула приложений требуется для настройки веб-сайтов в балансировке нагрузки или распределенной конфигурации.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Что произойдет, если в учетной записи компьютера уже настроены SPN?</strong></p></td>
<td align="left"><p>MBAM будет использовать уже зарегистрированные SPN, и вам не нужно настраивать дополнительные SPN, но вы не сможете настраивать веб-сайты в балансировке нагрузки или распределенной конфигурации.</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## Инструкции по обновлению инфраструктуры сервера MBAM


Выполните действия, описанные в следующих разделах, чтобы обновить MBAM для изолированной топологии или из топологии интеграции System Center Configuration Manager.

**Обновление инфраструктуры сервера MBAM для изолированной топологии**

1.  Удалите предыдущие версии MBAM из **программ и компонентов** , а также с веб-серверов, чтобы убедиться в том, что данные не записываются из MBAM клиентов в инфраструктуру MBAM. Инструкции можно найти в разделе [Удаление функций и программного обеспечения сервера MBAM](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).

2.  Создавайте резервные копии баз данных.

3.  Удалите предыдущие версии MBAM с сервера SQL Server, используя **программы и компоненты**, в том числе серверы SQL Server, на которых размещены отчеты MBAM, с помощью служб отчетов SQL. Удалите оставшиеся временные файлы или папки сервера MBAM на сервере базы данных и в службах отчетов.

    **Примечание**  Базы данных не будут удалены, а все данные о соответствии требованиям и данных о том, как в ней сохраняются.

     

4.  Установите и настройте базы данных, отчеты и веб-приложения MBAM 2.5 или 2,5 SP1 в нужном порядке. Базы данных будут обновлены на своем своем расположении.

5.  Обновите объекты групповой политики (GPO) с помощью шаблонов MBAM 2,5, чтобы использовать новые возможности MBAM, например принудительное шифрование. Если не обновить объекты групповой политики и клиент MBAM на MBAM 2,5, более ранние версии клиентов MBAM продолжат сообщать о текущих объектах GPO с ограниченными возможностями. Узнайте, [как получить шаблоны групповой политики для MDOP (ADMX)](https://www.microsoft.com/download/details.aspx?id=41183) , чтобы скачать последние версии шаблонов ADMX.

    После того как вы обновите инфраструктуру сервера MBAM, существующие клиентские компьютеры будут успешно передаваться на сервер MBAM 2.5 или 2,5 с пакетом обновления 1 (SP1), и данные восстановления продолжают храниться.

6.  Установите последнюю версию клиента MBAM 2.5 или 2,5 SP1. После развертывания клиентские компьютеры не нужно перезагружать.

**Обновление инфраструктуры MBAM для топологии интеграции System Center Configuration Manager**

1.  Удалите предыдущие версии MBAM из **программ и компонентов** , а также с веб-серверов, чтобы убедиться в том, что данные не записываются из MBAM клиентов в инфраструктуру MBAM. Инструкции можно найти в разделе [Удаление функций и программного обеспечения сервера MBAM](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).

2.  Создавайте резервные копии баз данных.

3.  Удалите предыдущие версии MBAM с сервера SQL Server, используя **программы и компоненты**, в том числе серверы SQL Server, на которых размещены отчеты MBAM, с помощью служб отчетов SQL. Удалите оставшиеся временные файлы или папки сервера MBAM на сервере базы данных и в службах отчетов.

4.  Удалите MBAM с сервера Configuration Manager.

    **Примечание**  Базы данных и объекты Configuration Manager (базовые и MBAM Поддерживаемые семейства компьютеров и отчеты) не будут удалены, а все данные о соответствии требованиям и восстановлении сохраняются в базе данных.

     

5.  Обновите файлы. mof.

6.  Установка и настройка баз данных, отчетов, веб-приложений и интеграции Configuration Manager в MBAM 2.5 или 2,5 SP1, а также в том же порядке. Базы данных и объекты Configuration Manager обновлены на своем своем расположении.

7.  При необходимости обновите объекты групповой политики (GPO) и измените параметры, если вы хотите реализовать новые функции в MBAM, например принудительное шифрование. Если вы не обновите объекты групповой политики, MBAM сохранится о текущих объектах GPO. Узнайте, [как получить шаблоны групповой политики для MDOP (ADMX)](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates) , чтобы скачать последние версии шаблонов ADMX.

    После того как вы обновите инфраструктуру сервера MBAM, существующие клиентские компьютеры будут успешно передаваться на сервер MBAM 2.5 или 2,5 с пакетом обновления 1 (SP1), и данные восстановления продолжают храниться.

8.  Установите последнюю версию клиента MBAM 2.5 или 2,5 SP1. После развертывания клиентские компьютеры не нужно перезагружать.

## Поддержка обновления для клиента MBAM


MBAM поддерживает обновления для клиента MBAM 2.5 из любой более ранней версии клиента MBAM.

**Способы установки клиента MBAM:**

-   После установки серверной инфраструктуры MBAM 2.5 Обновите компьютеры, на которых работает клиент MBAM, или постепенно.

-   Установите клиент MBAM через электронную систему распространения программного обеспечения или с помощью таких средств, как доменные службы Active Directory или System Center Configuration Manager.



## Статьи по теме


[Развертывание MBAM 2.5](deploying-mbam-25.md)

[Развертывание клиента MBAM 2.5](deploying-the-mbam-25-client.md)

[Настройка компонентов сервера MBAM 2.5 Server](configuring-the-mbam-25-server-features.md)

 

## У вас есть предложение MBAM?
- Здесь вы можете добавить предложения и проголосовать [здесь](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).
- Для MBAM проблемы используйте [MBAM Форум TechNet](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam). 





