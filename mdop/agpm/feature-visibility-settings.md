---
title: Параметры видимости компонентов
description: Параметры видимости компонентов
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820809"
---
# Параметры видимости компонентов


Параметры шаблона администрирования для расширенного управления групповыми политиками позволяют централизованно настраивать видимость узла и **журнала** **изменений** для администраторов групповой политики, которым применен объект групповой политики (GPO) с этими параметрами.

Ниже перечислены параметры, доступные в разделе User Configuration\\Administrative Templates\\Windows Components\\Microsoft (запрещенные и разрешенные Snap-ins\\Extension оснасток) в **редакторе объектов групповой политики** при редактировании GPO в консоли управления групповыми политиками (GPMC). Если этот путь не отображается, щелкните правой кнопкой мыши папку **Административные шаблоны**и добавьте шаблон для расширенного управления групповыми политиками (, ADMX. adm).

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Параметр</th>
<th align="left">Эффект</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Управление изменениями РАСШИРЕНного управления доступом</strong></p></td>
<td align="left"><p>Если этот флажок установлен или не задан, <strong> узел контроль изменений </strong> отображается в консоли управления групповыми политиками.</p>
<p>Если <strong> этот элемент отключен, </strong> узел изменения не отображается в консоли управления групповыми политиками.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Расширение ссылки по РАСШИРЕНию</strong></p></td>
<td align="left"><p>Если эта политика включена или не настроена, <strong> </strong> в GPMC появляется вкладка "журнал" для каждого связанного объекта групповой политики.</p>
<p>Если этот элемент отключен <strong> , </strong> вкладка История не отображается для связанных объектов групповой политики.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Расширение объекта групповой политики для РАСШИРЕНного расширения</strong></p></td>
<td align="left"><p>Если эта политика включена или не настроена, <strong> </strong> в GPMC для каждого объекта групповой политики появляется вкладка "журнал".</p>
<p>Если этот элемент отключен, вкладка История недоступна <strong> </strong> для объектов групповой политики.</p></td>
</tr>
</tbody>
</table>

 

### Дополнительные ссылки

-   [Параметры административных шаблонов](administrative-template-settings.md)

 

 





