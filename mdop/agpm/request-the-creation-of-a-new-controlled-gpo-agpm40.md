---
title: Запрос на создание нового управляемого объекта групповой политики
description: Запрос на создание нового управляемого объекта групповой политики
author: dansimp
ms.assetid: cb265238-386f-4780-a59a-0c9a4a87d736
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 85a435f84e055013c5100a720377f4bffaef4319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820319"
---
# Запрос на создание нового управляемого объекта групповой политики


Если вы не являетесь утверждающим или администратором РАСШИРЕНного управления правами (полный доступ), необходимо запросить создание нового объекта групповой политики (GPO).

Для выполнения этой процедуры требуется учетная запись пользователя с редактором или ролью "рецензент" или "проверяющий" или необходимыми разрешениями в расширенном управлении групповыми политиками. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Создание объекта групповой политики с управлением изменениями с помощью РАСШИРЕНного управления**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  Щелкните правой кнопкой мыши **изменить элемент управления**, а затем выберите команду **создать управляемый объект групповой политики**.

3.  Если у вас нет специального разрешения на создание GPO, необходимо отправить запрос на создание. В диалоговом окне **новый управляемый объект групповой политики** :

    1.  Чтобы получить копию запроса, введите свой адрес электронной почты в поле **"копия"** .

    2.  Введите имя для нового объекта групповой политики.

    3.  Необязательно: введите Примечание для нового объекта групповой политики.

    4.  Чтобы развернуть новый объект групповой политики в рабочей среде домена сразу после утверждения, нажмите кнопку **создать Live**. Чтобы создать новый объект групповой политики в автономном режиме без немедленного развертывания после утверждения, нажмите кнопку **создать в автономном режиме**.

    5.  Выберите шаблон GPO, который будет использоваться в качестве отправной точки для нового объекта групповой политики.

    6.  Нажмите кнопку **Отправить**.

4.  После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**. Новый объект групповой политики отображается в списке объектов групповой политики на вкладке **ожидающие** . Когда утверждающий утвердил ваш запрос, объект групповой политики будет перемещен на вкладку **Управление** .

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть редактором или рецензентом. В частности, для домена требуется разрешение на доступ к **содержимому списка** .

-   Чтобы отказаться от запроса до его утверждения, откройте вкладку **ожидающие** . Щелкните объект групповой политики правой кнопкой мыши и выберите команду **снять**. Объект групповой политики будет удален.

### Дополнительные ссылки

-   [Создание и администрирование объекта групповой политики](creating-or-controlling-a-gpo-agpm40-ed.md)

 

 




