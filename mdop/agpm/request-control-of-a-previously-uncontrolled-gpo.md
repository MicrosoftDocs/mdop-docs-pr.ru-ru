---
title: Запросить на управление ранее неуправляемым объектом групповой политики
description: Запросить на управление ранее неуправляемым объектом групповой политики
author: dansimp
ms.assetid: 00e8725d-5d7f-4eed-a5e6-c3631632cfbd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a92db48d87398568900fc0031e688c862a69b417
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818462"
---
# Запросить на управление ранее неуправляемым объектом групповой политики


Для использования расширенного управления групповыми политиками для предоставления управления изменениями для существующего объекта групповой политики (GPO) этот объект должен управляться с помощью РАСШИРЕНного контроля учетных элементов. Если вы не являетесь утверждающим или администратором РАСШИРЕНного управления правами (полный доступ), необходимо запросить управление объектом групповой политики.

Для выполнения этой процедуры требуется учетная запись пользователя с редактором или ролью "рецензент" или "проверяющий" или необходимыми разрешениями в расширенном управлении групповыми политиками. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Управление ранее неуправлениым объектом групповой политики**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  На вкладке **содержание** в области сведений щелкните вкладку **неконтрольные** значения, чтобы отобразить неконтрольные объекты групповой политики.

3.  Щелкните правой кнопкой мыши объект групповой политики, для которого нужно настроить управление групповыми политиками, и выберите пункт **элемент управления**.

4.  Если у вас нет специального разрешения на управление объектами групповой политики, необходимо отправить запрос на управление. Чтобы получить копию запроса, введите свой адрес электронной почты в поле **"копия"** . Введите Примечание, которое будет отображаться в **журнале** объекта групповой политики, а затем нажмите кнопку **Отправить**.

5.  После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**. Объект групповой политики удаляется из списка на вкладке " **неконтрольные элементы** " и добавляется на вкладку " **отложенные** ". Когда утверждающий утвердил ваш запрос, объект групповой политики будет перемещен на вкладку **Управление** .

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть редактором или рецензентом. В частности, необходимо иметь **содержимое списка** и **прочитать параметры** разрешений для домена.

-   Чтобы отменить запрос перед его утверждением, откройте вкладку **Ожидание** . Щелкните объект групповой политики правой кнопкой мыши и выберите команду **снять**. Объект GPO будет возвращен на вкладку **uncontrols** .

### Дополнительные ссылки

-   [Создание, администрирование и импорт объекта групповой политики](creating-controlling-or-importing-a-gpo-editor.md)

 

 





