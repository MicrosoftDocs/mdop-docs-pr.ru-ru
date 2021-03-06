---
title: Сведения об App-V 5.0 с пакетом обновления 2 (SP2)
description: Сведения об App-V 5.0 с пакетом обновления 2 (SP2)
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814989"
---
# Сведения об App-V 5.0 с пакетом обновления 2 (SP2)


App-V 5.0 SP2 обеспечивает улучшенную интегрированную платформу, более гибкую виртуализацию и мощное управление виртуализованными приложениями. Дополнительные сведения можно найти в [обзоре App-V 5,0](https://go.microsoft.com/fwlink/p/?LinkId=325265) ( https://go.microsoft.com/fwlink/?LinkId=325265) .

## Изменения в стандартных функциях App-V 5.0 с пакетом обновления 2 (SP2)


В следующих разделах содержатся сведения об изменениях в стандартных функциях для App-V 5.0 SP2.

### <a href="" id="bkmk-sp2-supported-cfg"></a>Поддержка Windows Server 2012 R2 и Windows 8,1

Приложение App-V 5,0 включает поддержку для Windows Server 2012 R2 и Windows 8,1

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> Приложение App-V 5.0 SP2 теперь поддерживает перенаправление папок для перемещаемой папки AppData пользователя.

App-V 5.0 SP2 поддерживает перемещаемую AppData (% AppData%) Перенаправление папок. Дополнительные сведения можно найти в разделе [планирование использования перенаправления папок с приложением App-V](planning-to-use-folder-redirection-with-app-v.md).

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a>Улучшенные возможности обновления пакетов и ожидающие задачи

В App-V 5.0 SP2 больше не будет предлагаться закрыть запущенное виртуальное приложение при публикации более новой версии пакета или группы подключения. Если при попытке выполнить связанную задачу используется пакет или группа соединения, появится сообщение, показывающее, что объект используется, и что операция будет выполнена позже.

Задачи, которые были помещены в состояние ожидания, выполняются в соответствии с приведенными ниже правилами.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Тип задачи</th>
<th align="left">Применимое правило</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Пользовательская задача, например Публикация пакета для пользователя</p></td>
<td align="left"><p>Задача будет выполнена после того, как пользователь войдет в систему, а затем снова войдите в нее.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Глобально на основе задач, например включение глобальной группы подключения</p></td>
<td align="left"><p>Задача, ожидающая выполнения, будет выполнена после отключения компьютера и повторного запуска.</p></td>
</tr>
</tbody>
</table>

 

Когда задача размещается в состоянии ожидания, клиент App-V также создает раздел реестра для задачи с отложенным вводом, как описано ниже.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Задача на основе пользователей или глобально</th>
<th align="left">Где создается раздел реестра</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Пользовательские задачи</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>Глобально на основе задач</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

### Виртуализация Microsoft Office 2013 и Microsoft Office 2010 с помощью App-V 5,0

Ниже приведены ссылки на дополнительные сведения о приложениях App-V 5,0, которые поддерживаются в сценариях Microsoft Office.

[Виртуализация Microsoft Office 2013 для Application Virtualization (App-V) 5.0](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

**Примечание**  В этом документе рассматривается создание пакета Microsoft Office 2013 App-V 5,0. Однако она также предоставляет сведения о сценариях для Microsoft Office 2010 с помощью App-V 5,0.

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> Приложение пользовательского интерфейса для управления клиентом App-V 5,0

В предыдущих версиях App-V 5,0 пользовательским интерфейсом управления клиентами предоставлена установка клиента App-V 5,0. С помощью App-V 5.0 SP2 это уже не так. Теперь у администраторов есть возможность развернуть клиентский интерфейс приложения App-V 5,0 в качестве виртуального приложения (с использованием всех поддерживаемых конфигураций развертывания App-V) или как установленное приложение.

Дополнительные сведения см. в [приложении клиентского интерфейса клиента Microsoft Application Virtualization 5,0](https://go.microsoft.com/fwlink/p/?LinkId=386345) ( https://go.microsoft.com/fwlink/?LinkId=386345) .

### Одностороннее (SxS) сборка Автоматическая упаковка и развертывание

Приложение App-V 5.0 с пакетом обновления 2 (SP2) теперь автоматически определяет параллельные сборки (SxS) и развертывание на компьютере с клиентским приложением App-V 5.0 SP2. В основном сборка SxS включает в себя зависимости VC + + времени выполнения и MSXML. В предыдущих версиях App-V виртуальные приложения, которые применяют зависимости в среде VC, требовали, чтобы эти зависимости находились локально на компьютере с клиентским приложением App-V 5.0 SP2.

Теперь поддерживаются следующие функциональные возможности:

-   Программа Sequencer App-V 5,0 автоматически захватывает сборку SxS в пакете независимо от того, установлен ли на компьютере, на котором запущено на нем, тестовый запуск VC-среды.

-   Клиент App-V 5,0 автоматически устанавливает необходимую сборку SxS на компьютер, на котором работает клиент, как требуется во время публикации.

-   В приложении App-V 5,0 Sequencer выводится зависимость VC-времени выполнения, использующая механизм отчетов Sequencer.

-   Приложение App-V 5,0 позволяет исключить зависимость времени выполнения VC в том случае, если зависимость уже доступна на компьютере, на котором запущен секвенсор.

### Улучшенные возможности обновления публикации

Приложение App-V 5,0 поддерживает несколько функций, позволяющих улучшить общее взаимодействие с обновлением набора приложений для определенного пользователя.

В списке ниже перечислены улучшения, повышающие качество обновления публикации.

В приведенном ниже списке содержатся дополнительные сведения о том, как включить новое улучшенное обновление публикации.

-   **EnablePublishingRefreshUI** — включает индикатор выполнения обновления публикации для компьютера, на котором запущен клиент App-V 5,0.

-   **HideUI** — скрывает индикатор выполнения обновления публикации во время синхронизации вручную.

### Новый параметр конфигурации клиента

Ниже перечислены новые параметры конфигурации клиента, доступные в приложении App-V 5,0 с пакетом обновления 2 (SP2).

**EnableDynamicVirtualization** — включает поддерживаемые расширения оболочки, вспомогательные объекты браузера и элементы управления ActiveX, которые должны быть виртуализированы и выполнены с виртуальными приложениями.

Дополнительные сведения можно найти в разделе [Параметры конфигурации клиента](about-client-configuration-settings.md).

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> Расширения оболочки App-V 5,0

Приложение App-V 5,0 с пакетом обновления 2 (SP2) теперь поддерживает расширения оболочки.

Дополнительные сведения содержатся в разделе **Поддержка расширений оболочки App-v 5.0 SP2** для [создания виртуализованных приложений app-v 5,0 и управления ими](creating-and-managing-app-v-50-virtualized-applications.md).

## <a href="" id="---------app-v-5-0-documentation-updates"></a> Обновления документации для App-V 5,0


Приложение App-V 5,0 SP2 содержит обновленную документацию по следующим сценариям.

-   [Перенос из предыдущей версии](migrating-from-a-previous-version-app-v-50.md)

-   [Сведения о App-V 5.0](about-app-v-50.md)

-   [Сведения об отчетах App-V 5,0](about-app-v-50-reporting.md) (раздел "часто задаваемые вопросы")

## Получение технологий для MDOP


Приложение App-V 5,0 является частью пакета оптимизации рабочей среды Майкрософт (MDOP). MDOP входит в состав Microsoft Software Assurance. Дополнительные сведения о программе Software Assurance и приобретении MDOP можно найти в [статьях получение MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) ( https://go.microsoft.com/fwlink/?LinkId=322049) .






## Статьи по теме


[Заметки о выпуске для App-V 5.0 с пакетом обновления 2 (SP2)](release-notes-for-app-v-50-sp2.md)

 

 





