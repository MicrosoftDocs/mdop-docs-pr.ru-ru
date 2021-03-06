---
title: Развертывание шаблонов расположения параметров UE-V для UE-V 1.0
description: Развертывание шаблонов расположения параметров UE-V для UE-V 1.0
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827122"
---
# Развертывание шаблонов расположения параметров UE-V для UE-V 1.0


Виртуализация взаимодействия с пользователем Microsoft (UE-V) использует шаблоны расположений параметров (XML-файлы), которые определяют параметры, зафиксированные и применяемые с помощью виртуализации взаимодействия с пользователем. UE-V включает набор стандартных шаблонов, а также средство, генератор UE-V, который позволяет создавать пользовательские шаблоны расположений параметров. После того как вы создадите шаблон расположения параметров, необходимо проверить его, чтобы убедиться в том, что параметры приложения правильно перемещены в тестовую среду. Затем вы можете безопасно развернуть шаблон расположения параметров на компьютерах в предприятии.

Шаблоны расположений параметров можно развертывать с помощью корпоративного распространения программного обеспечения (ESD), настроек групповой политики, а также путем настройки каталога шаблонов параметров UE-V. Шаблоны, развернутые с помощью ESD или групповой политики, должны быть зарегистрированы с помощью UE-V WMI или PowerShell. Шаблоны, которые хранятся в расположении каталога шаблонов параметров, автоматически регистрируются агентом UE-V.

## Развертывание шаблонов расположений параметров с помощью пути к каталогу шаблонов параметров


Путь к каталогу шаблонов расположений параметров UE-V можно определить с помощью следующих методов: групповая политика, параметры командной строки для установки агента, WMI или PowerShell. После того как вы определили путь к каталогу шаблонов, агент UE-V Agent извлекает из этого расположения новые или обновленные шаблоны. Агент UE-V проверяет это расположение один раз в день и обновляет режим синхронизации на основе шаблонов, найденных в этой папке. Шаблоны, добавленные или обновленные в этой папке с момента последней проверки регистрируются агентом UE-V. Агент UE-V также отменяет регистрацию шаблонов, которые были удалены из этой папки. Шаблоны регистрируются и отменяются из регистрации один раз в день с помощью планировщика заданий.

**Использование пути к каталогу шаблонов параметров для развертывания шаблонов расположений параметров UE-V**

1.  Перейдите к папке "сетевая папка", которая определена как каталог шаблонов параметров.

2.  Добавьте, удалите или обновите шаблоны расположений параметров в каталоге шаблонов параметров в соответствии с требуемой конфигурацией шаблона агента UE-V для компьютеров UE-V.

3.  Шаблоны на компьютерах обновляются ежедневно в соответствии с изменениями, внесенными в каталог шаблонов параметров.

4.  Откройте командную команду с повышенными привилегиями и перейдите в раздел **% Program Files%\\Microsoft виртуализация взаимодействия с пользователем \ \ &lt; x86 или x64 &gt; **, а затем запустите **ApplySettingsTemplateCatalog.exe** , чтобы вручную обновить шаблоны на компьютере, на котором запущен агент UE-V Agent.

## Статьи по теме


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[Развертывание UE-V 1.0](deploying-ue-v-10.md)

[Планирование того, какие приложения необходимо синхронизировать с UE-V 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





