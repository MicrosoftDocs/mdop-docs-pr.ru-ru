---
title: Высокоуровневая архитектура для MBAM 1.0
description: Высокоуровневая архитектура для MBAM 1.0
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825239"
---
# Высокоуровневая архитектура для MBAM 1.0


Администрирование и мониторинг Microsoft BitLocker (MBAM) — это решение для шифрования данных между клиентом и сервером, которое помогает упростить подготовку и развертывание BitLocker, улучшить соответствие BitLocker и создавать отчеты, а также сократить расходы на поддержку. MBAM включает в себя функции, описанные в этом разделе.

Кроме того, в этом видеоролике представлен обзор архитектуры MBAM и MBAM настройки. Дополнительные сведения можно найти в статье [Обзор развертывания и архитектуры MBAM](https://go.microsoft.com/fwlink/p/?LinkId=258392).

## Общие сведения об архитектуре


На приведенной ниже схеме показана архитектура MBAM. Односерверная топология развертывания MBAM, в которой представлены функции MBAM. Однако эта топология развертывания MBAM рекомендуется только для лабораторных сред.

**Примечание**  Для рабочего развертывания рекомендуется по крайней мере MBAM топология развертывания на основе трех компьютеров. Дополнительные сведения о топологиях развертывания MBAM см. [в разделе Развертывание инфраструктуры сервера MBAM 1,0](deploying-the-mbam-10-server-infrastructure.md).

 

![топология развертывания на едином сервере MBAM](images/mbam-1-server.jpg)

1.  **Сервер администрирования и наблюдения**. Сервер администрирования и мониторинга MBAM установлен на сервере Windows и размещает веб-сайт администрирования и управления MBAM и веб-службы мониторинга. Веб-сайт администрирования и управления MBAM используется для определения состояния соответствия требованиям предприятия, для проверки активности, для управления возможностями оборудования и для доступа к данным восстановления, таким как ключи восстановления BitLocker. Сервер администрирования и наблюдения подключается к следующим базам данных и службам:

    -   База данных восстановления и оборудования. База данных восстановления и оборудования устанавливается на сервер под управлением Windows и поддерживаемый экземпляр SQLServer. Эта база данных хранит данные для восстановления и сведения об оборудовании, полученные с клиентских компьютеров MBAM.

    -   База данных соответствия требованиям и аудита. База данных соответствия и аудита установлена на сервере Windows и поддерживаемом экземпляре SQLServer. Эта база данных хранит данные соответствия требованиям для клиентских компьютеров MBAM. Эти данные используются преимущественно для отчетов, размещенных службами SQL Server Reporting Services (SSRS).

    -   Отчеты о соответствии и аудите. Отчеты о соответствии и аудите устанавливаются на сервере под управлением Windows и поддерживает экземпляр SQLServer, на котором установлен компонент SSRS. Эти отчеты обеспечивают администрирование и мониторинг отчетов Microsoft BitLocker. Эти отчеты можно получить на веб-сайте администрирования и управления MBAM или непосредственно с сервера SSRS.

2.  **Клиент MBAM**. Клиент администрирования и мониторинга Microsoft BitLocker выполняет следующие задачи:

    -   Использует групповую политику для принудительного шифрования BitLocker клиентских компьютеров в корпоративной среде.

    -   Собирает ключ восстановления для трех типов дисков данных BitLocker: диски операционной системы, несъемные диски с данными и съемные носители данных (USB).

    -   Сбор сведений о восстановлении и сведений об оборудовании для клиентских компьютеров.

    -   Собирает данные о соответствии для компьютера и передает их в систему отчетности.

3.  **Шаблон политики**. Шаблон групповой политики MBAM установлен на поддерживаемом сервере или клиентском компьютере под управлением Windows. Этот шаблон используется для указания параметров реализации MBAM для шифрования диска BitLocker.

## Статьи по теме


[Начало работы с MBAM 1.0](getting-started-with-mbam-10.md)

 

 




