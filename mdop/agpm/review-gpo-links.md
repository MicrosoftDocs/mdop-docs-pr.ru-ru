---
title: Проверка ссылок объекта групповой политики
description: Проверка ссылок объекта групповой политики
author: dansimp
ms.assetid: 3c472448-f16a-493c-a229-5ca60a470965
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe8b40b4401f08a36217237487bf2b2c0c6c0689
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818342"
---
# Проверка ссылок объекта групповой политики


Вы можете отобразить схему, в которой выбранные объекты групповой политики (GPO) или GPO связаны с организационными подразделениями. Схемы связей GPO обновляются каждый раз, когда объект групповой политики управляется, импортируется или возвращается.

Для выполнения этой процедуры требуется учетная запись пользователя с ролью "рецензент", "редактор", "Утверждающий" или администратором расширенного управления групповыми политиками (полный доступ) или необходимыми разрешениями в расширенном управлении групповой политикой. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

## Просмотр ссылок GPO


-   [Для одного или нескольких GPO](#bkmk-gpos)

-   [Для одной или нескольких версий GPO](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**Отображение связей GPO для одного или нескольких объектов групповой политики**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений перейдите на вкладку **управляемые**, **ожидающие**или **корзины** , чтобы отобразить объекты групповой политики.

3.  Выберите один или несколько объектов групповой политики, для которых нужно отобразить ссылки, щелкните правой кнопкой мыши выделенный объект групповой политики, выберите пункт **Параметры**, а затем — **ссылки на объекты GPO** , чтобы отобразить схему доменов и организационных подразделений со ссылками на выбранные объекты GPO (-ы).

### <a href="" id="bkmk-gpo-versions"></a>

**Отображение связей GPO для одной или нескольких версий GPO**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений откройте вкладку **управляемая** **или корзины** , чтобы отобразить GPO.

3.  Дважды щелкните объект групповой политики, чтобы просмотреть его историю.

4.  Щелкните правой кнопкой мыши версию объекта групповой политики, для которого нужно просмотреть параметры, выберите пункт **Параметры**, а затем — **отчет HTML** или **отчет XML** , чтобы просмотреть сводку по параметрам объекта групповой политики.

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть рецензентом, редактором, утверждающим или администратором расширенного управления групповыми политиками (полный доступ). В частности, необходимо иметь **содержимое списка** и разрешения на **Чтение параметров** для GPO. Кроме того, чтобы отобразить список объектов групповой политики, необходимо иметь разрешение " **содержимое списка** " для домена.

### Дополнительные ссылки

-   [Выполнение задач рецензента](performing-reviewer-tasks.md)

 

 





