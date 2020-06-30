---
title: Создание отчетов MBAM
description: Создание отчетов MBAM
author: dansimp
ms.assetid: 083550cb-8c3f-49b3-a30e-97d85374d2f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ccdc1a2cd69d8cc2e2c2823827f5ea43ad867a78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824092"
---
# Создание отчетов MBAM


При установке системы администрирования и мониторинга Microsoft BitLocker (MBAM) с изолированной топологией вы можете создавать различные отчеты, чтобы отслеживать использование шифрования BitLocker и их соответствие требованиям. В этой статье описаны действия, которые необходимо выполнить, чтобы открыть веб-сайт администрирования и наблюдения и шаги, необходимые для создания администраторов Microsoft BitLocker и наблюдения за отчетами о соответствии требованиям в масштабах предприятия, отдельных компьютерах и действиях по восстановлению ключей. Подробные сведения, помогающие понять MBAM отчеты, можно найти в разделе [Основные сведения о MBAM отчетах](understanding-mbam-reports-mbam-2.md).

**Примечание**  Для запуска отчетов необходимо быть участником **роли пользователи отчета** на компьютерах, на которых установлены функции администрирования и мониторинга сервера, база данных соответствия требованиям и аудита, а также отчеты о соответствии требованиям и аудите.

 

**Открытие веб-сайта администрирования и мониторинга**

1.  Откройте веб-браузер и перейдите на веб-сайт администрирования и мониторинга. URL-адресом по умолчанию для веб-сайта администрирования и мониторинга является *http:// &lt; имя_компьютера &gt; *.

    **Примечание**  Если веб-сайт theAdministration и мониторинг установлены на порте, отличном от 80, необходимо указать порт в URL-адресе (например, *http:// &lt; имя_компьютера &gt; : &lt; порт &gt; *. Если вы указали имя узла для theAdministration и веб-сайта мониторинга во время установки, URL-адрес будет *http:// &lt; именем узла &gt; *.

     

2.  В левой области выберите пункт **отчеты** , а затем выберите отчет, который нужно выполнить, в верхней строке меню.

    Исторические данные клиента MBAM хранятся в базе данных соответствия требованиям для исторических ссылок в случае потери или кражи компьютера. При работе с корпоративными отчетами мы рекомендуем использовать соответствующие даты начала и окончания, чтобы определить временные интервалы для отчетов в отчете от одной до двух недель, чтобы улучшить отчет о точности данных.

    **Примечание**  Если служба SSRS не настроена на использование Secure Socket Layer, то при установке сервера MBAM URL-адрес для отчетов будет установлен в значение HTTP вместо HTTPS. Если затем перейти на портал службы поддержки и выбрать отчет, появится следующее сообщение: "только безопасное содержимое отображается". Чтобы отобразить отчет, выберите пункт **Показать весь контент**.

     

**Создание отчета о соответствии требованиям предприятия**

1.  На веб-сайте администрирования и мониторинга выберите узел **отчеты** в области навигации слева, выберите **отчет о корпоративном соответствии**и выберите Фильтры, которые вы хотите использовать. Ниже указаны доступные фильтры для отчета о соответствии требованиям предприятия.

    -   **Состояние соответствия требованиям**. Используйте этот фильтр, чтобы указать типы состояния соответствия (например, соответствие требованиям или несоответствующие требованиям) отчета.

    -   **Состояние ошибки**. Используйте этот фильтр, чтобы указать типы состояния ошибки (например, нет ошибки или ошибки) отчета.

2.  Нажмите кнопку **Просмотр отчета** , чтобы отобразить выбранный отчет.

    Результаты можно сохранять в разных форматах, таких как HTML, Microsoft Word и Microsoft Excel.

    **Примечание**  Отчет о соответствии требованиям предприятия создается заданием SQL, которое выполняется каждые шесть часов. Таким образом, при первом просмотре отчета могут возникнуть недостающие данные. Вы можете создавать обновленные данные отчета вручную с помощью SQL Management Studio. В окне **обозревателя объектов** разверните узел **Агент SQL Server**, разверните **задания**, щелкните правой кнопкой мыши задание **CreateCache** и выберите команду **начать задание на шаге....**

     

3.  Выберите имя компьютера, чтобы просмотреть сведения о нем в отчете о соответствии компьютера.

4.  Щелкните знак "плюс" (+) рядом с именем компьютера, чтобы просмотреть сведения о томах на компьютере.

**Создание отчета о соответствии компьютера**

1.  На веб-сайте администрирования и мониторинга выберите узел **отчета** в области навигации слева, а затем выберите **отчет о соответствии компьютера**. Используйте отчет о соответствии компьютера для поиска **имени пользователя** или **имени компьютера**.

2.  Нажмите кнопку **Просмотр отчета** , чтобы просмотреть отчет о компьютере.

    Результаты можно сохранять в разных форматах, таких как HTML, Microsoft Word и Microsoft Excel.

3.  Выберите имя компьютера, чтобы просмотреть дополнительные сведения о нем в отчете о соответствии компьютера.

4.  Щелкните знак "плюс" (+) рядом с именем компьютера, чтобы просмотреть сведения о томах на компьютере.

    **Примечание**  Клиентский компьютер MBAM считается совместимым, если компьютер соответствует требованиям, предъявляемым параметрами политики MBAM.

     

**Создание отчета об аудите ключа восстановления**

1.  На веб-сайте администрирования и мониторинга выберите узел **отчета** в области навигации слева, а затем выберите **отчет аудит восстановления**. Выберите Фильтры для отчета об аудите ключа восстановления. Ниже приведены доступные фильтры для аудита ключей восстановления.

    -   **Инициатор запроса**. С помощью этого фильтра пользователи смогут указать имя пользователя, который является инициатором запроса. Автор запроса — это человек в службе поддержки, который получил доступ к ключу от имени пользователя.

    -   **Инициатор запроса**. С помощью этого фильтра пользователи смогут указать имя пользователя, который является инициатором запроса. Автор запроса — это человек, который позвонил в службу поддержки, чтобы получить ключ восстановления.

    -   **Результат запроса**. Этот фильтр позволяет пользователям указывать типы результатов запросов (например, успех или неудача), на основе которых будет основываться отчет. Например, пользователи могут захочет просмотреть попытки доступа к Key с ошибками.

    -   **Тип ключа**. Этот фильтр позволяет пользователям указывать тип ключа (например, пароль ключа восстановления или хэш пароля доверенного платформенного модуля), для которого требуется создать отчет.

    -   **Дата начала**. Этот фильтр используется для определения части даты начала диапазона дат, о котором пользователь хочет сообщить.

    -   **Дата окончания**. Этот фильтр используется для определения части даты окончания диапазона дат, о котором вы хотите сообщить пользователям.

2.  Нажмите кнопку **Просмотр отчета** , чтобы просмотреть отчет.

    Результаты можно сохранять в разных форматах, таких как HTML, Microsoft Word и Microsoft Excel.

## Статьи по теме


[Мониторинг и создание отчетов по соответствию BitLocker с помощью MBAM 2.0](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 




