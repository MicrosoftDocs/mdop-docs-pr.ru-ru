---
title: Устранение неполадок средства расширенного управления групповыми политиками
description: Устранение неполадок средства расширенного управления групповыми политиками
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818252"
---
# Устранение неполадок средства расширенного управления групповыми политиками


В этом разделе перечислены некоторые распространенные проблемы, которые могут возникнуть при использовании расширенного управления групповыми политиками для управления объектами групповой политики (GPO).

## Какие неполадки возникают?


-   [Не удается получить доступ к архиву](#bkmk-access-an-archive)

-   [Состояние GPO меняется для разных администраторов групповой политики.](#bkmk-state-varies)

-   [Не удается изменить соединение с сервером РАСШИРЕНного разрешения](#bkmk-modify-archive-location)

-   [Не удается изменить шаблон или представление по умолчанию, создать, изменить, переименовать, развернуть или удалить GPO](#bkmk-perform-task)

-   [Я не могу использовать имя определенного объекта групповой политики](#bkmk-use-particular-name)

-   [Я не получаю уведомления по электронной почте для РАСШИРЕНного разгрузки](#bkmk-email)

-   [Я не могу использовать порт 4600 для службы РАСШИРЕНного использования.](#bkmk-port)

-   [Служба РАСШИРЕНного обслуживания не запускается](#bkmk-not-start)

-   [Установка программного обеспечения для групповой политики не может установить программное обеспечение](#bkmk-software-installation)

### <a href="" id="bkmk-access-an-archive"></a>Не удается получить доступ к архиву

-   **Причина**: вы не выбрали правильный сервер и порт для архива.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного разрешения: ознакомьтесь [с Разстройкой подключения сервера расширенного](configure-the-agpm-server-connection.md)администрирования.

    -   Если вы не являетесь администратором РАСШИРЕНного разрешения, выполните запрос сведений о подключении для сервера РАСШИРЕНного администрирования с помощью администратора РАСШИРЕНного разрешения. См.: [Настройка подключения к серверу расширенного конфигурирования](configure-the-agpm-server-connection-reviewer.md).

-   **Причина**: служба расширенного управления групповыми политиками не запущена.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного разрешения, запустите службу РАСШИРЕНного администрирования. Дополнительные сведения можно найти в разделе [Запуск и остановка службы расширенного](start-and-stop-the-agpm-service.md)просмотра.

    -   Если вы не являетесь администратором РАСШИРЕНного разрешения, обратитесь за помощью к администратору РАСШИРЕНного администрирования.

### <a href="" id="bkmk-state-varies"></a>Состояние GPO меняется для разных администраторов групповой политики.

-   **Причина**: различные администраторы групповой политики выбрали различные серверы расширенного доменных служб для одного и того же архива.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного разрешения: ознакомьтесь [с Разстройкой подключения сервера расширенного](configure-the-agpm-server-connection.md)администрирования.

    -   Если вы не являетесь администратором РАСШИРЕНного разрешения, выполните запрос сведений о подключении для сервера РАСШИРЕНного администрирования с помощью администратора РАСШИРЕНного разрешения. См.: [Настройка подключения к серверу расширенного конфигурирования](configure-the-agpm-server-connection-reviewer.md).

### <a href="" id="bkmk-modify-archive-location"></a>Не удается изменить соединение с сервером РАСШИРЕНного разрешения

-   **Причина**: Если параметры на вкладке " **сервер расширенного управления групповыми политиками** " недоступны, сервер расширенного доступа к данным был централизованно настроен с помощью административного шаблона.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного доступа к сети: Если параметры на вкладке **сервер расширенного** доступа к данным недоступны, ознакомьтесь [с Разстройкой подключения сервера расширенного](configure-the-agpm-server-connection.md)доступа к данным.

    -   Если вы не являетесь администратором РАСШИРЕНного доступа: Если параметры на вкладке **сервер расширенного** доступа к сети недоступны, вам не нужно изменять сервер расширенного доступа.

### <a href="" id="bkmk-perform-task"></a>Не удается изменить шаблон или представление по умолчанию, создать, изменить, переименовать, развернуть или удалить GPO

-   **Причина**: вам не назначена роль с разрешениями, необходимыми для выполнения задачи или задач.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного доступа к [доменным](delegate-domain-level-access.md) [ресурсам](delegate-access-to-an-individual-gpo.md), сделайте следующее: Разрешения РАСШИРЕНного доступа к доменным объектам будут каскадными из домена на все GPO в архиве. По мере добавления администраторов новой групповой политики на уровне домена их разрешения должны быть заданы для применения к **объекту и вложенным объектам**. Сведения о ролях, которые могут выполнять задачи, и о том, какие разрешения необходимы для выполнения задачи, можно найти в справке по этой задаче.

    -   Если вы не являетесь администратором РАСШИРЕНного доступа и вам требуются дополнительные роли или разрешения: обратитесь за помощью к администратору РАСШИРЕНного администрирования. Обратите внимание, что если вы являетесь редактором, вы можете начать процесс создания объекта групповой политики, развертывания объекта групповой политики или удаления объекта групповой политики из рабочей среды, но необходимо утвердить запрос с помощью администратора утверждающего или РАСШИРЕНного анализа.

### <a href="" id="bkmk-use-particular-name"></a>Я не могу использовать имя определенного объекта групповой политики

-   **Причина**: либо имя GPO уже используется, либо отсутствует разрешение на перечисление объектов групповой политики.

-   **Решение**:

    -   Если имя объекта групповой политики отображается на вкладке " **управляемый**", " **неуправляемый**" или " **ожидающий** ", выберите другое имя. Если развернутый объект групповой политики переименован, но еще не повторно установлен, он будет отображаться под его старым именем в рабочей среде, поэтому старое имя по-прежнему используется. Повторно разверните объект групповой политики, чтобы обновить его имя в рабочей среде, и отпустите это имя для другого объекта групповой политики.

    -   Если имя GPO не отображается на вкладке **управляемые**, **неуправляемые**или **ожидающие утверждения** , возможно, у вас отсутствует разрешение на перечисление объектов групповой политики. Чтобы запросить разрешение, обратитесь к администратору РАСШИРЕНного доступа к сети.

### <a href="" id="bkmk-email"></a>Я не получаю уведомления по электронной почте для РАСШИРЕНного разгрузки

-   **Причина**: допустимый SMTP-сервер электронной почты и адрес электронной почты не предоставлены либо никаких действий, которые создают уведомление по электронной почте.

-   **Решение**:

    -   Если вы являетесь администратором РАСШИРЕНного доступа к сети: для уведомлений по электронной почте о действиях, которые должны отправляться службой РАСШИРЕНного доступа к учетной записи, администратором РАСШИРЕНного **Domain Delegation** доступа к сети должны быть указаны допустимые SMTP-сервер электронной почты и адреса электронной почты утверждающих Дополнительные сведения можно найти в разделе [Настройка уведомлений по электронной почте](configure-e-mail-notification.md).

    -   Уведомления по электронной почте генерируются только в том случае, если редактор, рецензент или другой администратор групповых политик не имеет разрешения, необходимого для создания, развертывания или удаления объекта групповой политики, который отправляет запрос на выполнение одного из этих действий. Автоматическое уведомление о том, что утверждение или отклонение запроса не существует.

### <a href="" id="bkmk-port"></a>Я не могу использовать порт 4600 для службы РАСШИРЕНного использования.

-   **Причина**: по умолчанию порт, на который прослушивается служба расширенного выбора, является портом 4600.

-   **Решение**: Если для службы расширенного доступа к сети недоступен порт 4600, измените каждый файл индекса архива так, чтобы он использовал другой порт, а затем обновите сервер расширенного доступа для всех администраторов групповой политики. Дополнительные сведения можно найти [в разделе Изменение порта, прослушиваемого службой расширенного выбора](modify-the-port-on-which-the-agpm-service-listens.md).

### <a href="" id="bkmk-not-start"></a>Служба РАСШИРЕНного обслуживания не запускается

-   **Причина**: вы изменили параметры для службы расширенного **управления правами** в операционной системе в разделе Администрирование и **службы**.

-   **Решение**: измените параметры **расширенного управления групповыми политиками Microsoft — сервера** в разделе " **Установка и удаление программ**". Дополнительные сведения можно найти [в разделе Изменение учетной записи службы расширенного](modify-the-agpm-service-account.md)редактирования.

### <a href="" id="bkmk-software-installation"></a>Установка программного обеспечения для групповой политики не может установить программное обеспечение

-   **Причина**: с помощью функции пересылки обеспечивается целостность пакетов установки программного обеспечения групповой политики. Несмотря на то, что объекты групповой политики редактируются в автономном режиме, ссылки между пакетами, а также кэшированные данные клиента сохраняются. Это сделано намеренно.

-   **Решение**: при работе с групповой политикой в автономном режиме с помощью групповой политики настройте обновление пакета в другом GPO для ссылки на развернутый объект GPO, а не извлеченную копию. Редактор должен иметь разрешение на **Чтение** для развернутого объекта групповой политики.

 

 





