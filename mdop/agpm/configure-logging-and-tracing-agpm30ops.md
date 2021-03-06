---
title: Настройка ведения журнала и трассировки
description: Настройка ведения журнала и трассировки
author: dansimp
ms.assetid: 4f89552f-e949-48b0-9325-23746034eaa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6edcb643dd34a20a845cb3d44a0fe8b353a6291
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818982"
---
# Настройка ведения журнала и трассировки


Вы можете централизованно настраивать дополнительные функции ведения журнала и трассировки с помощью административных шаблонов. Это может быть полезно при диагностике проблем, связанных с расширенным управлением групповыми политиками.

Для выполнения этих процедур требуется учетная запись пользователя с ролью администратора расширенного управления групповыми политиками (полного доступа), учетная запись пользователя утверждающего, который создал объект групповой политики (GPO) или учетную запись пользователя с необходимыми разрешениями для управления ГРУППОВыми политиками. Кроме того, для запуска ведения журнала на сервере с РАСШИРЕНным доступом к данным требуется учетная запись пользователя, имеющего доступ к серверу РАСШИРЕНного доступа. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Настройка ведения журнала и трассировки для РАСШИРЕНного протоколирования**

1.  В дереве **консоли управления групповыми политиками** измените объект групповой политики, который применяется ко всем администраторам групповых политик, для которых вы хотите включить ведение журнала и трассировку. (Дополнительные сведения можно найти [в разделе изменение объекта групповой политики](editing-a-gpo-agpm30ops.md).)

2.  В окне **редактора управления групповыми политиками** выберите пункты **Конфигурация компьютера**, **политики**, **Административные шаблоны**, **компоненты Windows**и **Расширенное**управление правами.

3.  В области сведений дважды щелкните элемент **расширенного протоколирования: Настройка ведения журнала**.

4.  В окне **Свойства** щелкните **включить**и настройте уровень детализации для записи в журналах.

5.  Нажмите кнопку **ОК**.

6.  Закройте окно **редактора управления групповыми политиками** . (Дополнительные сведения можно найти [в разделе Развертывание объекта групповой политики](deploy-a-gpo-agpm30ops.md).) После обновления групповой политики необходимо перезапустить службу РАСШИРЕНного редактирования, чтобы запустить, изменить или остановить ведение журнала на сервере РАСШИРЕНного выбора. Администраторы групповой политики должны закрыть и перезапустить GPMC, чтобы начать, изменить или прекратить ведение журнала на своих компьютерах.

    **Расположение файлов трассировки**:

    -   Клиент:%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   Сервер:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### Дополнительные рекомендации

-   Вы должны иметь возможность редактирования и развертывания объекта групповой политики, чтобы настроить ведение журнала и трассировку в РАСШИРЕНном состоянии. Дополнительные сведения: [редактирование GPO](editing-a-gpo-agpm30ops.md) и [Развертывание объекта групповой политики](deploy-a-gpo-agpm30ops.md) .

### Дополнительные ссылки

-   [Настройка средства расширенного управления групповыми политиками](configuring-advanced-group-policy-management.md)

 

 





