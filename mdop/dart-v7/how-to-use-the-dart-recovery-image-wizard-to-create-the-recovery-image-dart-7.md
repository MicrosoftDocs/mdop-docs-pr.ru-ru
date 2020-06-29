---
title: Использование мастера образа для восстановления DaRT для создания образа для восстановления
description: Использование мастера образа для восстановления DaRT для создания образа для восстановления
author: dansimp
ms.assetid: 1b8ef983-fff9-4d75-a2f6-53120c5c00c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49253a8c0bf9c9073b57712acc773e4a57e31d72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822922"
---
# Использование мастера образа для восстановления DaRT для создания образа для восстановления


Набор средств диагностики и восстановления Microsoft (DaRT) 7 включает **мастер изображений для восстановления DaRT** , который используется в Windows для создания загрузочного образа международной организации по стандартизации (ISO). ISO-образ — это файл, который представляет собой необработанное содержимое компакт-диска.

**Мастеру создания изображений для восстановления DaRT** требуется следующая информация:

-   **Загрузочный образ**°, часть которого требуется, необходимо указать путь к установочным файлам на DVD-диске Windows 7 или Windows 7, которые необходимы для создания изображения для восстановления DART.

-   **Выбор инструментов**на ° по градусам. Вы можете выбрать инструменты, которые нужно включить в изображение для восстановления DART.

-   **Удаленные соединения**° по-градусы. Вы можете выбрать, нужно ли использовать в качестве изображения восстановления DaRT возможность устанавливать удаленное соединение между службой поддержки и компьютером конечного пользователя.

-   **Средства отладки для Windows**° ° вам будет предложено указать расположение средств отладки для Windows.

-   **Определения для автономного чистильщика системы**°, в котором вы можете определить, нужно ли скачивать последние определения на момент создания образа восстановления или скачивания определений позже.

-   **Drivers**° с другими драйверами вы запросите, хотите ли вы добавить драйверы к образу ISO.

-   **Дополнительные файлы**, которые могут помочь при диагностике проблем, вы можете добавить файлы в образ ISO °.

-   **Расположение изображений ISO**°, на которое нужно указать, где должен находиться образ ISO.

-   **Дисковод CD-и DVD-дисков**°, на котором отображается вопрос, нужно ли использовать компакт-диск или DVD-дисковод для записи CD или DVD.

**Примечание**  Размер образа ISO может отличаться в зависимости от средств, выбранных в **мастере создания изображений для восстановления DaRT**.

 

## Создание образа восстановления с помощью мастера создания изображений для восстановления DaRT


Следуйте этим инструкциям, чтобы создать изображение для восстановления DaRT с помощью **мастера создания изображений** для средства DART Recovery.

### Выбор инструментов для восстановления с помощью DaRT

**Мастер создания изображений для восстановления** с помощью DaRT предлагает диалоговое окно " **Выбор инструмента** ". Вы можете выбрать и удалить инструменты из списка инструментов, которые будут включены в изображение для восстановления DaRT, выделив инструмент и нажав кнопку **включить** или **Отключить** .

После выбора всех инструментов, которые вы хотите включить в образ восстановления, нажмите кнопку **Далее**.

### Добавление параметра для разрешения удаленного подключения

Вы можете установить флажок **Разрешить удаленные подключения** , чтобы предоставить возможность в окне **средств диагностики и восстановления** для установления удаленного соединения между агентом справочной службы и компьютером конечного пользователя. После того как агент службы поддержки установит удаленное соединение, он сможет запускать инструменты DaRT на компьютере конечного пользователя, находясь в удаленном расположении.

Вы можете установить флажок **задать номер порта** , чтобы указать конкретный номер порта, который будет использоваться при установлении удаленного подключения. Вы можете указать номер порта в диапазоне от 1 до 65535. Чтобы свести к минимуму вероятность конфликта, мы рекомендуем использовать номер порта 1024 или выше.

Вы также можете создать настраиваемое сообщение, которое будет получено конечным пользователем при установке удаленного подключения. Сообщение не может содержать более 2048 символов.

Дополнительные сведения об удаленном запуске средств DaRT можно найти в статьях [Восстановление удаленных компьютеров с помощью DaRT Recovery](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).

### Добавление средств отладки для Windows в образ восстановления DaRT

