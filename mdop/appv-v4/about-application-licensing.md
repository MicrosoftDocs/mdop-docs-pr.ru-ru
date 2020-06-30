---
title: Сведения о лицензировании приложений
description: Сведения о лицензировании приложений
author: dansimp
ms.assetid: 6b487641-1627-4e91-b829-04f001008176
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546bc630b95fe52f960c7bdfb771d3e2561f9318
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820099"
---
# Сведения о лицензировании приложений


Вы можете управлять лицензиями приложений прямо из консоли управления сервером Application Virtualization.

## Типы лицензий


Система виртуализации приложений System Center в настоящее время поддерживает следующие типы лицензий:

-   **Неограниченная лицензия**— предоставляет доступ к приложению на любое количество одновременных пользователей. Этот метод лицензирования подходит, если вы хотите связать лицензию на уровне Организации с приложением.

-   **Одновременная лицензия**— позволяет определить максимальное количество пользователей, которые могут использовать приложение.

-   " **Лицензия с именем**" — позволяет назначать лицензию отдельному пользователю. Именованную лицензию можно использовать, чтобы гарантировать, что определенный пользователь всегда сможет запускать приложение.

Вы можете сочетать одновременные и именованные лицензии для одного и того же приложения.

Лицензирование отключено по умолчанию, но вы можете включить его на вкладке " **конвейер поставщика** " в диалоговом окне **свойств поставщика** . Дополнительные сведения о включении и отключении лицензирования можно найти [в разделе Настройка и отключение лицензирования приложений](how-to-set-up-or-disable-application-licensing.md).

## Политики поставщика


Политики поставщика были разработаны для модели поставщика услуг приложения (ASP). В этой модели один ASP может размещать единую систему Application Virtualization для нескольких клиентов, где каждый клиент должен оставаться изолированным. Клиенты могут радикально различаться, например, если один клиент может требовать проверку подлинности, а другой — нет. Вы можете использовать политики поставщика для сопоставления разрешений с клиентами, чтобы только утвержденные пользователи могли получать доступ к каждому виртуальному приложению или пакету виртуальных приложений.

Для корпоративных клиентов вы можете использовать эту функцию, если у вас есть строгое требование к лицензированию для одного или нескольких приложений. В этой ситуации компонент лицензирования отключен на вкладке **конвейер поставщика** в диалоговом окне **Свойства поставщика** .

На вкладке **поставщик конвейера** также есть флажки для включения проверки подлинности, авторизации (**принудительного применения параметров разрешений доступа**) и отслеживания**использования журнала (сведения об использовании**). Если у вашей конфигурации есть особые требования, вы можете создать собственные компоненты конвейера и добавить их в систему, нажав кнопку **Дополнительно** .

## Учетные записи


Центр учетных записей — это домен, в котором установлен сервер Application Virtualization. После установки сервера вам будет предложено указать имя домена; домен, в котором установлен компьютер, по умолчанию будет обнаружен и использован. При попытке входа в систему пользователи получат запрос на ввод учетных данных, прежде чем они смогут получить доступ к этому домену.

Система виртуализации приложений поддерживает несколько доменов. Вы можете предоставить доступ к приложениям группам пользователей в других доменах, если установлено отношение доверия между доменами. Пользователи должны вводить учетные данные, которые распознаются каждым доменом.

В консоли управления сервером виртуализации приложений вы можете изменить основной домен (центр учетных записей) и учетные данные, которые используются для доступа к нему.

## Проверка подлинности


Проверка подлинности — это механизм, который используется для подтверждения личности пользователя. Любой пользователь с известным именем пользователя и паролем имеет доступ.

В системе виртуализации приложений вы можете включить или отключить проверку подлинности с помощью флажка на вкладке **конвейер поставщика** . По умолчанию проверка подлинности Windows включена.

## Authorization


Авторизация — это процесс, который используется для подтверждения личности пользователя. После подтверждения личности пользователя система определяет, предоставил ли пользователь доступ к системе и каким приложениям он предоставил доступ. Для включения или отключения авторизации в консоли управления сервером виртуализации приложений установлен флажок **принудительно установить разрешения на доступ** на вкладке **конвейера поставщика** .

В системе Виртуализация приложений доступ предоставляется только для группы пользователей, а не для отдельных пользователей.

## Статьи по теме


[Управление лицензиями приложений на консоли управления серверами](how-to-manage-application-licenses-in-the-server-management-console.md)

[Установка или отключение лицензирования приложений](how-to-set-up-or-disable-application-licensing.md)

[Консоль управления серверами: узел политик поставщика](server-management-console-provider-policies-node.md)

 

 




