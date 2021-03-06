---
title: Настройка расширений виртуальных приложений для определенной группы AD с помощью консоли управления
description: Настройка расширений виртуальных приложений для определенной группы AD с помощью консоли управления
author: dansimp
ms.assetid: 4f249ee3-cc2d-4b1e-afe5-d1cbf9cabd88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57ce4b82cc552e0a4adc2272f849111d8da0be71
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814253"
---
# Настройка расширений виртуальных приложений для определенной группы AD с помощью консоли управления


Чтобы настроить расширения виртуальных приложений для группы Active Directory (AD), выполните указанные ниже действия.

**Настройка расширений виртуальных приложений для группы AD**

1.  Чтобы просмотреть пакет, который вы хотите настроить, откройте консоль управления App-V 5,0. Чтобы просмотреть конфигурацию, назначенную данной группе пользователей, выберите пакет и щелкните правой кнопкой мыши имя пакета и выберите пункт **изменить доступ к Active Directory**. Кроме того, можно выбрать пакет и нажать кнопку **изменить** на панели **AD Access** .

2.  Чтобы настроить группу БАННЕРов, вы можете найти ее в списке **сущностей рекламных объявлений с Access**. Затем с помощью раскрывающегося списка в области **назначенная конфигурация** выберите пункт **Настраиваемая**и нажмите кнопку **изменить**.

3.  Чтобы отключить все расширения для данного приложения, снимите флажок **включить**.

    Чтобы добавить новое сочетание клавиш для выбранного приложения, щелкните его правой кнопкой мыши в области **ярлыков** и выберите команду **Добавить новый ярлык**. Чтобы удалить ярлык, щелкните его правой кнопкой мыши в области **ярлыков** и выберите команду **удалить ярлык**. Чтобы изменить существующий ярлык, щелкните приложение правой кнопкой мыши и выберите команду **изменить ярлык**.

4.  Чтобы просмотреть другие расширения приложения, нажмите кнопку **Дополнительно**и выберите пункт **Экспорт конфигурации**. Введите имя файла и нажмите кнопку **сохранить**. С помощью файла конфигурации можно просмотреть все расширения приложений, связанные с пакетом.

5.  Чтобы изменить дополнительные расширения приложения, измените файл конфигурации и нажмите кнопку **Импорт и перезапись конфигурации**. Выберите измененный файл и нажмите кнопку **Открыть**. В диалоговом окне нажмите кнопку **Перезаписать** , чтобы завершить процесс.

    **У вас есть предложение App-V**? Здесь вы можете добавить предложения и проголосовать [здесь](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **У вас возникла ошибка App-V?** Используйте [Форум TechNet App-V](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).

## Статьи по теме


[Операции, связанные с администрированием и использованием App-V 5.0](operations-for-app-v-50.md)

 

 





