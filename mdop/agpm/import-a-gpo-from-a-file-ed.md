---
title: Импорт объекта групповой политики из файла
description: Импорт объекта групповой политики из файла
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820722"
---
# Импорт объекта групповой политики из файла


Если вы экспортировали объект групповой политики (GPO) в файл CAB, вы можете импортировать параметры политики из этого GPO в существующий объект GPO в другом лесе. Импорт параметров политики в существующий объект групповой политики заменяет все параметры политики в этом GPO. Сведения об экспорте параметров GPO в CAB-файл можно найти в разделе [Экспорт объекта групповой политики в файл](export-a-gpo-to-a-file.md).

Для выполнения этой процедуры требуется учетная запись пользователя с ролью редактора или администратора расширенного управления групповыми политиками (полный доступ) или необходимых разрешений в расширенном управлении групповой политикой (ГРУППОВое управление).Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

## <a href="" id="bkmk-existing"></a>


**Импорт параметров политики в существующий объект групповой политики**

1.  В дереве **консоли управления групповыми политиками** нажмите **изменить элемент управления** в домене, в который вы хотите импортировать параметры политики.

2.  На вкладке **содержание** откройте вкладку **Управление** , чтобы отобразить управляемые объекты групповой политики.

3.  Изучите конечный объект групповой политики, в который вы хотите импортировать параметры политики.

4.  Щелкните целевой объект групповой политики правой кнопкой мыши, выберите пункт **Импорт из**, а затем — **файл**.

5.  Следуйте указаниям **мастера импорта параметров** для выбора резервной копии GPO, импорта параметров политики для замены ее в ЦЕЛЕВОМ объекте GPO и ввода комментария для контрольного GPO целевого объекта. По умолчанию конечный объект GPO возвращается после завершения работы мастера.

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть редактором или администратором расширенного управления групповыми политиками (полный доступ). В частности, необходимо иметь **содержимое списка**, **изменить параметры**и **импортировать разрешения GPO** для домена, и объект групповой политики должен быть извлечен вами.

-   Несмотря на то, что редактор не может импортировать параметры политики в новый объект групповой политики во время его создания, редактор может запросить создание нового объекта групповой политики, а затем импортировать в него параметры политики после ее создания.

### Дополнительные ссылки

-   [Использование тестовой среды](using-a-test-environment.md)

 

 





