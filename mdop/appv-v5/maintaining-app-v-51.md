---
title: Обслуживание App-V 5.1
description: Обслуживание App-V 5.1
author: dansimp
ms.assetid: 5abd17d3-e8af-4261-b914-741ae116b0e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 431ad65507a5699358159c73eaf9f3cf0dee33b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813613"
---
# Обслуживание App-V 5.1


После того как вы закончите все необходимое планирование, а затем развернуть App-V 5,1, вы можете использовать следующие сведения для поддержки инфраструктуры App-V 5,1.

## <a href="" id="move-the-app-v-5-1-server-"></a>Перемещение сервера App-V 5,1


Сервер App-V 5,1 подключается к базе данных App-V 5,1. Следовательно, вы можете установить компонент управления на любой компьютер в сети, а затем подключить его к базе данных App-V 5,1.

[Перенос сервера App-V на другой компьютер](how-to-move-the-app-v-server-to-another-computer51.md)

## <a href="" id="determine-if-an-app-v-5-1-application-is-running-virtualized-"></a>Определение того, запущено ли приложение App-V 5,1 виртуализировано


Независимые поставщики программного обеспечения, которые хотят определить, выполняется ли виртуализация приложения с помощью App-V 5,1 или более поздней версии, должен открыть именованный объект с именем **AppVVirtual- &lt; PID &gt; ** в пространстве имен по умолчанию. Например, можно использовать интерфейс Windows API **GetCurrentProcessId ()** для получения идентификатора текущего процесса, например 4052, а затем, если именованный объект события с именем **AppVVirtual-4052** может быть успешно открыт с помощью **OpenEvent ()** в пространстве имен по умолчанию для доступа к чтению, то приложение является виртуальным. Если происходит сбой вызова **OpenEvent ()** , приложение не является виртуальным.

Кроме того, для тех, кто хочет явно виртуализировать или не виртуализировать вызовы для определенного API с помощью App-V 5,1 и более поздних версий, может использовать функции **VirtualizeCurrentThread ()** и **CurrentThreadIsVirtualized ()** , реализованные в модуле AppEntSubsystems32.dll. Это позволяет подсказкам в нижестоящих компонентах, которые не должны быть виртуализированы при вызове.






## Другие ресурсы для обслуживания App-V 5,1


[Операции, связанные с администрированием и использованием App-V 5.1](operations-for-app-v-51.md)

 

 





