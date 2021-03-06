---
title: Открытие виртуализированного приложения с помощью командной строки
description: Открытие виртуализированного приложения с помощью командной строки
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816919"
---
# Открытие виртуализированного приложения с помощью командной строки


Вы можете открыть пакеты виртуальных приложений с помощью командной строки. Вы должны запустить командную запись **cmd** в качестве администратора.

Чтобы открыть последовательные пакеты приложений с помощью командной строки, выполните указанные ниже действия.

**Открытие последовательного приложения с помощью командной строки**

1.  Чтобы открыть командную команду, нажмите кнопку **Пуск**и выберите команду **выполнить**, введите **cmd**и нажмите кнопку **ОК**.

2.  В командной строке введите **cd\\** и укажите путь к каталогу, в котором установлен секвенсор, и нажмите клавишу **ВВОД.**

3.  В командной строке введите следующую команду, заменив текст курсивом на значения:

    SFTSequencer/OPEN:*"указывает файл SPRJ, который нужно открыть"*

    Нажмите клавишу **Ввод**.

4.  Вы также можете указать следующие необязательные параметры. В командной строке введите следующие команды, заменив курсивный текст на нужные значения:

    /PACKAGENAME: "*указывает имя пакета"*

    /MSI-указывает на создание связанного установщика Microsoft Windows.

    /COMPRESS — указывает, будет ли пакет сжиматься. По умолчанию пакеты не сжимаются.

    Нажмите клавишу **Ввод**.

    **Примечание**  Если установщик или пакет установщика Windows имеет графический интерфейс пользователя, он будет отображаться после того, как вы задаете параметры командной строки.

     

## Статьи по теме


[Управление виртуальными приложениями с помощью командной строки](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





