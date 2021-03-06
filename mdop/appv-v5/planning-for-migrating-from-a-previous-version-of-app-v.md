---
title: Планирование миграции из предыдущей версии App-V
description: Планирование миграции из предыдущей версии App-V
author: dansimp
ms.assetid: d4ca8f09-86fd-456f-8ec2-242ff94ae9a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2242f58a29473e116506ec013b94a79d1bb814a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813472"
---
# Планирование миграции из предыдущей версии App-V


Ниже приведены сведения о том, как выполнить миграцию в App-V 5,0 из предыдущих версий App-V.

## Требования к миграции


Прежде чем приступать к обновлению, ознакомьтесь с приведенными ниже требованиями.

-   Если вы выполняете обновление до версии App-V 4,6 SP2, перед обновлением до App-V 5,0 или более поздней версии обновите версию App-V 4,6 SP3. В этом случае сначала обновите клиенты App-V, а затем обновите серверные компоненты.
**Примечание.** Приложение App-V 4,6 завершило работу базовой поддержки.

-   Приложение App-V 5,0 поддерживает только пакеты, созданные с помощью App-V 5,0, или пакеты, которые были преобразованы в формат App-V 5,0 (**. AppV**).

-   Только для App-v 5,0 SP3: Если вы обновляете сервер App-v 5,0 SP1, ознакомьтесь с инструкциями по установке [App-v 5,0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3) .

## Одновременное выполнение клиента App-V 5,0 с приложением-V 4,6


Клиент App-V 5,0 может одновременно выполняться на том же компьютере, что и клиент App-V 4.6 SP3.

При запуске существующих клиентов App-V вы можете:

-   Преобразуйте пакет обновления 3 (SP3) для App-v 4,6 в формат App-V 5,0 и опубликуйте оба пакета, если оба клиента запущены.

-   Определите политику миграции для преобразованного пакета, который позволяет преобразованному пакету App-V 5,0 предполагать сопоставления типов файлов и ярлыки из пакета App-V 4,6.

### Поддерживаемые сценарии сосуществования

В следующей таблице показаны поддерживаемые сценарии сосуществования App-V. Мы рекомендуем установить последние доступные обновления определенного выпуска, если вы используете соуже существующие клиенты.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Тип клиента App-V 4,6</th>
<th align="left">Тип клиента App-V 5,0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 4,6 с пакетом обновления 3 (SP3)</p></td>
<td align="left"><p>App-V 5,0</p></td>
</tr>
<tr class="even">
<td align="left"><p>RDS-V 4,6 SP3</p></td>
<td align="left"><p>App-V 5,0 RDS</p></td>
</tr>
</tbody>
</table>

 

### Требования для запуска существующих клиентов

Для работы с существующими клиентами необходимо выполнить следующие действия:

-   Установите клиент App-V 4.6 перед установкой клиента App-V 5,0.

-   Включите параметр групповой политики **включения режима миграции** , который находится в узле досуществования клиента **App-V** &gt; **Client Coexistence** . Чтобы получить шаблон развертывания ADMX, ознакомьтесь со статьей [скачивание и развертывание шаблонов групповой политики MDOP](https://technet.microsoft.com/library/dn659707.aspx).

### Загрузка и документация для клиента

В приведенной ниже таблице содержится ссылка на документацию по выпускам TechNet. Документация TechNet о клиенте App-V применима к обоим клиентам, если не указано иное.

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Версия App-V</th>
<th align="left">Ссылка на документацию TechNet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 4.6 SP3</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)">Сведения о системе Microsoft Application Virtualization 4.6 с пакетом обновления 3 (SP3)</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.0 SP3</p></td>
<td align="left"><p><a href="about-app-v-50-sp3.md" data-raw-source="[About Microsoft Application Virtualization 5.0 SP3](about-app-v-50-sp3.md)">Сведения о Microsoft Application Virtualization 5,0 SP3</a></p></td>
</tr>
</tbody>
</table>

 

Дополнительные сведения о настройке сосуществования клиента App-V 5,0 можно найти в следующих статьях:

-   [Развертывание приложения App-V 4,6 и клиента App-V 5,0 на том же компьютере](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

-   [Сосуществование и миграция App-V 5,0](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a>Преобразование пакетов предыдущей версии с помощью преобразователя пакетов


Перед переносом пакета, созданного с помощью App-V 4.6 SP3 или более ранней версии, в App-V 5,0, ознакомьтесь с приведенными ниже требованиями.

-   Вы должны преобразовать пакет в файл формата **. AppV** .

-   Преобразователь пакетов поддерживает только прямое преобразование пакетов, созданных с помощью App-V 4,5 и более поздних версий. Чтобы использовать преобразователь пакетов для пакета, созданного с помощью предыдущей версии, необходимо использовать приложение App-V версии 4.5 или более поздней для обновления пакета, а затем можно выполнить преобразование пакета.

Дополнительные сведения об использовании конвертера пакетов для преобразования пакета приведены в разделе [Преобразование пакета, созданного в предыдущей версии App-V](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md). После преобразования файла вы можете развернуть его на целевые компьютеры, на которых запущен клиент App-V 5,0.






## Статьи по теме


[Планирование развертывания App-V](planning-to-deploy-app-v.md)

 

 





