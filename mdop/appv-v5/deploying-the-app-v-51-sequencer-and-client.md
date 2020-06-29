---
title: Развертывание Sequencer и клиента App-V 5.1
description: Развертывание Sequencer и клиента App-V 5.1
author: dansimp
ms.assetid: 74f32794-4c76-436f-a542-f9e95d89063d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3b78059e5005f563bb99d7e6f4b5fe0af2eae8d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814568"
---
# Развертывание Sequencer и клиента App-V 5.1


Microsoft Application Virtualization (App-V) 5,1 Sequencer и клиент позволяет администраторам виртуализировать и запускать виртуализированные приложения.

## Развертывание клиента


Клиент App-V 5,1 является компонентом, который запускает виртуализированное приложение на целевом компьютере. Клиент позволяет пользователям взаимодействовать со значками и дважды щелкать типы файлов, чтобы они могли запускать виртуализированное приложение. Клиент также может получить содержимое виртуального приложения с сервера управления.

[Развертывание клиента App-V](how-to-deploy-the-app-v-client-51gb18030.md)

[Удаление клиента App-V 5.1](how-to-uninstall-the-app-v-51-client.md)

[Развертывание приложения App-V 4,6 и клиента App-V 5,1 на том же компьютере](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

## Параметры конфигурации клиента


Клиент App-V 5,1 хранит свою конфигурацию в реестре. Вы можете собрать полезные сведения о клиенте, если вы понимаете формат данных в реестре. Вы также можете настроить множество клиентских действий, изменяя записи в реестре.

[Сведения о параметрах конфигурации клиента](about-client-configuration-settings51.md)

## Настройка клиента с помощью шаблона ADMX и групповой политики


Вы можете использовать шаблон Microsoft ADMX для настройки клиентских параметров для клиента App-V 5,1 и клиента служб удаленных рабочих столов. Шаблон ADMX управляет распространенными конфигурациями клиентов с помощью существующей инфраструктуры групповой политики, которая включает параметры конфигурации клиента App-V 5,1.

**Важно!**  Вы можете получить шаблон App-V 5,1 ADMX из центра загрузки Майкрософт.

 

После скачивания и установки шаблона ADMX выполните указанные ниже действия на компьютере, который будет использоваться для управления групповой политикой. Обычно это контроллер домена.

1.  Сохраните **ADMX** файл в следующем каталоге: **Windows \ \ PolicyDefinitions**

2.  Сохраните файл **ADML** в следующей папке: **каталог Windows \ \ PolicyDefinitions \ \ &lt; Справочник &gt; по языку**

После выполнения описанных выше действий вы можете управлять параметрами конфигурации клиента App-V 5,1 с помощью консоли **управления групповыми политиками** .

Клиент App-V 5,1 также хранит конфигурацию в реестре. Вы можете собрать полезные сведения о клиенте, если вы понимаете формат данных в реестре. Вы также можете настроить множество клиентских действий, изменяя записи в реестре.

[Изменение конфигурации клиента App-V 5.1 с помощью шаблона ADMX и групповой политики](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

## Развертывание клиента с помощью режима хранилища общего содержимого


Режим хранилища общего содержимого (SCS) App-V 5,1 позволяет клиентам SCS App-V 5,1 запускать виртуализированные приложения, не сохраняя никакие связанные данные пакета локально. Все необходимые виртуализированные данные пакета передаются по сети; Поэтому режим SCS следует использовать только в средах с быстрым подключением. Службы удаленных рабочих столов (RDS) и стандартная версия клиента App-V 5,1 поддерживаются в режиме SCS.

**Важно!**  Если клиент App-V 5,1 настроен для работы в режиме SCS, то расположение, в котором передаются пакеты приложения App-V 5,1, должно быть доступно, в противном случае виртуализированный пакет завершится сбоем. Кроме того, мы не рекомендуем развертывать виртуализированные приложения на компьютерах, на которых запущен клиент App-V 5,1 в режиме SCS через Интернет.

 

Кроме того, SCS не является физическим расположением, которое содержит виртуализированные пакеты. Это режим, позволяющий клиенту App-V 5,1 передавать необходимые виртуализованные данные пакета по сети.

Режим SCS полезен в следующих сценариях:

-   Развертывание инфраструктуры виртуальных рабочих столов (VDI)

-   Развертывания служб удаленных рабочих столов (RDS)

Чтобы использовать SCS в своей среде, необходимо включить клиент App-V 5,1 в режиме SCS. Этот параметр должен быть указан во время установки. По умолчанию клиент не настроен на использование режима SCS. Если вы планируете использовать SCS, вы должны установить клиент с помощью предлагаемой процедуры. Однако вы можете настроить существующий клиент App-V 5,1 для работы в режиме SCS, введя следующую команду PowerShell на компьютере, на котором запущен клиент App-V 5,1:

**Set-AppvClientConfiguration-SharedContentStoreMode 1**

Могут возникнуть ситуации, когда администратор выполняет предварительную загрузку некоторых виртуальных приложений на компьютере, на котором запущен клиент App-V 5,1 в режиме SCS. Это можно сделать с помощью команд PowerShell, чтобы добавить, опубликовать и подключить пакет. Например, если пакет предварительно загружен на все компьютеры, администратор может добавить, опубликовать и подключить пакет с помощью команд PowerShell. Пакет не помещается в поток по сети, так как он будет храниться локально.

[Установка клиента App-V 5.1 для режима хранилища общего содержимого](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

## Развертывание секвенсора


Секвенсор — это инструмент, который используется для преобразования стандартных приложений в виртуальные пакеты для развертывания на компьютеры, на которых запущен клиент App-V 5,1. Секвенсор помогает обеспечить простой и предсказуемый процесс преобразования с минимальными изменениями в предыдущих рабочих процессах последовательности. Кроме того, секвенсор позволяет пользователям более легко настраивать приложения, чтобы обеспечить подключение виртуализованных приложений.

Список изменений в секвенсоре App-V 5,1 можно найти в разделе [о приложении App-v 5,1](about-app-v-51.md).

[Установка программы Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)

## <a href="" id="---------app-v-5-1-client-and-sequencer-logs"></a> Журналы клиентского и секвенсора App-V 5,1


Данные журнала секвенсора App-V 5,1 можно использовать для устранения неполадок, связанных с установкой и функционированием секвенсора, при использовании App-V 5,1. Данные журнала, связанные с секвенсором, можно просмотреть в **средстве просмотра событий**. В следующей строке показан определенный путь для событий, связанных с секвенсором:

**Окно просмотра событий \ \ журналы приложений и служб \ \ Microsoft \ \ приложение V**. События, связанные с секвенсором, добавляются в начале с помощью службы **AppV \ _Sequencer**. События, связанные с клиентами, добавляются в начале с помощью службы **AppV \ _Client**.

## Другие ресурсы для развертывания секвенсора и клиента


[Развертывание App-V 5.1](deploying-app-v-51.md)

[Планирование использования App-V 5.1](planning-for-app-v-51.md)






 

 




