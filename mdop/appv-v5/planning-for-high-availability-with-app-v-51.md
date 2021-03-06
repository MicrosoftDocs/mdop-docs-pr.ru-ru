---
title: Планирование высокого уровня доступности в App-V 5.1
description: Планирование высокого уровня доступности в App-V 5.1
author: dansimp
ms.assetid: 1f190a0e-10ee-4fbe-a602-7e807e943033
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c8e0e684051859a4caa2c4ef983c040295bc6d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813480"
---
# Планирование высокого уровня доступности в App-V 5.1


Microsoft Application Virtualization (App-V) 5,1 конфигураций системы может использовать возможности, поддерживающие высокий уровень доступности служб.

Сведения о том, как развертывать App-V 5,1 в высокодоступной конфигурации, можно найти в следующих разделах.

-   [Поддержка кластеризации Microsoft SQL Server](#bkmk-sqlcluster)

-   [Поддержка балансировки нагрузки сети для IIS](#bkmk-iisloadbal)

-   [Поддержка кластерных файловых серверов при работе с режимом SCS](#bkmk-clusterscsmode)

-   [Поддержка зеркального отображения Microsoft SQL Server](#bkmk-sqlmirroring)

-   [Поддержка для Microsoft SQL Server всегда включена](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a>Поддержка кластеризации Microsoft SQL Server


Базу данных управления App-V и базу данных отчетов можно запускать на компьютерах, на которых запущены кластеры Microsoft SQL Server. Тем не менее, необходимо установить базы данных с помощью сценариев.

Инструкции можно найти в разделе [развертывание баз данных App-V с помощью сценариев SQL](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md).

## <a href="" id="bkmk-iisloadbal"></a>Поддержка балансировки нагрузки сети для IIS


С помощью балансировки сетевой нагрузки служб IIS можно настроить высокодоступную среду для компьютеров, на которых выполняются службы управления приложениями, публикации и создания отчетов, которые развертываются с помощью IIS.

Дополнительные сведения о настройке служб IIS и балансировки сетевой нагрузки на компьютерах с операционными системами Windows Server можно узнать ниже.

-   Содержит сведения о настройке служб IIS 7,0.

    [Достижение высокой доступности и масштабируемости — ARR и NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)

-   Настройка Microsoft Windows Server

    [Балансировка сетевой нагрузки](https://go.microsoft.com/fwlink/?LinkId=316370) ( https://go.microsoft.com/fwlink/?LinkId=316370) .

    Эти сведения также относятся к кластерам балансировки сетевой нагрузки (NLB) служб IIS в Windows Server2008, Windows Server2008R2 или Windows Server2012.

    **Примечание**  Компоненты балансировки нагрузки сети для служб IIS в Windows Server2012, как правило, совпадают с Windows Server2008R2. Однако некоторые сведения о задачах изменяются в Windows Server2012. Сведения о новых способах выполнения задач можно найти [в разделе типичные задачи управления и Навигация в Windows server 2012 R2 Preview и Windows server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) ( https://go.microsoft.com/fwlink/?LinkId=316371) .

     

## <a href="" id="bkmk-clusterscsmode"></a>Поддержка кластерных файловых серверов при работе с режимом SCS


Поддерживается приложение App-V 5,1 в режиме общего доступа к хранилищу содержимого (SCS) с кластерными файловыми серверами.

Для включения этой конфигурации можно использовать описанные ниже действия.

-   Настройте App-V 5,1 для работы в режиме клиента SCS. Дополнительные сведения о настройке режима App-V 5,1 SCS можно найти [в разделе Установка клиента App-v 5,1 для общего режима хранения содержимого](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md).

-   Настройте кластер файлового сервера, настроенный как в режиме "Server2012 Scale out", так и в режиме предварительного **2012** с помощью виртуальной сети SAN.

Для проверки конфигурации можно использовать описанные ниже действия.

1.  Добавьте пакет на сервере публикаций. Дополнительные сведения о добавлении пакета можно найти в разделе [Добавление и обновление пакетов с помощью консоли управления](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md).

2.  Выполните обновление публикации на компьютере с клиентом App-V 5,1 и откройте приложение.

3.  Переключите узлы кластера на середину и посредине, чтобы убедиться, что она работает правильно.

Дополнительные сведения о настройке отказоустойчивых кластеров Windows Server можно получить из указанных ниже.

-   [Контрольный список: создание кластеризованного файлового сервера](https://go.microsoft.com/fwlink/?LinkId=316372) ( https://go.microsoft.com/fwlink/?LinkId=316372) .

-   [Используйте общие тома кластера в отказоустойчивом кластере Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316373) ( https://go.microsoft.com/fwlink/?LinkId=316373) .

## <a href="" id="bkmk-sqlmirroring"></a>Поддержка зеркального отображения Microsoft SQL Server


С помощью зеркального отображения Microsoft SQL Server, в котором база данных сервера App-V 5,1 зеркально используется с двумя экземплярами SQL Server, поддерживается поддержка баз данных сервера управления App-V 5,1.

Ознакомьтесь с дополнительными сведениями о настройке зеркального отображения Microsoft SQL Server.

-   [Инструкции: Подготовка зеркальной базы данных для зеркального отображения (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)

-   [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)

Для проверки конфигурации можно использовать описанные ниже действия.

1.  Запуск сеанса зеркального отображения Microsoft SQL Server.

2.  Выберите пункт **отработка отказа** , чтобы назначить новый основной экземпляр Microsoft SQL Server.

3.  Убедитесь, что сервер управления App-V 5,1 продолжает работать надлежащим образом после перехода на другой ресурс.

Строку подключения на сервере управления можно изменить, чтобы включить резервный **партнер = &lt; Server2 &gt; **. Это поможет вам только в том случае, если на сервере-источнике произошел сбой с дополнительным подключением, а на компьютере, на котором запущен клиент App – V 5,1, установлено новое соединение (скажем, после перезагрузки).

Выполните следующие действия, чтобы изменить строку подключения для включения резервного **партнера = &lt; Server2 &gt; **:

**Важно!**  В этой статье описано, как изменить реестр Windows с помощью редактора реестра. Если изменить реестр Windows некорректно, это может привести к серьезным неполадкам, которые могут потребовать повторной установки Windows. Перед изменением реестра необходимо создать резервную копию файлов реестра (System. dat и User. dat). Корпорация Майкрософт не несет ответственности за то, что проблемы, которые могут возникнуть при изменении реестра, могут быть устранены. Изменение реестра на свой страх и риск.

 

1.  Войдите на сервер управления и откройте **редактор реестра Regedit**.

2.  Перейдите в раздел **hKey \ _LOCAL \ _MACHINE**  \\  **программного обеспечения**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**.

3.  Измените значение **управления _SQL \ _CONNECTION \ _STRING** с помощью резервного **партнера = &lt; Server2 &gt; **.

4.  Перезапустите службу управления с помощью консоли IIS.

    **Примечание**  Зеркальное отображение базы данных — это список устаревших функций ядра СУБД для Microsoft SQL Server2012 из-за возможности **AlwaysOn** , доступной в Microsoft sql Server 2012.

     

Чтобы получить дополнительные сведения, щелкните одну из следующих ссылок:

-   [Инструкции: Подготовка зеркальной базы данных для зеркального отображения (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=394235) ( https://go.microsoft.com/fwlink/?LinkId=394235) .

-   [Инструкции: Настройка сеанса зеркального отображения базы данных (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) ( https://go.microsoft.com/fwlink/?LinkId=394236) .

-   [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) ( https://go.microsoft.com/fwlink/?LinkId=394237) .

-   [Устаревшие функции ядра СУБД в SQL server 2012](https://go.microsoft.com/fwlink/?LinkId=394238) ( https://go.microsoft.com/fwlink/?LinkId=394238) .

## <a href="" id="bkmk-sqlalwayson"></a>Поддержка в конфигурации Microsoft SQL Server всегда включена


База данных сервера управления App-V 5,1 поддерживает развертывание на компьютерах с операционной системой Microsoft SQL Server с **постоянной** конфигурацией.






## Статьи по теме


[Планирование развертывания App-V](planning-to-deploy-app-v51.md)

 

 





