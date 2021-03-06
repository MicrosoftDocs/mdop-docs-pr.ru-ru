---
title: Проектирование серверной инфраструктуры MED-V Server
description: Проектирование серверной инфраструктуры MED-V Server
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824182"
---
# Проектирование серверной инфраструктуры MED-V Server


В этом разделе рассматривается разработка инфраструктуры сервера для каждого экземпляра MED-V. Сюда входит определение того, будет ли экземпляр SQL Server существовать на сервере MED-V или на удаленном сервере, а также от размера базы данных SQL Server. Кроме того, будет определено расположение консоли управления.

## Разработайте и разместите сервер для каждого экземпляра MED-V.


Сервер MED-V реализует политики и хранит сведения о состоянии и истории своих клиентов.

### Конструктивный фактор

MED-V рекомендует использовать Двухъядерный процессор с тактовой частотой 2,8 ГГц и 2 ГБ оперативной памяти. Эта рекомендация основывается на предположении, что сервер MED-V будет работать на выделенном компьютере, а сервер SQL Server и консоль управления MED-V будут работать на отдельных компьютерах.

В результате этой рабочей нагрузки сервер MED-V должен быть сравнительно тонкой загрузкой. В отсутствие конкретных руководств по архитектуре на серверном конструктивном параметре Разработайте сервер с помощью рекомендации MED-V с памятью, соответствующей стандартному конструктивному параметру Организации. Сервер MED-V может быть запущен на виртуальной машине (ВМ) в Windows Server2008 Hyper-V. Если виртуальная машина будет использоваться, убедитесь в том, что она имеет доступ к ресурсам ЦП и памяти, эквивалентные указанным для физического компьютера.

Для хранения файлов конфигурации рабочей области для MED-V необходим достаточный объем дискового пространства, требуемого сервером MED-v. Рабочая область MED-V может использовать только одну виртуальную машину и одну политику для одного или нескольких пользователей. Таким образом, количество рабочих областей MED-V, которые необходимо сохранить, зависит от того, в какой степени используются различные политики для разных пользователей одной и той же виртуальной машины, а также количество виртуальных машин, которые будут использоваться. XML-файлы рабочей области MED-V об30KBся по размеру типичной рабочей области для MED-V. Чтобы определить требуемую емкость диска, умножьте 30 КБ на количество рабочих областей MED-V, которые будут храниться на сервере MED-V.

Наиболее важными сетевыми подключениями для сервера MED-V являются ссылки на них, поэтому сервер находится в сетевом расположении, обеспечивающем максимальную доступную пропускную способность и наиболее надежные ссылки на ее клиентов.

### Отказоустойчивость

В экземпляре MED-V может быть только один активный сервер MED-v, а в MED-V нет стандартных возможностей для размещения сервера в кластере Microsoft Cluster Server (MSCS), обеспечивающего отказоустойчивость. Пассивный резервный сервер можно настроить вручную.

Чтобы решить, нужно ли вручную настроить пассивный резервный сервер для экземпляра MED-V, определите, разрешено ли пользователям использовать изображения MED-V в автономном режиме. Сведения о [том, как настроить пользователя или группу домена, можно](how-to-configure-a-domain-user-or-groupmedvv2.md)найти в автономном режиме. Если пользователи не могут работать в автономном режиме, они не смогут продолжить работу в случае сбоя сервера MED-V, даже если на клиенте уже запущено рабочее пространство MED-V. Если разрешена работа в автономном режиме, для каждой рабочей области MED-V укажите, как долго клиент может работать в автономном режиме, прежде чем он будет проходить проверку подлинности. Это максимальный период времени, в течение которого сервер может быть недоступен.

## Проектирование и размещение базы данных SQL Server


Сервер MED-V использует базу данных SQL Server для хранения сведений о состоянии клиента и событиях. Вы можете установить базу данных SQL Server на том же компьютере, что и сервер MED-V, или разместить его на отдельном сервере SQL Server, который может при желании быть удаленным. Вы можете предоставить общий доступ к базе данных другим экземплярам MED-V, в этом случае события и оповещения из этих экземпляров будут храниться в той же базе данных, а отчеты будут включать события из всех экземпляров. Вы можете установить базу данных в существующем экземпляре SQL Server, и в этом же экземпляре могут находиться базы данных других серверов MED-V.

Если вы размещаете сервер базы данных в расположении, которое удалено с сервера MED-V, по связям через сети, в которых недостаточно пропускной способности, то при загрузке в консоли может замедлиться загрузка отчетов, а также не выводить последние данные от клиентов. Ознакомьтесь со сведениями о том, как определить [область охвата проекта](define-the-project-scope.md) и использовать эту информацию, чтобы решить, куда следует поместить базу данных SQL Server, в соответствии с заданными положениями службы Организации.

