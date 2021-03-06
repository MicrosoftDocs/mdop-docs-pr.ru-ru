---
title: О виртуальной среде связывающей группы
description: О виртуальной среде связывающей группы
author: dansimp
ms.assetid: 535fa640-cbd9-425e-8437-94650a70c264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bd93c9e7acbf7bbf3f9da506d5d95b8df09e1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814909"
---
# О виртуальной среде связывающей группы


**В этой статье:**

-   [Определение приоритета пакета](#bkmk-pkg-priority-deter)

-   [Слияние одинаковых путей к пакетам в один виртуальный каталог в группах подключений](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a>Определение приоритета пакета


Виртуальная среда и ее текущее состояние связаны с группой подключения, а не с отдельными пакетами. Если пакет App-V удален из группы подключения, то состояние, которое существовало как часть группы соединения, не будет перенесено вместе с пакетом.

Если один и тот же пакет входит в две разные группы соединения, необходимо указать, какая группа подключения должна использоваться приложением App-V. Например, в группе подключения может быть два пакета, каждый из которых определяет одинаковый параметр Registry.

Используемая Группа соединения основывается на порядке, в котором пакет находится в XML-документе **AppConnectionGroup** :

-   Первый пакет имеет наивысший приоритет.

-   Второй пакет имеет второй наивысший приоритет.

Ниже приведен примерный раздел.

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

Предполагается, что параметр DWORD ABC (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region) определен в первом и третьем пакете, например:

-   Пакет 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5

-   Пакет 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10

Поскольку сначала появляется пакет 1, в виртуальной среде AppConnectionGroup будет указано значение 5 (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5). Это означает, что виртуальные приложения в пакете 1, пакет 2 и пакет 3 будут видеть значение 5 при запросе HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region.

Другие виртуальные ресурсы среды разрешаются аналогичным образом, но в обычном случае конфликт происходит в реестре.

## <a href="" id="bkmk-merged-root-ve-exp"></a>Слияние одинаковых путей к пакетам в один виртуальный каталог в группах подключений


Если несколько пакетов в группе подключения содержат одинаковые пути к каталогам, они объединяются в один виртуальный каталог в виртуальной среде "Группа подключения". Это объединение путей позволяет приложению в одном пакете получить доступ к файлам в другом пакете.

При удалении пакета из группы подключения приложения, удаленные из этого пакета, больше не смогут получать доступ к файлам в остальных пакетах в группе подключения.

Порядок, в котором приложение App-V ищет имя файла в группе подключения, определяется порядком, в котором пакеты App-V указаны в файле манифеста группы подключения.

В следующем примере показан порядок и связь поиска имени файла в группе подключения для **пакета а** и **пакета B**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Упаковка</th>
<th align="left">Пакет B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>C:\Windows\System32</p></td>
<td align="left"><p>C:\Windows\System32</p></td>
</tr>
<tr class="even">
<td align="left"><p>C:\AppTest</p></td>
<td align="left"><p>C:\AppTest</p></td>
</tr>
</tbody>
</table>

 

В приведенном выше примере после того, как виртуализированное приложение пытается найти конкретный файл, сначала выполняется поиск в пакете A для соответствующего пути к файлу. Если соответствующий путь не найден, выполняется поиск пакета B, используя следующие правила сопоставления.

-   Если файл с именем **test.txt** существует в той же иерархии виртуальных папок в обоих пакетах приложения, используется первый совпадающий файл.

-   Если файл с именем **bar.txt** существует в иерархии виртуальных папок одного пакета приложения, но не в другом, используется первый совпадающий файл.






## Статьи по теме


[Управление связывающими группами](managing-connection-groups.md)

 

 





