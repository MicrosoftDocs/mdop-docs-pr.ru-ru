---
title: Изменение параметров объектов групповой политики MBAM 1.0
description: Изменение параметров объектов групповой политики MBAM 1.0
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824282"
---
# Изменение параметров объектов групповой политики MBAM 1.0


Чтобы успешно развернуть администрирование и мониторинг Microsoft BitLocker (MBAM), необходимо сначала определить групповые политики, которые будут использоваться при реализации администрирования и мониторинга Microsoft BitLocker. Более подробную информацию о различных доступных политиках можно найти в разделе [планирование для MBAM 1,0, предъявляемых групповой политикой](planning-for-mbam-10-group-policy-requirements.md). После определения политик, которые вы собираетесь использовать, необходимо изменить один или несколько объектов групповой политики (GPO), которые содержат параметры политики MBAM.

Ниже описаны действия, которые необходимо выполнить, чтобы настроить основные и рекомендуемые параметры объектов групповой политики (GPO), чтобы разрешить MBAM управлять шифрованием BitLocker для клиентских компьютеров организации.

**Изменение параметров объекта групповой политики клиента MBAM**

1.  На компьютере, на котором установлен шаблон групповой политики MBAM, убедитесь в том, что службы MBAM включены.

2.  С помощью консоли управления групповыми политиками (GPMC. msc) или расширенной программы для управления групповыми политиками (для Windows) MDOP выполните указанные ниже действия. Выберите **Конфигурация компьютера**, выберите пункт **политики**, щелкните **Административные шаблоны**, выберите пункт **компоненты Windows**, а затем — пакет **MDOP MBAM (Управление BitLocker)**.

3.  Измените параметры объекта групповой политики, необходимые для включения клиентских служб MBAM на клиентских компьютерах. Для каждой политики в приведенной ниже таблице выберите **Группа политики**, щелкните **политику**и настройте **параметр**.

    Группа политики

    Политика

    Параметр

    Управление клиентами

    Настройка служб MBAM

    Включено. Настройте **конечную точку для восстановления MBAM и службы оборудования** и **выберите данные восстановления BitLocker для хранения**.

    Установите **конечную точку службы соответствия MBAM** и **Введите частоту отчета о состоянии (в минутах)**.

    Разрешение проверки совместимости оборудования

    Служба отключена. Эта политика включена по умолчанию, но не требуется для базовой реализации MBAM.

    Диск операционной системы

    Параметры шифрования диска операционной системы

    Включено. Установите **переключатель выбрать предохранитель для диска операционной системы**. Это необходимо для сохранения данных на диске операционной системы на сервере восстановления ключа MBAM.

    Съемный диск

    Управление использованием BitLocker на съемных дисках

    Включено. Это необходимо, если MBAM сохранит съемные данные на сервере восстановления ключа MBAM.

    Несъемный диск

    Управление использованием BitLocker на съемных дисках

    Включено. Это необходимо, если MBAM сохранит данные фиксированного диска на сервере восстановления ключа MBAM.

    Укажите, **как можно восстановить диски, защищенные с помощью BitLocker** , и **разрешите агент восстановления данных**.



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## Статьи по теме


[Развертывание объектов групповой политики MBAM 1.0](deploying-mbam-10-group-policy-objects.md)









