---
title: Определение различий между объектами групповой политики, версиями объекта групповой политики или шаблонами
description: Определение различий между объектами групповой политики, версиями объекта групповой политики или шаблонами
author: dansimp
ms.assetid: 6320afc4-af81-47e8-9f4c-463ff99d5a53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fd7966c9c72b2f0d30595af55520940c779a409f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820759"
---
# Определение различий между объектами групповой политики, версиями объекта групповой политики или шаблонами


Вы можете создавать отчеты об отличиях на основе HTML или XML для анализа различий между объектами групповой политики (GPO), шаблонами или различными версиями GPO.

Для выполнения этой процедуры требуется учетная запись пользователя с ролью "рецензент", "редактор", "Утверждающий" или администратором расширенного управления групповыми политиками (полный доступ) или необходимыми разрешениями в расширенном управлении групповой политикой. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

## Определение различий между GPO, версиями объектов групповой политики или шаблонами


-   [Между двумя объектами групповой политики или шаблонами](#bkmk-two-gpos)

-   [Между объектом групповой политики и шаблоном](#bkmk-gpo-and-template)

-   [Между двумя версиями одного объекта групповой политики](#bkmk-two-versions)

-   [Между версией GPO и шаблоном](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**Определение различий между двумя объектами групповой политики или шаблонами**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений щелкните вкладку, чтобы отобразить объекты групповой политики (или шаблоны, если они сравниваются два шаблона).

3.  Выберите два GPO или шаблоны.

4.  Щелкните правой кнопкой мыши один из объектов групповой политики или шаблонов, выберите пункт **различия**, а затем — **отчет о формате HTML** или **отчет в формате XML** для отображения отчета о различиях между параметрами объектов групповой политики (GPO) и шаблонов.

### <a href="" id="bkmk-gpo-and-template"></a>

**Определение различий между объектом групповой политики и шаблоном**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений щелкните вкладку, чтобы отобразить объекты групповой политики (или шаблоны, если они сравниваются два шаблона).

3.  Щелкните объект групповой политики правой кнопкой мыши, выберите пункт " **различия**", а затем — пункт " **шаблон**".

4.  Выберите шаблон и тип отчета, а затем нажмите кнопку **ОК** , чтобы отобразить отчет о разнице, в котором выводятся общие сведения о параметрах GPO и шаблона.

### <a href="" id="bkmk-two-versions"></a>

**Определение различий между двумя версиями одного объекта групповой политики**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений щелкните вкладку, чтобы отобразить объекты групповой политики (или шаблоны, если они сравниваются два шаблона).

3.  Дважды щелкните объект групповой политики, чтобы просмотреть его историю, а затем выберите версии для сравнения.

4.  Щелкните правой кнопкой мыши одну из версий, выберите пункт **различия**, а затем — **отчет HTML** или **отчет в формате XML** для отображения отчета о различиях между параметрами GPO.

### <a href="" id="bkmk-gpo-version-and-template"></a>

**Определение различий между версией GPO и шаблоном**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений щелкните вкладку, чтобы отобразить объекты групповой политики (или шаблоны, если они сравниваются два шаблона).

3.  Дважды щелкните объект групповой политики, чтобы просмотреть его историю.

4.  Щелкните правой кнопкой мыши требуемую версию объекта групповой политики, выберите пункт **отличия**, а затем — **шаблон**.

5.  Выберите шаблон и тип отчета, а затем нажмите кнопку **ОК** , чтобы отобразить отчет о разнице, в котором суммируются параметры версии и шаблона объекта групповой политики.

## Ключевые для отчетов о различиях


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Символ</th>
<th align="left">Значение</th>
<th align="left">Цвет</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Нет</p></td>
<td align="left"><p>Элемент существует с одинаковыми параметрами в обоих объектах групповой политики</p></td>
<td align="left"><p>Зависит от уровня</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[#]</strong></p></td>
<td align="left"><p>Элемент существует в обоих объектах GPO, но с измененными параметрами</p></td>
<td align="left"><p>Синюю</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>[-]</strong></p></td>
<td align="left"><p>Элемент существует только в первом объекте групповой политики</p></td>
<td align="left"><p>Красный</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[+]</strong></p></td>
<td align="left"><p>Элемент существует только во втором объекте групповой политики</p></td>
<td align="left"><p>Зеленый</p></td>
</tr>
</tbody>
</table>

 

-   Для элементов с измененными параметрами измененные параметры определяются при разворачивании элемента. Значение атрибута в каждом объекте групповой политики отображается в том же порядке, в котором эти объекты отображаются в отчете.

-   Некоторые изменения в параметрах могут привести к тому, что элемент будет представлен в виде двух различных элементов (один — только в первый объект групповой политики), но только во второй, а не в виде одного из измененных элементов.

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть рецензентом, редактором, утверждающим или администратором расширенного управления групповыми политиками (полный доступ). В частности, необходимо иметь **содержимое списка** и разрешения на **Чтение параметров** для GPO. Кроме того, чтобы отобразить список объектов групповой политики, необходимо иметь разрешение " **содержимое списка** " для домена.

### Дополнительные ссылки

-   [Выполнение задач рецензента](performing-reviewer-tasks.md)

 

 





