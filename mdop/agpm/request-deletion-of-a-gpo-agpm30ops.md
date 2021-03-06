---
title: Запрос на удаление объекта групповой политики
description: Запрос на удаление объекта групповой политики
author: dansimp
ms.assetid: 576ece5c-dc6d-4b5e-8628-01c15ae2c9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87368d9f132d1ef7dc6a70fffa0611d33a23aa78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818442"
---
# Запрос на удаление объекта групповой политики


Если вы не являетесь утверждающим или администратором РАСШИРЕНного управления правами (полный доступ), необходимо запросить удаление объекта групповой политики (GPO).

Для выполнения этой процедуры требуется учетная запись пользователя с ролью "редактор" или необходимыми разрешениями в расширенном управлении групповыми политиками. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Запрос удаления управляемого объекта групповой политики**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** откройте вкладку **Управление** , чтобы отобразить управляемые объекты групповой политики.

3.  Щелкните правой кнопкой мыши объект групповой политики, который вы хотите удалить, и выберите команду **Удалить**.

    -   Чтобы удалить GPO из архива, не открывая внедренный объект, не находясь в рабочей среде, выберите команду **Удалить GPO из архива**.

    -   Чтобы удалить GPO из архивной и производственной сред, выберите команду **удалить объект групповой политики из архива и из рабочей**среды.

4.  Если у вас нет специального разрешения на удаление объектов групповой политики, необходимо отправить запрос на удаление развернутого объекта групповой политики. Чтобы получить копию запроса, введите свой адрес электронной почты в поле **"копия"** . Введите Примечание, которое будет отображаться в контрольной записи для объекта групповой политики, и нажмите кнопку **Отправить**.

5.  После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**. Объект групповой политики отображается в списке объектов групповой политики на вкладке **ожидающие** . Когда утверждающий утвердил ваш запрос, объект GPO будет перемещен с вкладки " **ожидающие** " на вкладку " **Корзина** ", где ее можно восстановить или уничтожить.

### Дополнительные рекомендации

-   Для выполнения этой процедуры необходимо быть редактором по умолчанию. В частности, необходимо иметь **содержимое списка** и разрешения на **изменение параметров** для GPO.

-   Чтобы отменить запрос перед его утверждением, откройте вкладку **Ожидание** . Щелкните объект групповой политики правой кнопкой мыши и выберите команду **снять**. Объект групповой политики будет возвращен на вкладку " **управляемые** ".

-   Чтобы удалить неуправляемый объект групповой политики из производственной среды, не открывая его сначала, в **консоли управления групповыми политиками**нажмите кнопку **лес**, выберите ** &lt; пункт &gt; ** **домены**, а затем — пункт **объекты групповой политики**. Щелкните ненужный объект групповой политики правой кнопкой мыши и выберите команду **Удалить**.

### Дополнительные ссылки

-   [Выполнение задач редактора](performing-editor-tasks-agpm30ops.md)

 

 





