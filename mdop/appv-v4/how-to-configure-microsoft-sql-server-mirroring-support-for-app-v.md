---
title: Настройка поддержки зеркального отображения Microsoft SQL Server для App-V
description: Настройка поддержки зеркального отображения Microsoft SQL Server для App-V
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817932"
---
# Настройка поддержки зеркального отображения Microsoft SQL Server для App-V


С помощью описанной ниже процедуры можно настроить среду Microsoft Application Virtualization (App-V) для использования зеркального отображения базы данных Microsoft SQL Server. Настройка зеркального отображения базы данных может помочь в сценариях аварийного восстановления и перехода на другой ресурс. App-V 4,5 SP2 поддерживает все режимы зеркального отображения базы данных, доступные в настоящее время для Microsoft SQL Server 2005 и SQL Server 2008.

**Примечание.**  
Эта процедура предназначена для администраторов, знакомых с настройкой и настройкой баз данных SQL Server и зеркальным отображением базы данных в Microsoft SQL Server и, следовательно, охватывает только определенные параметры конфигурации, уникальные для App-V.



**Настройка среды App-V для использования зеркального отображения базы данных Microsoft SQL Server**

1.  Настройте зеркальное отображение базы данных SQL Server в базе данных App-V, следуя стандартным бизнес-рекомендациям для зеркального отображения базы данных. Чтобы получить общие сведения о реализации зеркального отображения базы данных Microsoft SQL Server, воспользуйтесь следующими ссылками:

    -   **Microsoft SQL 2005**—[Настройка зеркального отображения базы данных](https://go.microsoft.com/fwlink/?LinkId=187478) (https://go.microsoft.com/fwlink/?LinkId=187478)

    -   **Microsoft SQL 2008**—[Настройка зеркального отображения базы данных](https://go.microsoft.com/fwlink/?LinkId=187477) (https://go.microsoft.com/fwlink/?LinkId=187477)

    Кроме того, вы можете найти советы и рекомендации по [обеспечению зеркального отображения баз данных и их производительности](https://go.microsoft.com/fwlink/?LinkId=190270) ( https://go.microsoft.com/fwlink/?LinkId=190270) .

2.  После настройки зеркального отображения убедитесь в том, что база данных App-V показывает состояние **(основной, синхронизированный)**, а зеркальная база данных показывает состояние **(зеркало, синхронизированное и восстановление)**. Устраните проблемы зеркального отображения, прежде чем переходить к следующему шагу. Дополнительные сведения о наблюдении за состоянием можно найти в разделе [наблюдение за состоянием зеркального отображения](https://go.microsoft.com/fwlink/?LinkId=190279) ( https://go.microsoft.com/fwlink/?LinkId=190279) .

3.  На компьютере SQL Server с зеркалом базы данных App-v создайте имя пользователя SQL Server для учетной записи сетевой службы сервера управления App-v с помощью имени учетной записи ** &lt; domain &gt; \\ &lt; ManagementServerHostName &gt; $ **.

4.  Установите Microsoft SQL Server Native Client на сервере App-V Management Server и на компьютере с веб-службой управления App-V, установленном на другом компьютере. Если вы планируете подключить дополнительные серверы управления App-V к зеркальной базе данных SQL для балансировки нагрузки, необходимо также установить клиент Microsoft SQL Server Native на этих компьютерах. Вы можете скачать собственный клиент Microsoft SQL Server на веб-странице Microsoft [SQL server 2008 с пакетом дополнительных компонентов](https://go.microsoft.com/fwlink/?LinkId=187479) в центре загрузки Майкрософт ( https://go.microsoft.com/fwlink/?LinkId=187479) .

5.  Проверьте раздел **hKey \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlservername** и убедитесь, что он включает только имя узла сервера SQL Server. Если он содержит имя экземпляра (например, *serverhostname\\instancename*), его имя должно быть удалено.

    **Важно.**  
    Сервер управления App-V использует сетевую библиотеку TCP/IP для связи с SQL Server при включенном зеркальном отображении базы данных, поэтому имена экземпляров использовать нельзя. Вместо этого номера портов должны быть указаны в разделах реестра.



6.  Проверьте раздел **hKey \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlserverport** и убедитесь, что он содержит номер порта, который используется для SQL на компьютере SQL Server. Если вы используете именованный экземпляр, это значение ключа должно быть задано для порта, используемого для именованного экземпляра.

7.  Создайте раздел реестра **hKey \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverservername** AS REG \ _SZ и укажите в качестве значения имя узла сервера SQL Server, на котором размещается зеркало.

8.  Создайте раздел реестра **hKey \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverserverport** как DWORD и укажите номер порта, который будет использоваться для SQL на компьютере, на котором запущен SQL Server, для размещения зеркала. Если вы используете именованный экземпляр для зеркала, это значение ключа должно быть задано на номер порта, который используется для именованного экземпляра.

9.  На компьютере, на котором работает веб-служба управления App-V, настройте текстовый файл универсальной связи с данными (UDL). В каталоге, где установлено приложение App-V, дважды щелкните **SftMgmt. udl** и укажите следующие значения:

    -   На вкладке **поставщик** выберите поставщик OLE DB **Native Client 10,0 клиента SQL Server**.

    -   Нажмите кнопку **Далее** , чтобы выбрать вкладку **Подключение** . В поле **имя сервера** введите имя сервера SQL Server. Затем выберите **использовать встроенную безопасность Windows NT**. Наконец, щелкните список, **выберите базу данных**и укажите имя базы данных App-V.

    -   Откройте вкладку **все** , а затем выберите участника, на котором будет находиться **отказ**при входе. Нажмите кнопку **изменить значение**, а затем введите имя сервера SQL Server, на котором будет отработка отказа. Нажмите кнопку **ОК**.

    **Важно.**  
    Система App-V использует проверку подлинности Kerberos. Таким образом, когда вы настраиваете зеркальное отображение SQL, в котором включена проверка подлинности Kerberos на сервере SQL Server и служба SQL Server работает под учетной записью пользователя домена, необходимо вручную настроить SPN. Дополнительные сведения можно найти в разделе "когда служба SQL использует учетные записи на основе доменов" в статье [Настройка администрирования App-V для распределенной среды](https://go.microsoft.com/fwlink/?LinkId=203186) ( https://go.microsoft.com/fwlink/?LinkId=203186) .



10. Чтобы убедиться в том, что зеркальное отображение базы данных работает правильно, проверьте переход на другой ресурс и убедитесь, что сервер управления App-V продолжает работать правильно.

    **Важно.**  
    Будьте внимательны и проследите за вашими стандартными бизнес-рекомендациями, чтобы убедиться в том, что в случае сбоя система не будет прервана.



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## Статьи по теме


[Выполнение задач администрирования на консоли управления серверами Application Virtualization](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









