---
title: Настройка подключений к серверу AGPM
description: Настройка подключений к серверу AGPM
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819072"
---
# Настройка подключений к серверу AGPM


Все версии всех управляемых объектов групповой политики (GPO) хранятся в центральном архиве, так что администраторы групповых политик могут просматривать и изменять GPO в автономном режиме без немедленного воздействия на развернутую версию каждого GPO.

Учетная запись пользователя с ролью администратора РАСШИРЕНного управления правами (полного доступа), учетная запись пользователя утверждающего, создавшего объект групповой политики, которая использовалась в этих процедурах, или учетная запись пользователя с необходимыми разрешениями в расширенном управлении групповыми политиками (ГРУППОВое управление), необходимы для того, чтобы выполнить эти процедуры для централизованной настройки расположения архивов для всех администраторов Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

## Настройка подключений к серверу с помощью РАСШИРЕНного конфигурирования


Как Администратор расширенного управления групповыми политиками, вы можете обеспечить подключение всех администраторов групповой политики к одному и тому же серверу с помощью централизованной настройки соответствующего параметра. Если в вашей среде для некоторых или всех доменов требуется отдельный сервер РАСШИРЕНного доменных данных, настройте дополнительные серверы РАСШИРЕНного использования в качестве исключений по умолчанию. Если вы не настраиваете подключения к серверу РАСШИРЕНного управления правами, каждый администратор групповой политики должен вручную настроить отображение сервера расширенного управления групповыми политиками для каждого домена.

-   [Настройка подключения к серверу РАСШИРЕНного конфигурирования для всех администраторов групповой политики](#bkmk-defaultarchiveloc)

-   [Настройка дополнительных подключений к РАСШИРЕНным конфигурациям для всех администраторов групповой политики](#bkmk-additionalarchiveloc)

-   [Настройка подключения к серверу РАСШИРЕНного конфигурирования для учетной записи вручную](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**Настройка подключения к серверу РАСШИРЕНного конфигурирования для всех администраторов групповой политики**

1.  В дереве **консоли управления групповыми политиками** измените объект групповой политики, который применяется ко всем администраторам групповой политики. (Дополнительные сведения можно найти [в разделе изменение объекта групповой политики](editing-a-gpo-agpm40.md).)

2.  В окне **редактора управления групповыми политиками** выберите элементы **Конфигурация пользователя**, **политики**, **Административные шаблоны**, **компоненты Windows**и управление **групповыми**политиками.

3.  В области сведений дважды щелкните элемент расширенной настройки и выберите **сервер по умолчанию (все домены)**.

4.  В окне **Свойства** установите флажок **включено** и введите полное имя компьютера и порт (например, Server.contoso.com:4600).

5.  Нажмите кнопку **ОК**. Если вы не хотите настраивать дополнительные подключения к серверу РАСШИРЕНного управления правами, закройте окно **редактора групповых политик** и разверните объект групповой политики. (Дополнительные сведения можно найти [в разделе Развертывание объекта групповой политики](deploy-a-gpo-agpm40.md).) При обновлении групповой политики подключение к серверу РАСШИРЕНного политики конфигурации выполняется для всех администраторов групповых политик.

### <a href="" id="bkmk-additionalarchiveloc"></a>

**Настройка дополнительных подключений к серверу РАСШИРЕНного администрирования для всех администраторов групповой политики**

1.  Если подключение к серверу РАСШИРЕНного конфигурирования не настроено, выполните описанные выше действия, чтобы настроить сервер по умолчанию для всех доменов.

2.  Чтобы настроить отдельные серверы расширенного управления групповыми политиками для некоторых или всех доменов (переопределение сервера РАСШИРЕНной политики по умолчанию), в дереве **консоли управления групповыми политиками** измените объект групповой политики, применяемый ко всем администраторам групповой политики. (Дополнительные сведения можно найти [в разделе изменение объекта групповой политики](editing-a-gpo-agpm40.md).)

3.  В окне **редактора управления групповыми политиками** щелкните **Конфигурация пользователя**, **политики**, **Административные шаблоны**, **компоненты Windows**, **а затем выберите**пункт многоязыковый интерфейс.

4.  В области сведений дважды щелкните элемент **групповое руководство: укажите серверы расширенного**выбора.

5.  В окне **Свойства** установите флажок **включено** и нажмите кнопку **Показать**.

6.  В окне " **Показать содержимое** ":

    1.  Щелкните **Добавить**.

    2.  В поле " **имя параметра**" введите имя домена (например, Server1.contoso.com).

    3.  В поле " **значение**" введите имя и порт сервера расширенного использования для этого домена (например, Server2.contoso.com:4600), а затем нажмите кнопку **ОК**. (По умолчанию служба РАСШИРЕНных аналитик прослушивает порт 4600. Чтобы использовать другой порт, ознакомьтесь со сведениями о том, как [изменить службу расширенного использования службы](modify-the-agpm-service-agpm40.md).)

    4.  Повторите эти действия для каждого домена, не использующего сервер по умолчанию для РАСШИРЕНного использования функций.

7.  Нажмите кнопку **ОК** , чтобы закрыть окно " **Показать содержимое** и **Свойства** ".

8.  Закройте окно **редактора управления групповыми политиками** . (Дополнительные сведения можно найти [в разделе Развертывание объекта групповой политики](deploy-a-gpo-agpm40.md).) При обновлении групповой политики для всех администраторов групповой политики настраиваются новые подключения к серверам РАСШИРЕНного ключа.

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

Если вы централизованно настроили подключение к серверу РАСШИРЕНного доступа, параметр для его настройки вручную будет недоступен для всех администраторов групповой политики.

**Настройка сервера РАСШИРЕНного выбора, который будет отображаться для вашей учетной записи, вручную**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  В области сведений щелкните вкладку **сервер расширенного сервера** .

3.  Введите полное имя компьютера для сервера расширенного управления групповыми политиками, который управляет архивом, используемым для этого домена (например, server.contoso.com), и портом, по которому служба управления ГРУППОВыми операциями прослушивает (по умолчанию — порт 4600).

4.  Нажмите кнопку **Применить**, а затем — **Да** для подтверждения.

### Дополнительные рекомендации

-   Вы должны иметь возможность изменить и развернуть объект групповой политики, чтобы выполнить процедуры централизованной настройки подключений к серверам расширенного управления групповыми политиками для всех администраторов групповой политики. Дополнительные сведения: [редактирование GPO](editing-a-gpo-agpm40.md) и [Развертывание объекта групповой политики](deploy-a-gpo-agpm40.md) .

-   Выбранный сервер РАСШИРЕНного доступа к сети определяет объекты, которые будут отображаться на вкладке " **содержимое** ", и укажите расположение, в которое будут применены параметры вкладки **делегирования домена** . Если вы не управляете централизованно с помощью административного шаблона, каждый администратор групповой политики должен настроить этот параметр таким образом, чтобы он указывал на сервер РАСШИРЕНного управления правами для домена.

-   Членство в группе "владельцы создателей групповой политики" должно быть ограничено, soit не используется для обхода управления доступом к GPO. (В **консоли управления групповыми политиками**щелкните **объекты групповой политики** в лесу и домене, в которых вы хотите управлять объектами GPO, выберите пункт **Делегирование**и настройте параметры в соответствии с потребностями Организации.)

### Дополнительные ссылки

-   [Настройка средства расширенного управления групповыми политиками](configuring-advanced-group-policy-management-agpm40.md)

 

 





