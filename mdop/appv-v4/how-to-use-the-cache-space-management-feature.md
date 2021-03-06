---
title: Использование функции управления размером кэша
description: Использование функции управления размером кэша
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816409"
---
# Использование функции управления размером кэша


Функция управления пространством кэша файловой системы использует по крайней мере Последнее использование алгоритма (LRU) и включается по умолчанию. Если пространство, требуемое для нового пакета, превысит доступное свободное пространство в кэше, клиент Application Virtualization (App-V) использует эту функцию, чтобы определить, какие из существующих пакетов могут удалять из кэша, чтобы освободить место для нового пакета. Клиент удаляет пакет с самой ранней датой последнего доступа, если он старше значения, указанного в параметре реестра MinPkgAge. Использование функции управления пространством кэша FileSystem также поможет избежать проблем с кэшем кэша.

При необходимости в них удаляется несколько пакетов. Заблокированные пакеты не удаляются.

**Примечание**  Чтобы убедиться в том, что в кэше достаточно места для всех пакетов, которые могут быть развернуты, используйте параметр " **использовать порог свободного места на диске** " при настройке клиента, чтобы при необходимости кэш мог расти. Кроме того, вы можете заранее определить, сколько места на диске требуется для кэша App-V, и в процессе установки задать размер кэша соответствующим образом.

 

Функция управления пространством кэша управляется значением реестра UnloadLeastRecentlyUsed. Значение 1 включает функцию, а значение 0 (ноль) — отключает ее.

**Включение и отключение функции управления пространством кэша**

-   Задайте для следующего значения реестра значение 1, чтобы включить алгоритм LRU. Установите для него значение 0 (нуль), чтобы отключить эту функцию.

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed

**Управление пакетами, которые могут быть удалены**

-   Чтобы определить, когда можно выбрать пакет для удаления, задайте для следующего значения реестра значение, равное минимальному количеству дней, которое вы хотите пропройти с момента последнего доступа к пакету. Пакеты, которые использовались в последнее время, не удаляются.

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge

    **Внимание!**  Максимальное значение для этого раздела реестра — 0x00011111. Большие значения будут препятствовать правильной работе функции управления пространством кэша.

     

## Статьи по теме


[Настройка параметров реестра клиента App-V с помощью командной строки](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





