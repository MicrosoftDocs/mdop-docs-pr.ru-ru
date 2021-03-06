---
title: Развертывание образа для восстановления DaRT в качестве части раздела восстановления
description: Развертывание образа для восстановления DaRT в качестве части раздела восстановления
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823559"
---
# Развертывание образа для восстановления DaRT в качестве части раздела восстановления


После завершения работы мастера изображений для восстановления DaRT и создания образа восстановления вы можете извлечь файл Boot. wim из файла образа ISO и развернуть его как раздел восстановления в образе Windows 7.

**Развертывание DaRT в разделе восстановления образа Windows 7**

1.  Создайте конечную секцию в том формате Windows 7, которая больше или равна размеру файла образа ISO, созданного с помощью **мастера подготовки изображений для восстановления**.

    Минимальный размер, необходимый для раздела DaRT, составляет примерно 300MB. Тем не менее, мы рекомендуем 450MB, чтобы они соответствовали возможностям удаленного подключения для DaRT.

2.  Извлеките файл Boot. wim из файла образа DaRT ISO.

    1.  Подключите файл образа ISO, созданный в диалоговом окне **Создание образа запуска** , с помощью предпочтительного способа подключения образа.

    2.  Откройте файл образа ISO и скопируйте файл Boot. wim из папки \\sources на подключенном образе в расположение на вашем компьютере или на внешнем диске.

        **Примечание**  Если вы загрузили CD или DVD-диск в образ восстановления, вы можете открыть файлы на компакт-диске или DVD-диске и скопировать файл Boot. wim из папки \\sources. Это позволяет пропустить необходимость монтировать образ.

         

3.  С помощью файла Boot. wim Создайте загрузочный раздел для восстановления с помощью стандартного метода для создания собственного образа Windows RE.

    Дополнительные сведения о том, как создать или настроить раздел восстановления, можно найти [в разделе Настройка среды Windows RE](https://go.microsoft.com/fwlink/?LinkId=214222).

4.  Замените конечную секцию в образе Windows 7 на раздел восстановления.

После того как вы будете готовы к сообразу Windows 7, распространите изображение на компьютеры организации с помощью стандартного процесса развертывания образа вашей компании. Дополнительные сведения о том, как создать образ Windows 7, приведены в [статье Создание стандартного образа Windows 7: пошаговое руководство](https://go.microsoft.com/fwlink/?LinkId=212103).

Дополнительные сведения о том, как развернуть решение для восстановления для повторной установки заводского образа в случае сбоя системы, можно найти в разделе [развертывание образа восстановления системы](https://go.microsoft.com/fwlink/?LinkId=214221).

## Статьи по теме


[Развертывание образа для восстановления DaRT 7.0](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





