---
title: Запрос на развертывание объекта групповой политики
description: Запрос на развертывание объекта групповой политики
author: dansimp
ms.assetid: 9aa9af29-4754-4f72-b624-bb3e1087cbe1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a9e5fdbbd352adb6d542932c7180c513cfac8b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820379"
---
# Запрос на развертывание объекта групповой политики


После изменения и возврата объекта групповой политики (GPO) разверните этот объект, чтобы он вступил в силу в рабочей среде.

Для выполнения этой процедуры требуется учетная запись пользователя с ролью "редактор" или необходимыми разрешениями для расширенного управления групповыми политиками. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Запрос развертывания объекта групповой политики в рабочей среде**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений откройте вкладку **Управление** , чтобы отобразить управляемые объекты групповой политики.

3.  Щелкните правой кнопкой мыши объект групповой политики, который нужно развернуть, и выберите команду **развернуть**.

4.  Если вы не являетесь администратором или у вас нет специального разрешения на развертывание объектов групповой политики, необходимо отправить запрос на развертывание. Чтобы получить копию запроса, введите свой адрес электронной почты в поле **"копия"** . Введите Примечание, которое будет отображаться в **журнале** для объекта групповой политики, а затем нажмите кнопку **Отправить**.

5.  После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**. Объект групповой политики отображается в списке объектов групповой политики на вкладке **ожидающие** . Когда утверждающий утвердил ваш запрос, объект групповой политики будет перемещен с вкладки **ожидающие** на вкладку **управляемый** и будет развернут.

### Дополнительные рекомендации

-   Для выполнения этой процедуры необходимо быть редактором по умолчанию. В частности, необходимо иметь **содержимое списка** и разрешения на **изменение параметров** для GPO.

-   Чтобы отменить запрос перед его утверждением, откройте вкладку **Ожидание** . Щелкните объект групповой политики правой кнопкой мыши и выберите команду **снять**. Объект групповой политики будет возвращен на вкладку " **управляемые** ".

### Дополнительные ссылки

-   [Изменение объекта групповой политики](editing-a-gpo.md)

 

 





