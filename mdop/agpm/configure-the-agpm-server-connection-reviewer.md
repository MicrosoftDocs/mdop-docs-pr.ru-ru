---
title: Настройка подключения к серверу AGPM
description: Настройка подключения к серверу AGPM
author: dansimp
ms.assetid: 74e8f348-a8ed-4d69-a8e0-9c974aaeca2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83a2437ee8c2fe562141ff167cb85c6a06b7cefe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818919"
---
# Настройка подключения к серверу AGPM


Чтобы убедиться в том, что вы подключены к правильному центральному архиву, проверьте конфигурацию подключения сервера расширенного управления групповыми политиками. Если Администратор расширенного управления групповыми политиками (полный доступ) не настроил подключение к серверу РАСШИРЕНного доступа, его необходимо настроить вручную.

**Выбор сервера РАСШИРЕНного выбора**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  В области сведений перейдите на вкладку **сервер расширенного сервера** :

    -   Если параметры на вкладке **сервер расширенного управления групповыми политиками** недоступны, они были централизованно настроены АДМИНИСТРАТОРом расширенного управления правами.

    -   Если доступны параметры на вкладке **сервер расширенного** доступа к сети, введите полное имя компьютера для сервера расширенного доступа (например, Server.contoso.com) и порт, прослушиваемый службой расширенного доступа (по умолчанию используется порт 4600). Нажмите кнопку **Применить**, а затем — **Да** для подтверждения.

### Дополнительные рекомендации

-   Выбранные серверы РАСШИРЕНного доступа определяют, какие GPO отображаются на вкладке " **содержимое** " и к чему применяются параметры вкладки **делегирования домена** . Если вы не управляете централизованно с помощью административного шаблона, каждый администратор групповой политики должен настроить этот параметр таким образом, чтобы он указывал на сервер РАСШИРЕНного управления правами для домена.

### Дополнительные ссылки

-   [Выполнение задач редактора](performing-editor-tasks.md)

-   [Выполнение задач утверждающего](performing-approver-tasks.md)

-   [Выполнение задач рецензента](performing-reviewer-tasks.md)

 

 





