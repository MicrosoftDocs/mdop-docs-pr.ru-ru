---
title: Поиск и фильтрация списка объектов групповой политики
description: Поиск и фильтрация списка объектов групповой политики
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820262"
---
# Поиск и фильтрация списка объектов групповой политики


С помощью расширенного управления групповыми политиками вы можете выполнить поиск по списку объектов групповой политики (GPO) и их атрибутов, чтобы отфильтровать список объектов GPO. Например, можно выполнить поиск объектов групповой политики с определенным именем, состоянием или примечанием. Вы также можете искать объекты GPO, которые были изменены администратором групповой политики или определенной датой.

## Выполнение сложного поиска


Вы можете выполнить сложный поиск с помощью атрибута "GPO" формата *1: строка поиска 1 атрибут GPO 2: Поиск строки 2... строки поиска по всем столбцам*. При поиске не учитывается регистр.

-   **Атрибут GPO:** Заголовок любого столбца в списке объектов групповой политики в РАСШИРЕНном наборе, кроме **версии компьютера** или **пользователя**. Атрибуты GPO включают имя GPO, состояние, пользователя, который последним изменил объект групповой политики, дату и время последнего изменения объекта групповой политики, Примечание, состояние GPO и фильтр WMI, примененный к объекту групповой политики.

-   **Строка поиска:** Текст, для которого нужно выполнить поиск в указанном столбце. Если строка содержит пробелы, ее необходимо заключить в кавычки.

-   **Строки для поиска по столбцам:** Текст, для которого нужно выполнить поиск во всех столбцах списка (GPO), кроме **версии компьютера** и **пользовательской версии**. Вы можете добавить несколько строк, разделенных пробелами. Если строка содержит пробелы, ее необходимо заключить в кавычки.

Каждый атрибут GPO и пара строк поиска и каждая строка поиска по столбцу объединяются с помощью логической операции и. Результат представляет собой список всех GPO, каждый из которых содержит указанную строку поиска и для которых все строки поиска по столбцам отображаются хотя бы в одном столбце. Поиск возвращает все частично найденные совпадения для строк, чтобы можно было ввести часть имени или имени объекта групповой политики, а также просмотреть список всех GPO, содержащих этот текст в имени.

Ниже приведены примеры поиска.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Описание результата поиска</th>
<th align="left">Поисковый запрос</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Все GPO, имена которых включают в себя <strong> Безопасность текста </strong> и <strong> Северная Америка </strong> .</p></td>
<td align="left"><p><strong>Имя: </strong><strong> </strong><strong> имя безопасности: </strong> &quot; <strong> Северная Америка</strong>&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>Все извлеченные объекты GPO.</p></td>
<td align="left"><p><strong>состояние: </strong> &quot; <strong> извлечено</strong>&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Все GPO, недавно измененные пользователем <strong> администратора </strong> , и недавно измененные в предыдущем месяце.</p></td>
<td align="left"><p><strong>Кем изменено </strong><strong> : </strong><strong> Дата изменения администратора: </strong><strong> lastmonth</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Все объекты групповой политики, в которых <strong> брандмауэр Word </strong> входит в последнее примечание и в котором <strong> отображается безопасность Word </strong> в любом столбце.</p></td>
<td align="left"><p><strong>Примечание: </strong><strong> </strong><strong> Безопасность брандмауэра</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Все GPO, у которых есть состояние " <strong> отключено все параметры" </strong> .</p></td>
<td align="left"><p><strong>состояние объекта групповой политики: </strong><strong> все</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Все GPO, к которым применен фильтр WMI с именем " <strong> Мой фильтр WMI" </strong> и которые имеют состояние " <strong> Параметры конфигурации пользователя" отключены </strong> .</p></td>
<td align="left"><p><strong>фильтр WMI: </strong> &quot; <strong> состояние GPO «мой фильтр WMI» </strong> &quot; <strong> : </strong><strong> пользователь</strong></p></td>
</tr>
</tbody>
</table>

 

## Указание дат


Вы можете выполнять поиск объектов групповой политики, измененных на определенную дату, в определенное время или в течение интервала времени, используя те же специальные условия, доступные при поиске в Windows. Если вы вводите определенную дату или время, необходимо использовать формат, который используется в столбце **изменить дату** . Ниже приведены примеры операций поиска в столбце " **Дата изменения** ".

-   **Дата изменения:****10/10/2009**

-   **Дата изменения:****10/10/2009 9:00:00 AM**

-   **Дата изменения:****thisweek**

При поиске в столбце " **Дата изменения** " можно использовать следующие специальные условия, не учитывающие регистр.

-   **Сегодня**

-   **Вчера**

-   **ThisWeek**

-   **LastWeek**

-   **ThisMonth**

-   **LastMonth**

-   **TwoMonths (Два месяца)**

-   **ThreeMonths (Три месяца)**

-   **ThisYear**

-   **LastYear**

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть рецензентом, редактором, утверждающим или администратором расширенного управления групповыми политиками (полный доступ). В частности, для домена требуется разрешение на доступ к **содержимому списка** .

-   Дополнительные сведения об атрибутах GPO можно найти в статьях [вкладка содержание](contents-tab-features-agpm40.md).

### Дополнительные ссылки

-   [Средство расширенного управления групповыми политиками 4.0](advanced-group-policy-management-40.md)

 

 





