---
title: Изменение уровней создания отчетов журналов и сброс файлов журналов
description: Изменение уровней создания отчетов журналов и сброс файлов журналов
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818049"
---
# Изменение уровней создания отчетов журналов и сброс файлов журналов


С помощью описанной ниже процедуры можно изменить уровень ведения отчета журнала с узла **Application Virtualization** в консоли управления Application Virtualization. Если файл журнала достигнет максимального размера (значение по умолчанию — 256 МБ), сброс будет принудительным, когда происходит следующая запись в журнал. Сброс приводит к созданию нового файла журнала, а старый файл переименовывается в качестве резервной копии.

**Изменение уровня ведения журнала**

1.  Щелкните правой кнопкой мыши узел **Application Virtualization** и во всплывающем меню выберите пункт **свойства** .

2.  На вкладке **Общие** в диалоговом окне **свойства** в раскрывающемся списке **Log Level (журнал** ) выберите необходимый уровень ведения журнала.

    **Примечание**  Если вы выбрали **подробный** уровень ведения журнала, файлы журнала будут значительно увеличиваться очень быстро. Это может препятствовать работе клиента, поэтому рекомендуется использовать этот уровень ведения журнала только для диагностики конкретных проблем.

     

3.  На вкладке **Общие** в диалоговом окне **свойства** в раскрывающемся списке **системный журнал** выберите необходимый уровень ведения журнала.

    **Примечание**  Параметр **уровня системного журнала** определяет уровень сообщений, отправляемых в журнал событий системы. Журнальные сообщения идентичны сообщениям, которые регистрируются в журнале событий клиента, но хранятся в другом расположении.

     

4.  Нажмите кнопку **ОК** или **Применить** , чтобы изменить параметр.

**Сброс файла журнала**

1.  Щелкните правой кнопкой мыши узел **Application Virtualization** и во всплывающем меню выберите пункт **свойства** .

2.  На вкладке **Общие** в диалоговом окне **Свойства** нажмите кнопку **сброс журнала** , чтобы создать резервную копию текущего файла журнала и сразу же начните новый файл журнала. Файлы журнала резервного копирования хранятся в той же папке.

3.  Нажмите кнопку **ОК** или **Применить** , чтобы изменить параметр.

## Статьи по теме


[Настройка клиента в консоли управления клиентом Application Virtualization](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[Разрешения на доступ пользователей в клиенте Application Virtualization](user-access-permissions-in-application-virtualization-client.md)

 

 





