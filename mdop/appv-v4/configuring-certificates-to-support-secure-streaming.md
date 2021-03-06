---
title: Настройка сертификатов для обеспечения поддержки безопасной потоковой передачи
description: Настройка сертификатов для обеспечения поддержки безопасной потоковой передачи
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821892"
---
# Настройка сертификатов для обеспечения поддержки безопасной потоковой передачи


По умолчанию служба App-V запускается под учетной записью Network Service. Тем не менее, вы можете создать учетную запись службы в доменных службах Active Directory и заменить ее учетную запись сетевой службы учетной записью домена Active Directory.

Контекст безопасности, под которым запускается служба, важен для настройки расширенной безопасной связи. Этот контекст безопасности должен иметь разрешения на чтение закрытого ключа сертификата. Когда для сервера App-V генерируется *запрос на подписывание сертификата* PKCS \ #10 (CSR), вызывается *поставщик служб шифрования* Windows и создается закрытый ключ. Закрытый ключ защищен с помощью разрешений, предоставленных только учетным записям System и Administrator.

Необходимо изменить списки управления доступом (ACL) для закрытого ключа, чтобы предоставить серверу управления App-V или потоковой передачи доступ к закрытому ключу, требуемому для успешной безопасной передачи данных TLS.

## Получение и установка сертификата


Ниже приведены сценарии для получения и установки сертификата для App-V.

-   Внутренняя инфраструктура открытых ключей (PKI).

-   Центр сертификации (ЦС), выдавший сертификат стороннего поставщика.

    **Примечание**  Если вам нужно получить сертификат из стороннего центра сертификации, воспользуйтесь документацией, доступной на веб-сайте этого ЦС.

     

Если инфраструктура PKI была развернута, обратитесь к администратору инфраструктуры PKI для получения сертификата, который соответствует требованиям, описанным в этой статье. Если инфраструктура PKI недоступна, вы можете получить действительный сертификат с помощью стороннего ЦС.

Пошаговые инструкции по получению и установке сертификата вы найдете в статье <https://go.microsoft.com/fwlink/?LinkId=151969> .

## Статьи по теме


Настройка сертификатов для обеспечения поддержки защищенной потоковой передачи [разрешения на изменение закрытого ключа для поддержки сервера управления или потокового сервера](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





