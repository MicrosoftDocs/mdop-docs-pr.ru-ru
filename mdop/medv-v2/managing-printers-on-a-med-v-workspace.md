---
title: Управление принтерами в рабочей области MED-V
description: Управление принтерами в рабочей области MED-V
author: dansimp
ms.assetid: ba0a65ad-444f-4d18-95eb-8b9fa1a3ffba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bc7a62075c95e8816a425eff89ffb992f1185d04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826119"
---
# Управление принтерами в рабочей области MED-V


В Microsoft Enterprise Virtualization (MED-V) 2,0, перенаправление принтеров обеспечивает конечные пользователи с одинаковым интерфейсом печати между виртуальной машиной MED-V и ведущим компьютером.

В этом разделе приводятся сведения о том, как управлять печатью в рабочей области MED-V.

## Управление принтерами в рабочих областях MED-V


В большинстве случаев MED-V автоматически обрабатывает перенаправление принтера. После первого завершения настройки MED-V определяет все сетевые принтеры, установленные на узле, извлекает соответствующие драйверы с сетевого сервера печати и, если он найден, устанавливает соответствующие драйверы в рабочую область MED-V. После того как все драйверы будут найдены и установлены, MED-V перезагружает рабочую область MED-V. Только после перезапуска рабочей области MED-V принтеры узла будут представлены и доступны на гостевом компьютере (обычно через несколько минут).

**Примечание**  Если в рабочей области для MED-V запущены приложения, пользователю будет предложено выполнить перезагрузку, чтобы продолжить, или отложить ее на более поздний срок. Если приложение не запущено, перезагрузка выполняется автоматически и не отображается для конечного пользователя.

 

При каждом запуске MED-V выполняется проверка того, установлены ли на узле новые принтеры, и, если оно найдено, извлекает соответствующие драйверы с сетевого сервера печати и устанавливает их на гость. Затем MED-V перезапустит рабочую область MED-V точно так же, как при первом завершении настройки.

**Важно!**  После того как на гостевой компьютере будут установлены необходимые драйверы, принтеры станут видны только на гостевой машине после перезапуска.

 

Если вы в любой момент не можете найти или установить драйвер, его необходимо установить на гостевой машине вручную, чтобы обеспечить доступность сетевого принтера для конечного пользователя.

Ниже приведены некоторые дополнительные рекомендации.

**Только сетевые принтеры управляются с помощью MED-V**. Драйверы для принтеров, установленных локально на узле, не устанавливаются автоматически на гостевой машине.

**При обнаружении на сервере печати MED-V устанавливаются только драйверы принтера**. В противном случае драйверы принтера должны быть установлены вручную.

**Принтеры, установленные вручную на гостевом компьютере, недоступны для узла**. По умолчанию MED-V поддерживает перенаправление принтеров только от гостя на узел.

**Предупреждение**  Если принтер установлен вручную на гостевом компьютере, а этот принтер позже установлен на нем, то в результате этот принтер устанавливается дважды на гостевой машине. Чтобы избежать такой ситуации, рекомендуется управлять перенаправлением принтеров одним способом: отключите перенаправление и установите принтеры вручную на гостевой или включите перенаправление и не устанавливайте принтеры вручную на гостевой машине.

 

## Статьи по теме


[Управление параметрами рабочей области MED-V](manage-med-v-workspace-settings.md)

 

 