### Конструктивный фактор

Если вы запустите SQL Server на том же сервере, что и MED-V, и SQL Server будет использоваться только для хранения данных этого сервера, начните с рекомендации по работе с MED-V и добавьте ресурсы для загрузки SQL Server. Если SQL Server будет хранить события и оповещения из нескольких экземпляров MED-V, сведения о том, как масштабировать серверный конструктивный фактор, можно найти в руководстве [Планирование инфраструктуры и проектирование Microsoft SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) (http://go.Microsoft.com/fwlink/?LinkId=163302).

Размер базы данных зависит от количества клиентских событий, которые будут храниться в базе данных. События создаются при нормальной работе клиента, например при запуске рабочей области MED-V или при возникновении ошибки в рабочей области MED-V. Интервал по умолчанию, по истечении которого клиент отправляет события, составляет 1 минуту.

Чтобы оценить размер базы данных, определите следующие значения:

-   Количество клиентов в экземпляре MED-V. Максимальное значение — 5 000.

-   Типичная скорость поступления событий. Это зависит от поведения клиента, но занимает от 15 до 20 событий в день на одного клиента.

-   Размер события. Обычно размер составляет около 200 байт.

-   Объем хранилища. Количество дней, в течение которых будут храниться события.

Объедините эти значения, чтобы вычислить размер требуемого хранилища данных в байтах, а затем добавьте для учетной записи для следующих параметров безопасный коэффициент.

-   Ошибки, которые могут создавать большое количество событий от клиента за короткий период времени.

-   Таблица базы данных и организационное пространство.

Чтобы приблизительно оценить требования к оптимизации инфраструктуры в секунду, используйте приведенные выше значения, умножая типичный темп поступления событий на количество клиентов в экземпляре. В результате количество записей, которые можно записать за день, будет вычислено. Разделите это число на 86 400, чтобы получить количество записей, записываемых в секунду. Если операции записи могут быть эквивалентны единственной операцией оптимизации инфраструктуры (IO), это число является обязательным для ввода-вывода. Добавьте буфер для создания отчетов о действиях. Это сложно определить, но зависит от количества используемых вами консолей на экземпляре и частотой, с которой они используются для создания отчетов.

### Отказоустойчивость

Если клиент MED-V запущен, если сервер недоступен, события будут заархивированы на клиенте, а отчеты будут недоступны на консоли управления. Ознакомьтесь с ограничениями уровня обслуживания Организации, определенными в разделе [Определение области охвата проекта](define-the-project-scope.md) , чтобы определить, требуется ли проектирование отказоустойчивой инфраструктуры SQL Server.

MED-V не предоставляет поддержку для выполнения SQL Server в кластере MSCS. Для обеспечения горячего резервирования и предотвращения потери данных в случае сбоя можно поместить SQL Server в конфигурацию доставки журналов. Сведения о доставке журналов можно найти в разделе [Планирование инфраструктуры и проектирование справочника по Microsoft SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) ( https://go.microsoft.com/fwlink/?LinkId=163302) .

## Проектирование консоли управления


Частью функций консоли управления MED-V является тестирование виртуальных машин перед упаковкой для распространения в клиентах MED-V. Следовательно, консоль управления следует разрабатывать с помощью форм-фактора, как можно ближе всего к стандартному клиентскому компьютеру под управлением MED-V.

Консольное приложение для управления установлено вместе с клиентом MED-V и использует Microsoft Virtual PC2007 SP1 вместе с исправлением, описанным в статье 974918 Microsoft Knowledge Base. Необходимо использовать клиентскую операционную систему; консоль управления MED-V не может работать в той же системе, что и сервер MED-V.

Нельзя предоставить общий доступ к консоли управления с несколькими экземплярами сервера MED-V. Адрес сервера MED-V указан при установке клиента MED-V на консоли управления. Это можно изменить после установки, но в любой момент консоль управления может работать только с одним сервером MED-V.

Вы можете использовать несколько консолей управления с одним сервером MED-V. Чтобы избежать конфликтов, можно воспользоваться механизмом, который уведомляет других пользователей консоли, когда одна из них внеса изменения в рабочую область MED-V.

Для каждого экземпляра MED-V определите, сколько консолей управления потребуется и где они будут размещены. Выберите стандартный клиентский конструктивный фактор для MED-V, который будет использоваться для консоли управления.

## Статьи по теме


[Поддерживаемые конфигурации MED-V 1.0 с пакетом обновления 1 (SP1)](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[Настройка сервера MED-V Server в режиме кластера](configuring-med-v-server-for-cluster-mode.md)

[Установка клиента MED-V и консоли управления MED-V](how-to-install-med-v-client-and-med-v-management-console.md)

[Использование пользовательского интерфейса консоли управления MED-V](using-the-med-v-management-console-user-interface.md)

 

 





