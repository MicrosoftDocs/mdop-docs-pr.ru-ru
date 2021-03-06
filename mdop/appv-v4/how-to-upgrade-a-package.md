---
title: Обновление пакета
description: Обновление пакета
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816502"
---
# Обновление пакета


Процесс автоматического обновления такой же, как и для добавления версии пакета в консоли управления сервером Application Virtualization. Автоматическое обновление выполняется при переупорядочении приложения в существующем пакете. Затем вы можете добавить эту новую версию на серверы для потоковой передачи.

Когда вы обновляете пакет с помощью новой версии, вы можете оставить существующую версию на своем место или удалить, а затем оставить только последнюю из них. Вы можете оставить старую версию для обеспечения совместимости с устаревшими документами или протестировать новую версию перед тем, как сделать ее доступной для всех пользователей.

**Автоматическое обновление пакета**

1.  Скопируйте новый SFT-файл в папку содержимого сервера Application Virtualization.

    **Примечание**  Если в ходе повторной последовательности не были добавлены функции, которые изменили файлы дескрипторов программного обеспечения (OSD), значка (ICO) или секвенсора (SPRJ), вам не нужно их копировать. Вы можете включить эти файлы, если хотите, чтобы все эти файлы отображались одинаковой датой.

     

2.  В левой области консоли управления сервером виртуализации приложений разверните раздел **пакеты**.

3.  Щелкните правой кнопкой мыши пакет, который вы хотите обновить, и выберите команду **Добавить версию**.

4.  В диалоговом окне **Добавить версию пакета** найдите и введите полный путь к новой версии приложения в поле **файл** . Это должен быть SFT — файл.

5.  Нажмите кнопку **Далее**.

6.  В диалоговом окне **Сводка** показано расположение файла и запрос на его копирование, если вы еще не сделали этого. После проверки данных нажмите кнопку **Готово** .

    Новая версия теперь завершена и готова к потоку.

## Статьи по теме


[Управление пакетами на консоли управления серверами](how-to-manage-packages-in-the-server-management-console.md)

 

 





