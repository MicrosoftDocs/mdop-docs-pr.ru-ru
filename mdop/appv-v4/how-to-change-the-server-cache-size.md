---
title: Изменение размера кэша сервера
description: Изменение размера кэша сервера
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818029"
---
# Изменение размера кэша сервера


Вы можете использовать описанную ниже процедуру, чтобы изменить размер кэша для любого сервера прямо из консоли управления сервером виртуализации приложений.

**Примечание**  Несмотря на то, что вы можете изменить размер кэша, если только для вашей конфигурации вам не потребуется изменить размер, рекомендуется оставить для размера кэша значения, заданные по умолчанию.

 

**Изменение размера кэша сервера**

1.  Щелкните узел **группы серверов** на левой панели, чтобы развернуть список групп серверов.

2.  В области **результатов** дважды щелкните нужную группу серверов, чтобы отобразить список серверов в группе.

3.  В области **результатов** щелкните правой кнопкой мыши требуемый сервер и выберите пункт **свойства**.

4.  Откройте вкладку **Дополнительно** .

5.  Введите значение в поле **максимального выделения памяти** для кэша сервера и введите значение порога предупреждения в поле **предупреждать выделения памяти** .

6.  Введите значение в поле **максимального размера блока** . Это число должно быть больше или равно максимальному размеру блока для максимального пакета, который будет передаваться на поток от сервера.

7.  Нажмите кнопку **ОК**.

## Статьи по теме


[Изменение порта сервера](how-to-change-the-server-port.md)

[Управление серверами на консоли управления серверами](how-to-manage-servers-in-the-server-management-console.md)

 

 





