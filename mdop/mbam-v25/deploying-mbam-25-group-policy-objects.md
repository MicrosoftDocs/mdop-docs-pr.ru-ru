---
title: Развертывание объектов групповой политики MBAM 2.5
description: Развертывание объектов групповой политики MBAM 2.5
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824389"
---
# Развертывание объектов групповой политики MBAM 2.5


Чтобы развернуть MBAM, необходимо задать параметры групповой политики, определяющие параметры реализации MBAM для шифрования диска BitLocker. Для выполнения этой задачи необходимо скопировать шаблоны групповой политики MBAM на сервер или рабочую станцию, которые могут выполнять консоль управления групповыми политиками (GPMC) или расширенное управление групповыми политиками, а затем изменить параметры.

**Важно!**  Не изменяйте параметры групповой политики в разделе " **Шифрование диска BitLocker** " или MBAM будут работать неправильно. При настройке параметров групповой политики на узле **MDOP MBAM (Управление BitLocker)** MBAM автоматически настраивает параметры **шифрования диска для BitLocker** .

 

## Копирование шаблонов групповой политики MBAM 2.5


Перед установкой клиента MBAM необходимо скопировать MBAM-специфические объекты групповой политики (GPO) на рабочую станцию управления. Эти GPO определяют параметры реализации MBAM для шифрования диска BitLocker. Вы можете скопировать шаблоны групповой политики на любой сервер или рабочую станцию, которые поддерживаются в Windows Server или на клиентском компьютере, и смогли запустить консоль управления групповыми политиками или расширенное управление групповыми политиками.

[Копирование шаблонов групповой политики MBAM 2.5](copying-the-mbam-25-group-policy-templates.md)

## Изменение параметров объекта групповой политики MBAM 2,0


После создания необходимых GPO необходимо развернуть параметры групповой политики MBAM на клиентских компьютерах своей организации. Для просмотра и создания объектов групповой политики необходимо установить консоль управления групповыми политиками (GPMC) или расширенное управление групповыми политиками.

[Изменение параметров групповой политики MBAM 2.5](editing-the-mbam-25-group-policy-settings.md)

## Отображение и скрытие панели управления MBAM на панели управления Windows


Поскольку MBAM позволяет настроить панель управления Windows BitLocker по умолчанию, вы также можете отобразить или скрыть панель управления по умолчанию для конечных пользователей с помощью параметров групповой политики.

[Скрытие элемента шифрования диска BitLocker по умолчанию на панели управления](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## Другие ресурсы по развертыванию объектов групповой политики MBAM 2,0


[Развертывание MBAM 2.5](deploying-mbam-25.md)

## У вас есть предложение MBAM?
- Здесь вы можете добавить предложения и проголосовать [здесь](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring). 
- Для MBAM проблемы используйте [MBAM Форум TechNet](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).

 

 





