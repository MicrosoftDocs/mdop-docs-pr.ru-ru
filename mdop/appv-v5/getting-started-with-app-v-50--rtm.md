---
title: Начало работы с App-V 5.0
description: Начало работы с App-V 5.0
author: dansimp
ms.assetid: 3e16eafb-ce95-4d06-b214-fe0f4b1b495f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7979c81b7b57107f824b96d9fef8049a00c5b08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814552"
---
# Начало работы с App-V 5.0


Приложение App-V 5,0 позволяет администраторам развертывать, обновлять и поддерживать приложения в виде служб в реальном времени, по мере необходимости. Отдельные приложения преобразуются из локально установленных продуктов в централизованно управляемые службы и доступны там, где это необходимо, без необходимости предварительной настройки компьютеров и изменения параметров операционной системы.

App-V состоит из следующих элементов:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Элемент</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Сервер управления App-V</p></td>
<td align="left"><ul>
<li><p>Предоставляет центральное расположение для управления инфраструктурой App-V, которое предоставляет виртуальные приложения для клиентского компьютера App-V и служб удаленных рабочих столов (ранее — служб терминалов).</p></li>
<li><p>Использует Microsoft SQL Server® для хранилища данных, где один или несколько серверов управления App-V могут совместно использовать одно хранилище данных SQL Server.</p></li>
<li><p>Выполняет проверку подлинности запросов и обеспечивает безопасность, измерения, мониторинг и сбор данных. Для управления пользователями и приложениями на сервере используются службы Active Directory и поддерживаемые инструменты.</p></li>
<li><p>У вас есть веб-сайт управления® Silverlight, с помощью которого можно настроить инфраструктуру App-V на любом компьютере. Вы можете добавлять и удалять приложения, управлять сочетаниями клавиш, назначать разрешения на доступ пользователям и группам, а также создавать группы подключений.</p></li>
<li><p>Обеспечивает связь между консолью управления веб-приложением App-V и хранилищем данных SQL Server. Эти компоненты могут быть установлены на одном сервере или на одном или нескольких отдельных компьютерах в зависимости от требуемой системной архитектуры.</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Сервер публикаций App-V</p></td>
<td align="left"><ul>
<li><p>Предоставляет клиентам App-V приложения с лицензионными данными для определенного пользователя</p></li>
<li><p>Размещает виртуальный пакет приложения для потоковой передачи.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>Классическое приложение App-V</p></td>
<td align="left"><ul>
<li><p>Получение виртуальных приложений</p></li>
<li><p>Публикация приложений на клиентах</p></li>
<li><p>Автоматическая настройка виртуальных сред во время выполнения для конечных точек Windows и управление ими.</p></li>
<li><p>Сохраняются пользовательские параметры виртуальных приложений, такие как реестр и изменения файлов, в каждом пользовательском профиле&#39;s.</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Клиент служб удаленных рабочих столов (RDS) для App-V</p></td>
<td align="left"><p>Позволяет серверам узлов сеансов удаленных рабочих столов использовать возможности настольного клиента App-V для общих сеансов рабочего стола.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Секвенсор App-V</p></td>
<td align="left"><ul>
<li><p>— Это средство на основе мастера, которое используется для преобразования традиционных приложений в виртуальные приложения.</p></li>
<li><p>Создает пакет приложения, который состоит из следующих элементов:</p>
<ol>
<li><p>файл последовательного приложения (APPV)</p></li>
<li><p>файл установщика Windows (MSI), который может быть развернут на клиентах, настроенных для изолированной операции</p></li>
<li><p>Несколько XML-файлов, в том числе Report.XML, PackageName_DeploymentConfig.XML и PackageName_UserConfig.XML. XML-файлы UserConfig и DeploymentConfig используются для настройки изменения поведения пакета по умолчанию.</p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

Дополнительные сведения об этих элементах можно найти в разделе [архитектура высшего уровня для App-V 5,0](high-level-architecture-for-app-v-50.md).

Если вы не знакомы с этим продуктом, рекомендуем вам внимательно ознакомиться с документацией. Перед развертыванием в рабочей среде мы также рекомендуем проверить план развертывания в среде тестовой сети. Вы также можете воспользоваться классом, чтобы узнать о необходимых технологиях. Дополнительные сведения о возможностях обучения Microsoft можно найти в разделе Общие сведения о Microsoft Training <https://go.microsoft.com/fwlink/p/?LinkId=80347> .

**Примечание**  Недоступна загружаемая версия руководства администратора. Тем не менее, вы можете узнать о специальных режимах библиотеки TechNet, где можно выбрать статьи, сгруппировать их в коллекцию, распечатать или экспортировать в файл по адресу <https://go.microsoft.com/fwlink/?LinkId=272491> ( https://go.microsoft.com/fwlink/?LinkId=272491) .

 

Этот раздел руководства администратора App-V 5,0 содержит подробные сведения о приложении App-V 5,0, которые помогут вам понять, как ознакомиться с продуктом, прежде чем приступить к планированию развертывания.

## Начало работы с приложением-V 5,0


-   [Сведения о App-V 5.0](about-app-v-50.md)

    В этой статье приведены общие сведения о приложении App-V 5,0 и его использовании в Организации.

-   [Сведения о App-V 5.0 с пакетом обновления 1 (SP1)](about-app-v-50-sp1.md)

    Высокоуровневый обзор App-V 5.0 SP1 и его использования в вашей организации.

-   [Сведения об App-V 5.0 с пакетом обновления 2 (SP2)](about-app-v-50-sp2.md)

    Общий обзор приложения App-V 5.0 SP2 и его использование в Организации.

-   [Сведения об App-V 5.0 с пакетом обновления 3 (SP3)](about-app-v-50-sp3.md)

    Общий обзор приложения App-V 5.0 SP2 и его использование в Организации.

-   [Оценка App-V 5.0](evaluating-app-v-50.md)

    Сведения о том, как наилучшим образом оценить приложение App-V 5,0 для использования в вашей организации.

-   [Высокоуровневая архитектура App-V 5.0](high-level-architecture-for-app-v-50.md)

    Содержит описание функций App-V 5,0 и их взаимодействия друг с другом.

-   [Специальные возможности для App-V 5.0](accessibility-for-app-v-50.md)

    Сведения о функциях и службах, которые делают этот продукт и соответствующую документацию более удобной для людей с ограниченными возможностями.

## <a href="" id="other-resources-for-this-product-"></a>Другие ресурсы для этого продукта


-   [Руководство администратора Microsoft Application Virtualization 5,0](microsoft-application-virtualization-50-administrators-guide.md)

-   [Планирование использования App-V 5.0](planning-for-app-v-50-rc.md)

-   [Развертывание App-V 5.0](deploying-app-v-50.md)

-   [Операции, связанные с администрированием и использованием App-V 5.0](operations-for-app-v-50.md)

-   [Устранение неполадок в App-V 5.0](troubleshooting-app-v-50.md)






 

 





