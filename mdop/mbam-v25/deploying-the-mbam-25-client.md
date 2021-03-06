---
title: Развертывание клиента MBAM 2.5
description: Развертывание клиента MBAM 2.5
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826279"
---
# Развертывание клиента MBAM 2.5


Клиентское программное обеспечение Microsoft BitLocker Administration и Monitoring (MBAM) позволяет администраторам принудительно применять и отслеживать шифрование диска BitLocker на компьютерах предприятия. Клиент BitLocker можно интегрировать в организацию, развертывая клиент с помощью электронной системы распространения программного обеспечения, например доменных служб Active Directory или напрямую шифруя клиентские компьютеры в рамках первоначального процесса обработки изображений.

В зависимости от того, как вы развертываете клиентское программное обеспечение для администрирования Microsoft BitLocker и наблюдения за ним, вы можете включить шифрование диска BitLocker на компьютере в вашей организации до того, как пользователь получит компьютер или попозже настроить групповую политику и развернуть клиентское программное обеспечение MBAM с помощью корпоративной системы развертывания программного обеспечения.

## Развертывание клиента MBAM на настольных компьютерах и ноутбуках


После настройки параметров групповой политики вы можете использовать корпоративную систему развертывания программного обеспечения, например MicrosoftSystemCenter2012 ConfigurationManager или доменные службы Active Directory, для развертывания файлов установщика Windows MBAM на целевые компьютеры. Вы можете использовать либо 32-разрядный, либо 64-разрядный MbamClientSetup.exe, либо файлы 32-bit или 64-bit MBAMClient.msi, которые предоставляются в клиентском программном обеспечении MBAM. Дополнительные сведения о развертывании параметров групповой политики MBAM см. в разделе [Развертывание объектов групповой политики MBAM 2,5](deploying-mbam-25-group-policy-objects.md).

**Примечание**  Начиная с MBAM 2,5 с пакетом обновления 1 (SP1), отдельный MSI больше не входит в состав продукта MBAM. Тем не менее, вы можете извлечь MSI из исполняемого файла (exe), который входит в состав продукта.

 

[Развертывание клиента MBAM на настольных компьютерах и ноутбуках](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## Развертывание клиента MBAM в рамках развертывания Windows


В организациях, где компьютеры принимают и настраиваются централизованно, вы можете установить клиент MBAM для управления шифрованием диска BitLocker на каждом компьютере, прежде чем на него будут записываться пользовательские данные. Преимущество этого процесса состоит в том, что каждый из компьютеров является совместимым с шифрованием диска BitLocker. Этот метод не полагается на действия пользователя, так как администратор уже зашифровал компьютер. Ключевым допущением для этого сценария является то, что политика Организации устанавливает корпоративный образ Windows до того, как компьютер будет доставлен пользователю. Если параметрам групповой политики требуется ПИН-код, пользователи получат запрос на установку PIN-кода после того, как он получит эту политику.

[Включение BitLocker с помощью MBAM в составе развертывания Windows](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## Развертывание клиента MBAM с помощью командной строки


В этом разделе объясняется, как установить клиент MBAM с помощью командной строки.

[Развертывание клиента MBAM с помощью командной строки](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## Другие ресурсы для развертывания клиента MBAM


[Развертывание MBAM 2.5](deploying-mbam-25.md)



## Статьи по теме


[Развертывание MBAM 2.5](deploying-mbam-25.md)

[Планирование для MBAM 2.5](planning-for-mbam-25.md)

 
## У вас есть предложение MBAM?
- Здесь вы можете добавить предложения и проголосовать [здесь](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring). 
- Для MBAM проблемы используйте [MBAM Форум TechNet](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).
 





