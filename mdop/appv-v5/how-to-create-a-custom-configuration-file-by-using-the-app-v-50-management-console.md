---
title: Создание пользовательского файла конфигурации с помощью консоли управления App-V 5.0
description: Создание пользовательского файла конфигурации с помощью консоли управления App-V 5.0
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814328"
---
# Создание пользовательского файла конфигурации с помощью консоли управления App-V 5.0


Вы можете использовать динамическую конфигурацию для настройки пакета App-V 5,0 для определенного пользователя. Тем не менее, прежде чем можно будет использовать файлы, необходимо сначала создать файл динамической конфигурации (XML) или динамической конфигурации развертывания. Создание файла является расширенной операцией вручную. Общие сведения о файлах динамической конфигурации пользователей можно найти в разделе [сведения о динамической конфигурации App-V 5,0](about-app-v-50-dynamic-configuration.md).

Выполните описанные ниже действия, чтобы создать файл динамической конфигурации пользователя с помощью консоли управления App-V 5,0.

**Создание файла динамической конфигурации пользователя**

1.  Щелкните правой кнопкой мыши имя пакета, который вы хотите просмотреть, и выберите команду **изменить доступ к Active Directory** , чтобы просмотреть конфигурацию, назначенную данной группе пользователей. Кроме того, можно выбрать пакет и нажать кнопку **изменить**.

2.  С помощью списка **сущностей AD с Access**выберите группу AD, которую вы хотите настроить. В раскрывающемся списке выберите пункт **другой** , если он еще не выбран. Будет показана ссылка " **изменить** ".

3.  Нажмите кнопку **Изменить**. Появится динамическая конфигурация пользователя, назначенная группе AD.

4.  Нажмите кнопку **Дополнительно**и выберите пункт **Экспорт конфигурации**. Введите имя файла и нажмите кнопку **сохранить**. Теперь вы можете изменить файл, чтобы настроить пакет для пользователя.

    **У вас есть предложение App-V**? Здесь вы можете добавить предложения и проголосовать [здесь](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **У вас возникла ошибка App-V?** Используйте [Форум TechNet App-V](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).

## Статьи по теме


[Операции, связанные с администрированием и использованием App-V 5.0](operations-for-app-v-50.md)

 

 





