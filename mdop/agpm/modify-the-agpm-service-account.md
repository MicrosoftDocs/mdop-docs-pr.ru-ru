---
title: Изменение учетной записи службы AGPM
description: Изменение учетной записи службы AGPM
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820522"
---
# Изменение учетной записи службы AGPM


Служба управления групповыми политиками — это служба Windows, которая выступает в качестве прокси-сервера, управляет доступом клиентов к объектам групповой политики (GPO) в архивной и рабочей среде. Если эта служба остановлена или отключена, клиенты с РАСШИРЕНным управлением разрешениями не смогут выполнять операции через сервер.

Учетная запись "путь к архиву и служба РАСШИРЕНного поиска" настраивается во время установки сервера РАСШИРЕНного использования и может быть изменена в дальнейшем с помощью **добавления или удаления программ** на сервере расширенного использования.

**Внимание!**  Не изменяйте параметры службы РАСШИРЕНного **управления правами с помощью средств администрирования** и **служб** в операционной системе. Это может привести к невозможности запуска службы РАСШИРЕНного настольных служб.

 

Учетная запись пользователя, которая входит в группу администраторов домена и имеет доступ к серверу расширенного управления групповыми политиками (на компьютере, на котором установлен компонент Advanced Group Policy Management), для выполнения этой процедуры требуется.

**Важно!**  Учетная запись службы РАСШИРЕНного доступа должна иметь полный доступ к объектам групповой политики, которым он управляет, и будет предоставлять **Вход в качестве разрешения на доступ к службам** . Если вы будете управлять объектами групповой политики в одном домене, вы можете создать учетную запись локальной системы для основного контроллера домена в службе расширенного управления групповыми политиками.

Если вы будете управлять объектами групповой политики в нескольких доменах или рядовым сервером является сервер управления групповыми политиками, вы должны настроить другую учетную запись в качестве учетной записи службы РАСШИРЕНного доступа, так как учетная запись локальной системы для одного контроллера домена не может получить доступ к объектам групповой политики в других доменах.

 

**Изменение учетной записи службы РАСШИРЕНного редактирования**

1.  На компьютере, на котором установлен сервер расширенного управления групповыми политиками (Microsoft), нажмите кнопку **Пуск**, выберите пункт **Панель управления**, а затем — **Установка и удаление программ**.

2.  **На вкладке Advanced Group Management (Microsoft) выберите Server (сервер**), а затем нажмите кнопку **изменить**.

3.  Нажмите кнопку **Далее**, а затем — **изменить**.

4.  Следуйте инструкциям на экране, чтобы настроить параметры для службы РАСШИРЕНного выбора.

    1.  В качестве пути к архиву подтвердите или измените расположение архива относительно сервера РАСШИРЕНного поиска. Путь к архиву может указывать на папку на сервере расширенного управления групповыми политиками или в другом месте, но в расположении должно быть достаточно места для хранения всех объектов групповой политики и данных журнала, управляемых этим сервером управления групповыми политиками.

    2.  Введите новые учетные данные для учетной записи службы РАСШИРЕНного доступа к данным.

    3.  Для владельца архива введите учетные данные администратора РАСШИРЕНного управления правами (полный доступ).

5.  Нажмите кнопку **изменить**, после завершения установки нажмите кнопку **Готово**.

### Дополнительные ссылки

-   [Управление службой AGPM](managing-the-agpm-service.md)

 

 





