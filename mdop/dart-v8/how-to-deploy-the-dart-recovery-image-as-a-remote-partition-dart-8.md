---
title: Развертывание образа для восстановления DaRT в качестве удаленного раздела
description: Развертывание образа для восстановления DaRT в качестве удаленного раздела
author: dansimp
ms.assetid: 58f4a6c6-6193-42bd-a095-0de868711af9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e9a6e3a9dc25139210ae22ba767da984e9a7b86d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821269"
---
# Развертывание образа для восстановления DaRT в качестве удаленного раздела


После того как вы закончите работу мастера создания образа восстановления для Microsoft Diagnostics и восстановления (DaRT) 8,0 и создали образ восстановления, вы можете извлечь файл Boot. wim из файла образа ISO и развернуть его как удаленную секцию в сети.

**Развертывание DaRT 8,0 как удаленной секции**

1.  Извлеките файл Boot. wim из файла образа DaRT ISO.

    1.  Подключите файл образа ISO, созданный в диалоговом окне **Создание образа запуска** , с помощью предпочтительного способа подключения образа.

    2.  Откройте файл образа ISO и скопируйте файл Boot. wim из папки \\sources на подключенном образе в расположение на вашем компьютере или на внешнем диске.

        **Примечание**  Если вы загрузили CD или DVD-диск в образ восстановления, вы можете открыть файлы на компакт-диске или DVD-диске и скопировать файл Boot. wim из папки \\sources. Это позволяет пропустить необходимость монтировать образ.

         

2.  Развертывание файла Boot. wim на сервере WDS, доступ к которому можно получить с компьютеров конечных пользователей на предприятии.

3.  Настройте WDS-сервер для использования файла Boot. wim для DaRT, следуя стандартным процедурам развертывания WDS.

Дополнительные сведения о том, как развернуть DaRT как удаленную секцию, можно найти в разделе [Пошаговое руководство: развертывание образа с помощью PXE](https://go.microsoft.com/fwlink/?LinkId=212108) и [руководства по началу работы служб развертывания Windows](https://go.microsoft.com/fwlink/?LinkId=212106).

## Статьи по теме


[Создание образа для восстановления DaRT 8.0](creating-the-dart-80-recovery-image-dart-8.md)

[Развертывание образа для восстановления DaRT](deploying-the-dart-recovery-image-dart-8.md)

[Планирование для DaRT 8.0](planning-for-dart-80-dart-8.md)

 

 





