---
title: Создание нового управляемого объекта групповой политики
description: Создание нового управляемого объекта групповой политики
author: dansimp
ms.assetid: b43ce0f4-4519-4278-83c4-c7d5163ddd11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a64e22036bfe99e1d5012d732e3f2e081acdcca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821092"
---
# Создание нового управляемого объекта групповой политики


Новые объекты групповой политики (GPO), созданные с помощью узла **элемента управления изменениями** , будут автоматически управляться, что позволяет управлять ими с помощью расширенного управления групповыми политиками.

Для выполнения этой процедуры требуется учетная запись пользователя с ролью администратора (полного доступа) утверждающего или расширенного управления групповыми политиками или необходимыми разрешениями. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Создание объекта групповой политики с управлением изменениями с помощью РАСШИРЕНного управления**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  Щелкните правой кнопкой мыши узел **контроль изменений** и выберите команду **создать управляемый объект групповой политики**.

3.  В диалоговом окне **новый управляемый объект групповой политики** :

    1.  Введите имя для нового объекта групповой политики.

    2.  Необязательно: введите Примечание для нового объекта групповой политики, которое будет отображаться в **журнале** для объекта групповой политики.

    3.  Для немедленного развертывания нового объекта групповой политики в рабочей среде нажмите кнопку **создать Live**. Чтобы создать новый объект групповой политики в автономном режиме без немедленного развертывания, выберите команду **создать автономно**.

    4.  Выберите шаблон GPO, который будет использоваться в качестве отправной точки для нового объекта групповой политики.

    5.  Нажмите кнопку **ОК**.

4.  После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**. Новый объект групповой политики отображается в списке объектов групповой политики на вкладке " **управляемые** ".

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть утверждающим или администратором расширенного управления групповыми политиками (полный доступ). В частности, необходимо иметь **содержимое списка** и **создать разрешения GPO** для домена.

### Дополнительные ссылки

-   [Создание, администрирование и импорт объекта групповой политики](creating-controlling-or-importing-a-gpo-approver.md)

 

 





