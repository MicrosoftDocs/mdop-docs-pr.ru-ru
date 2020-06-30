---
title: Резервное копирование архива
description: Резервное копирование архива
author: dansimp
ms.assetid: 538d85eb-3596-4c1d-bbd7-26bc28857c28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c6888d61e126d603aefa4e818f1070c5a493ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819212"
---
# Резервное копирование архива


Чтобы упростить восстановление архива для расширенного управления групповыми политиками (в случае аварии), администратор РАСШИРЕНного управления правами (Full Control) должен часто архивировать Архив. По умолчанию Архив создается в%ProgramData%\\Microsoft\\AGPM. Однако вы можете указать другой путь во время настройки расширенного управления групповыми политиками (Майкрософт): сервер.

Для выполнения этой процедуры необходимо иметь учетную запись пользователя, у которой есть доступ к обоим серверам (в том числе с установленной службой РАСШИРЕНного доступа к данным) и к папке, содержащей архив.

**Создание резервной копии архива**

1.  Остановите службу РАСШИРЕНного. Дополнительные сведения можно найти в разделе [Запуск и остановка службы расширенного](start-and-stop-the-agpm-service-agpm40.md)просмотра.

2.  Создайте резервную копию архивной папки с помощью проводника, xcopy, Windows Server® резервной копии или другого средства резервного копирования. Убедитесь в том, что вы хотите создать резервную копию скрытых, системных и только для чтения файлов.

3.  Храните архивную резервную копию в безопасном месте.

4.  Перезапустите службу РАСШИРЕНного обслуживания. Дополнительные сведения можно найти в разделе [Запуск и остановка службы расширенного](start-and-stop-the-agpm-service-agpm40.md)просмотра.

**Примечание**  Если администратор РАСШИРЕНного администрирования не будет периодически архивировать Архив, объекты групповой политики (GPO) в архиве архивации не будут актуальными. Чтобы лучше удостовериться в том, что резервная копия архивации актуальна, создайте резервную копию архива в рамках стратегии ежедневного резервного копирования вашей организации.

 

### Дополнительные ссылки

-   [Восстановление архива из резервной копии](restore-the-archive-from-a-backup-agpm40.md)

-   [Перемещение сервера и архива AGPM](move-the-agpm-server-and-the-archive-agpm40.md)

-   [Управление архивами](managing-the-archive-agpm40.md)

 

 