В диалоговом окне **анализатора аварийного завершения** **мастера создания изображений для восстановления DaRT**вам будет предложено указать расположение средств отладки для Windows. Если у вас нет копии инструментов, вы можете скачать их из Microsoft. Ниже приведена ссылка на страницу загрузки, указанная в мастере: [скачивание и установка средств отладки для Windows](https://go.microsoft.com/fwlink/?LinkId=99934).

Вы можете указать расположение инструментальных средств отладки на компьютере, на котором запущен **Мастер создания образа для восстановления DaRT**, или вы можете использовать инструменты, которые находятся на целевом компьютере. Если вы решили использовать копию на другом компьютере, необходимо убедиться, что эти средства установлены на всех компьютерах, на которых выполняется диагностика сбоя.

**Примечание**  Если вы включите в образ ISO- **Analyzer аварийный анализ** , мы рекомендуем вам также включить средства отладки для Windows.

 

Чтобы добавить инструменты отладки для Windows, выполните указанные ниже действия.

1.  Необязательно Щелкните гиперссылку, чтобы загрузить инструменты отладки для Windows.

2.  Выберите один из следующих вариантов:

    -   **Используйте инструменты отладки для Windows в следующем расположении**. Если выбрать этот параметр, вы можете перейти к расположению инструментов.

    -   **Найдите инструменты отладки для Windows в системе, которую вы хотите восстановить**. Если вы выберете этот параметр, **анализатор сбоев** не будет работать, если средства отладки для Windows не будут найдены на компьютере с неполадками.

3.  Закончив, нажмите кнопку **Далее**.

### Добавление определений для автономного очистки системы в образ восстановления DaRT

Определения — это репозиторий известных вредоносных программ и другой потенциально нежелательной программы. Поскольку вредоносные программы постоянно разрабатываются, **автономный** средство проверки системы основывается на текущих определениях, чтобы определить, является ли программное обеспечение, которое пытается установить, запустить или изменить параметры на компьютере, может быть нежелательным или вредоносным программным обеспечением.

Чтобы включить последние определения в изображение для восстановления DaRT (рекомендуемый вариант), нажмите кнопку **Да, чтобы скачать последние определения.** Обновление определений запускается автоматически. Для выполнения этой процедуры необходимо подключение к Интернету.

Чтобы пропустить обновление определения, нажмите кнопку **нет, загрузив определения позже вручную**. Определения не будут включены в образ восстановления DaRT.

Если вы решили не включать последние определения в образ восстановления или если определения, включенные в образ восстановления, больше не являются актуальными в момент, когда вы будете готовы использовать **автономный**средство проверки системы, получите последние определения перед началом сканирования, следуя инструкциям, приведенным в **автономном**выходе системы.

**Важно!**  Вы не можете проверить, нет ли каких – либо определений.

 

Закончив, нажмите кнопку **Далее**.

### Добавление драйверов в образ восстановления DaRT

**Внимание!**  По умолчанию при добавлении драйвера в образ восстановления DaRT все дополнительные файлы и вложенные папки, расположенные в этой папке, добавляются в образ восстановления. Дополнительные сведения можно найти в разделе [Устранение неполадок DaRT 7,0](troubleshooting-dart-70-new-ia.md).

 

Вы должны добавить в образ восстановления дополнительные драйверы для DaRT7, которые могут потребоваться при восстановлении компьютера. Сюда обычно относятся устройства хранения данных или сетевые контроллеры, не включенные в DVD-диск Windows.

**Важно!**  Если вы выбрали драйвер для включения, имейте в виду, что в DaRT не поддерживается беспроводная связь (например, Bluetooth или 802.11 a/b/g/n).

 

**Добавление драйвера хранилища или сетевого контроллера в образ восстановления**

1.  В диалоговом окне **Дополнительные драйверы** **мастера создания изображений для восстановления DaRT**нажмите кнопку **Добавить устройство**.

2.  Перейдите к файлу, который нужно добавить для драйвера, и нажмите кнопку **Открыть**.

    **Примечание**  Файл **драйвера** предоставляется производителем устройства хранения или сетевого контроллера.

     

3.  Повторите действия 1 и 2 для каждого драйвера, который вы хотите включить.

4.  Закончив, нажмите кнопку **Далее**.

### Добавление файлов в образ восстановления DaRT

Выполните эти действия, чтобы добавить файлы в образ восстановления, чтобы их можно было использовать для диагностики неполадок на компьютере.

1.  В диалоговом окне **Дополнительные файлы** **мастера изображений для восстановления DaRT**нажмите кнопку **Показать файлы**. Откроется окно проводника, в котором отображается папка, в которой хранятся общие файлы.

2.  Создайте вложенную папку в папке, которая указана в диалоговом окне.

3.  Скопируйте файлы, которые вы хотите добавить в новую вложенную папку.

4.  Закончив, нажмите кнопку **Далее.**

### Выбор расположения ISO-файла, содержащего изображение для восстановления DaRT

Чтобы указать расположение для создания образа ISO, выполните указанные ниже действия.

1.  В диалоговом окне **Создание образа запуска** **мастера изображений для восстановления DaRT**нажмите кнопку **Обзор**.

2.  Найдите нужное расположение в окне " **Сохранить как** " и нажмите кнопку " **сохранить**".

3.  Закончив, нажмите кнопку **Далее**.

Размер образа ISO может зависеть от выбранных вами инструментов и файлов, которые вы добавляете в мастере.

Для мастера требуется, чтобы ISO-образ имел расширение имени **. ISO** , так как в большинстве программ, которые занимают CD или DVD, требуется это расширение. Если вы не укажете другое расположение, на рабочем столе создается образ ISO с именем **DaRT70. ISO**.

### Запись образа восстановления на компакт-диск или DVD-диск

Если **Мастер создания изображений для восстановления** с помощью DaRT обнаружит на компьютере совместимый дисковод CD-RW, он предложит записать образ ISO на диск. Если вы хотите записать CD или DVD-диск, а мастер не распознает диск, необходимо использовать другую программу, например программу, которая была включена в диск. Вы можете создавать дополнительные копии с помощью дубликата, службы дублирования или программного обеспечения для записи DVD-дисков.

1.  В диалоговом окне **записать на компакт-диск или DVD** -диск с помощью **мастера создания изображений для восстановления DaRT**выберите **записать изображение на записываемый компакт-диск или DVD-дисковод**.

2.  Выберите CD или DVD-диск.

    **Примечание**  Если диск не распознается и вы установили новый диск, вы можете нажать кнопку **Обновить список дисков** , чтобы заставить мастер обновить список доступных дисков.

     

3.  Нажмите кнопку **Далее**.

## Статьи по теме


[Создание образа для восстановления DaRT 7.0](creating-the-dart-70-recovery-image-dart-7.md)

 

 




