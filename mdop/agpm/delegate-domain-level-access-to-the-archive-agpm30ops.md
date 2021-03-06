---
title: Предоставление доступа на уровне домена к архиву
description: Предоставление доступа на уровне домена к архиву
author: dansimp
ms.assetid: d232069e-71d5-4b4d-b22e-bef11de1cfd4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01fbc4964493da6ba40382ac40671922eeffa30e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821009"
---
# Предоставление доступа на уровне домена к архиву


Настройте делегирование для своей среды, чтобы администраторы групповой политики могли получать доступ к объектам групповой политики (GPO) в архиве и управлять им. Существуют базовые разрешения, которые можно применять для повышения эффективности операций. Вы можете предоставить разрешения в соответствии с потребностями Организации.

Для выполнения этой процедуры требуется учетная запись пользователя с ролью администратора РАСШИРЕНного управления правами (полного доступа) или необходимых разрешений в расширенном управлении групповыми политиками. Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".

**Делегирование доступа для пользователей и групп с соответствующими разрешениями для всех GPO в рамках домена**

1.  В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.

2.  Откройте вкладку **Делегирование домена** и настройте доступ ко всем объектам групповой политики в домене.

    1.  Чтобы добавить доступ для пользователя или группы, нажмите кнопку **Добавить** , выберите пользователя или группу и нажмите кнопку **ОК**. В диалоговом окне **Добавление группы или пользователя** выберите роль и нажмите кнопку **ОК**.

    2.  Чтобы удалить доступ для пользователя или группы, выберите пользователя или группу и нажмите кнопку **Удалить** .

    3.  Чтобы изменить роли и разрешения, делегированные пользователю или группе, нажмите кнопку " **Дополнительно** ". В диалоговом окне **разрешения** выберите пользователя или группу, установите флажки для всех ролей, которые необходимо назначить этому пользователю или группе, а затем нажмите кнопку **ОК**.

        **Примечание**  В редактор и утверждающие есть разрешения на просмотр.

         

### Дополнительные рекомендации

-   По умолчанию для выполнения этой процедуры необходимо быть администратором РАСШИРЕНной версии (полный доступ). В частности, необходимо иметь разрешение на **изменение безопасности** для домена.

-   Для делегирования доступа на чтение для администраторов групповой политики, использующих многогрупповую политику, необходимо предоставить им **содержимое списка** и разрешения на **Чтение параметров** . Это позволит им просматривать объекты групповой политики на вкладке " **содержимое** " в режиме расширенного использования. Другие разрешения должны быть явным образом делегированы.

-   Редакторам необходимо предоставить разрешение на **Чтение** для развернутой копии объекта групповой политики, чтобы полностью использовать установку программного обеспечения.

-   Членство в группе "владельцы создателей групповой политики" должно быть ограничено, soit не используется для обхода управления доступом к GPO. (В **консоли управления групповыми политиками**щелкните **объекты групповой политики** в лесу и домене, в которых вы хотите управлять объектами GPO, выберите пункт **Делегирование**и настройте параметры в соответствии с потребностями Организации.)

### Дополнительные ссылки

-   [Управление архивами](managing-the-archive.md)

 

 





