---
title: Рекомендации по безопасности в App-V 5.1
description: Рекомендации по безопасности в App-V 5.1
author: dansimp
ms.assetid: 6bc6c1fc-f813-47d4-b763-06fd4faf6a72
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a5606b3e0ba5e6fb8c62f14e2ed8d93ea2cf134
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814765"
---
# Рекомендации по безопасности в App-V 5.1


В этой статье содержится краткий обзор учетных записей и групп, файлов журналов и других вопросов, связанных с безопасностью, для Microsoft Application Virtualization (App-V) 5,1.

**Важно.**  
Приложение App-V 5,1 не является продуктом для обеспечения безопасности и не предоставляет никаких гарантий для безопасной среды.



## Функция PackageStoreAccessControl (PSAC) устарела


В июне 2014 функция PackageStoreAccessControl (PSAC), которая была введена в Microsoft Application Virtualization (App-V) 5,0 с пакетом обновления 2 (SP2), устарела как для однопользовательского, так и для многопользовательского окружения.

## Общие рекомендации по безопасности


**Общие сведения о рисках для системы безопасности.** Наиболее серьезный риск для App-V 5,1 заключается в том, что его функции могут быть перехвачены неавторизованным пользователем, который затем может заново настроить данные ключа на клиентах App-V 5,1. Прекращение функциональных возможностей App-V 5,1 в течение короткого промежутка времени из-за атаки типа "отказ в обслуживании" обычно не вызывает катастрофического воздействия.

**Физическая защита компьютеров**. Безопасность не завершена без физического обеспечения безопасности. Любой пользователь, имеющий физический доступ к приложению App-V 5,1, может вызвать атаку на всю клиентскую базу. Любые потенциальные физические атаки следует учитывать в случае высокой опасности и устранения соответствующих проблем. Серверы App-V 5,1 должны храниться в физически надежной серверной комнате с управляемым доступом. Защитите эти компьютеры, если администраторы не находятся в физическом режиме, с помощью операционной системы и запирания компьютера или защищенной экранной заставки.

**Установка последних обновлений для системы безопасности на всех компьютерах**. Чтобы получать сведения о последних обновлениях для операционных систем, Microsoft SQL Server и App-V 5,1, подпишитесь на службу уведомлений системы безопасности ( <https://go.microsoft.com/fwlink/p/?LinkId=28819> ).

**Используйте надежные пароли и передавайте фразы**. Всегда используйте надежные пароли с 15 и более знаками для всех учетных записей администраторов App-V 5,1 и App-V 5,1. Никогда не используйте пустые пароли. Дополнительные сведения о концепциях паролей можно найти в статье "пароли и политики учетных записей" на сайте TechNet ( <https://go.microsoft.com/fwlink/p/?LinkId=30009> ).

## Учетные записи и группы в App-V 5,1


Рекомендации по управлению учетными записями пользователей — это создание глобальных групп домена и добавление в них учетных записей пользователей. Затем добавьте глобальные учетные записи домена в необходимые локальные группы App-V 5,1 на серверах App-V 5,1.

**Примечание.**  
Учетные записи клиентских компьютеров App-V, которые должны подключаться к серверу публикаций, должны входить в локальную группу " **Пользователи** сервера публикаций". По умолчанию все компьютеры домена входят в группу " **Авторизованные пользователи** ", которая входит в локальную группу " **Пользователи** ".



### <a href="" id="-------------app-v-5-1-server-security"></a> Безопасность App-V 5,1 Server

При установке App-V 5,1 группы не создаются автоматически. Вы должны создать следующие глобальные группы доменных служб Active Directory для управления работой сервера App-V 5,1.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя группы</th>
<th align="left">Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Группа администраторов управления App-V</p></td>
<td align="left"><p>Используется для управления сервером управления App-V 5,1. Эта группа создается при установке сервера управления App-V 5,1.</p>
<div class="alert">
<strong>Важно.</strong><br/><p>После завершения установки вы не сможете создать группу с помощью консоли управления.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Учетная запись службы управления для чтения и записи базы данных</p></td>
<td align="left"><p>Предоставляет доступ к базе данных управления для чтения и записи. Эта учетная запись должна создаваться во время установки базы данных системы управления App-V 5,1.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Учетная запись администратора для установки службы управления App-V</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Это необходимо только в том случае, если база данных управления устанавливается отдельно от службы.</p>
</div>
<div>

</div></td>
<td align="left"><p>Предоставляет общий доступ к таблице схемы-версии в базе данных управления. Эта учетная запись должна создаваться во время установки базы данных системы управления App-V 5,1.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Учетная запись администратора установки службы отчетов App-V</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Это необходимо только в том случае, если база данных отчетов устанавливается отдельно от службы.</p>
</div>
<div>

</div></td>
<td align="left"><p>Открытый доступ к таблице схемы-версии в базе данных отчетов. Эта учетная запись должна создаваться при установке базы данных Reporting App-V 5,1.</p></td>
</tr>
</tbody>
</table>



Рассматривайте следующие дополнительные сведения:

-   Доступ к общим ресурсам пакета: Если общий доступ находится на том же компьютере, что и сервер управления, **Сетевая** служба должна иметь доступ на чтение к общему ресурсу. Кроме того, на каждом клиентском компьютере App-V должен быть доступ на чтение к общему доступу к пакету.

    **Примечание.**  
    В предыдущих версиях App-V общий доступ к пакетам назывался общим контентом.



-   Регистрация серверов публикаций с помощью сервера управления: сервер публикаций должен быть зарегистрирован на сервере управления. Например, его необходимо добавить в базу данных, чтобы учетные записи сервера публикации могли обращаться к API-интерфейсу службы управления.

### <a href="" id="-------------app-v-5-1-package-security"></a> Безопасность пакета App-V 5,1

Ниже приведены сведения о том, как обеспечить безопасность виртуализированных пакетов.

-   Если установщик приложения применяет список управления доступом (ACL) к файлу или каталогу, этот список ACL не сохраняется в пакете. Если при развертывании пакета этот файл или каталог изменяется пользователем, он либо наследует список ACL от **% UserProfile%** , либо наследует список ACL для каталога целевого компьютера. Первый случай происходит в том случае, если файл или каталог не существует в виртуальной файловой системе. в последнем случае это случается, если файл или каталог находятся в папке виртуальной файловой системы, например **% WINDIR%**.

## <a href="" id="---------app-v-5-1-log-files"></a> Файлы журнала App-V 5,1


Во время установки App-V 5,1 файлы журнала программы установки создаются в папке **% TEMP%** для пользователя, выполняющего установку.






## Статьи по теме


[Подготовка среды для развертывания App-V 5.1](preparing-your-environment-for-app-v-51.md)









