---
title: Режим изолированной работы
description: Режим изолированной работы
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821622"
---
# Режим изолированной работы


Параметры режима разъединенных операций: доступ, щелкнув правой кнопкой мыши узел **Application Virtualization** , выбрав пункт **свойства**и нажав на вкладку **Подключение** , можно использовать клиент или клиент для служб удаленных рабочих столов Application Virtualization (ранее — службы терминалов) для запуска приложений, которые хранятся в кэше файловой системы клиента, когда клиент не может подключиться к серверу управления виртуализации приложений.

Причины сбоя при подключении к серверу: отказ сервера, отключение от сети или соединение с сетью. При возникновении сбоя клиент автоматически переключается на отключенную операцию. Если после отключения клиента требуется добавить дополнительные данные с сервера, чтобы продолжить выполнение приложения, а также в случае истечения времени ожидания отключенной операции, клиент попытается повторно подключиться к серверу. Если при попытке подключения происходит сбой, приложение будет закрыто.

По умолчанию отключенная операция включена, а время ожидания — 90 дней. Значение времени ожидания задается как количество дней, в которых вы хотите ограничить режим работы в режиме ожидания с подключением, и вы можете ввести значение от 1 до 999.

## Статьи по теме


[Отключение или изменение параметров режима изолированной работы](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





