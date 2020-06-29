---
title: Создание связывающей группы
description: Создание связывающей группы
author: dansimp
ms.assetid: 221e2eed-7ebb-42e3-b3d6-11c37c0578e6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f20b3e71c7c0b72d66700bbad945860112ffd03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814333"
---
# Создание связывающей группы


Выполните эти действия, чтобы создать группу подключений с помощью консоли управления App-V. Чтобы использовать PowerShell для создания групп подключений, ознакомьтесь со [сведениями о том, как управлять группами подключений на отдельном компьютере с помощью PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md).

Когда вы размещаете пакеты в группе подключений, их пути к корневому каталогу пакета объединяются. Если вы удалите пакеты, Объединенные корневые пакеты обслуживаются только в остальных пакетах.

**Создание группы подключения**

1.  В консоли управления App-V 5,1 выберите **группы подключения** , чтобы отобразить библиотеку групп подключения.

2.  Нажмите кнопку **Добавить группу подключения** , чтобы создать новую группу подключения.

3.  В области **Новая группа подключения** введите описание группы.

4.  Нажмите кнопку **изменить** в области **подключенные пакеты** , чтобы добавить в группу Подключение новое приложение.

5.  В области " **пакеты всей библиотеки** " выберите приложение, которое необходимо добавить, и щелкните стрелку, чтобы добавить приложение.

    Чтобы удалить приложение, выберите приложение, которое нужно удалить, в области **пакеты** и щелкните стрелку.

    Чтобы переустановить приоритеты приложений в группе "соединение", используйте стрелки в области " **пакеты** ".

    **Важно!**  По умолчанию конфигурации доступа доменных служб Active Directory, связанные с определенным приложением, не добавляются в группу подключения. Чтобы перенести конфигурацию доступа в Active Directory, выберите **Добавить пакет доступ к группе**, которая находится в области **пакеты** .

     

6.  После добавления всех приложений и настройки доступа к Active Directory нажмите кнопку **Применить**.

    **У вас есть предложение App-V**? Здесь вы можете добавить предложения и проголосовать [здесь](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **У вас возникла ошибка App-V?** Используйте [Форум TechNet App-V](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).

## Статьи по теме


[Операции, связанные с администрированием и использованием App-V 5.1](operations-for-app-v-51.md)

[Управление связывающими группами](managing-connection-groups51.md)

 

 




