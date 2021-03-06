---
title: Развертывание рабочей области MED-V с помощью системы электронного распространения программного обеспечения
description: Развертывание рабочей области MED-V с помощью системы электронного распространения программного обеспечения
author: dansimp
ms.assetid: b5134c35-e1de-470c-93f8-ead6218d9dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56d21b0c2f010f63c04056d9fadd7763531bd9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812992"
---
# Развертывание рабочей области MED-V с помощью системы электронного распространения программного обеспечения


Электронная система распространения программного обеспечения разработана для эффективного перемещения программного обеспечения на различные компьютеры в медленных или быстрых сетевых подключениях. В следующем разделе содержатся сведения и инструкции, которые помогут вам развернуть рабочую область MED-V в рамках всего предприятия с помощью системы распространения программного обеспечения.

**Примечание.**  
Независимо от того, какое решение используется для распространения программного обеспечения, вам должны быть знакомы требования, предъявляемые с конкретным решением. Если вы используете System Center Configuration Manager 2007 R2 или более поздней версии, ознакомьтесь с [библиотекой документации Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=66999) в технической библиотеке Microsoft ( https://go.microsoft.com/fwlink/?LinkId=66999) .



**Важно.**  
Если вы используете System Center Configuration Manager 2007 с пакетом обновления 2 (SP2), а ваши рабочие области MED-V настроены для работы в режиме **NAT** , виртуальные машины классифицируются как Интернет-клиенты и не могут найти ближайшие точки распространения для загрузки содержимого.

[Исправление для улучшения функциональности виртуальных машин, управляемых с помощью MED-](https://go.microsoft.com/fwlink/?LinkId=201088) v ( https://go.microsoft.com/fwlink/?LinkId=201088) добавляются новые возможности на виртуальные машины, управляемые med-v и настроенные для работы в режиме **NAT** . Новая функция позволяет виртуальным машинам получить доступ к ближайшим точкам распространения. Таким образом, администратор может управлять виртуальной машиной и ведущим компьютером точно так же. Сначала необходимо установить это исправление на сервере сайта, а затем на клиенте.

Обновление доступно для общего доступа. Тем не менее, вам может быть предложено принимать условия соглашения для служб Майкрософт. Следуйте указаниям на последовательных страницах, чтобы получить это исправление.



Вы также можете развернуть компоненты MED-V с помощью пакетного файла, но это требует перезапуска после установки Windows Virtual PC. Чтобы обойти это требование, вы можете задать один перезапуск после того, как все компоненты будут установлены. Кроме того, вы автоматически запускаете MED-v, так как при установке рабочей области MED-V в RUNKEY добавляется запись.

**Развертывание рабочей области MED-V с помощью системы распространения программного обеспечения**

1.  Определите группу компьютеров и пользователей в системе электронной рассылки программного обеспечения как целевые наборы компьютеров и пользователей.

2.  Создайте пакеты для каждого установочного файла Microsoft, который нужно распространить. Ниже указаны необходимые файлы и порядок их установки.

    1.  **Операционная система Windows Virtual PC** — если она еще не установлена (требуется перезагрузка компьютера). Дополнительные сведения можно найти в разделе [Настройка предварительных требований для установки](configure-installation-prerequisites.md).

    2.  Добавлены **и обновленные виртуальные компьютеры Windows** — если они еще не установлены. Дополнительные сведения можно найти в разделе [Настройка предварительных требований для установки](configure-installation-prerequisites.md).

    3.  **Установочный файл агента узла MED-v** — Установка агента узла (MED-V \ _HostAgent \ _setup установочный файл). Дополнительные сведения [можно найти в разделе Установка агента узла MED-V вручную](how-to-manually-install-the-med-v-host-agent.md).

        **Warning**  
        Перед установкой агента узла MED-V закройте Internet Explorer, в противном случае конфликты могут возникать позже с перенаправлением URL-адреса. Вы также можете сделать это, указав компьютер во время распространения.



    4.  **Программа установки рабочей области MED-v, VHD и исполняемый файл Setup** создаются в **упаковщике рабочих областей med-v**. Дополнительные сведения можно найти [в разделе Создание пакета рабочей области для MED-V](create-a-med-v-workspace-package.md).

        **Важно.**  
        Сжатый файл виртуального жесткого диска (. MEDV) и исполняемая программа установки (setup.exe) должны находиться в той же папке, что и в установщике рабочей области для MED-V. Затем установите установщик рабочей области MED-V, запустив setup.exe.



~~~
    **Tip**  
    Because problems can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



3. Настройте пакеты для работы в режиме молчания (вмешательство пользователя не требуется).

   При запуске в автоматическом режиме удаляется запрос на закрытие Internet Explorer, если он запущен, и запрос на запуск агента хоста MED-V. Оба действия выполняются при перезапуске компьютера.

   **Примечание.**  
   Для установки Virtual PC для Windows требуется перезагрузить компьютер. Вы можете создать один процесс установки и установить все компоненты одновременно, если отключить его и игнорировать предварительные требования, необходимые для установки MED-V. Это также можно сделать с помощью аргументов командной строки. Пример этих аргументов можно найти [в разделе Развертывание компонентов MED-V с помощью электронной системы распространения программного обеспечения](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch). MED-V автоматически запускается при перезапуске компьютера.



4. Перед установкой Windows Virtual PC установите MED-V и ее компоненты. Пример пакетного файла приведен ниже в этом разделе.

   **Важно.**  
   Выберите параметр **игнорировать \ _PREREQUISITES** , как показано в пакетном файле примера, чтобы можно было установить компоненты MED-V до необходимых компонентов VPC. Установите компоненты MED-V в соответствии с этим заказом, чтобы обеспечить единую перезагрузку.



5. Определите другие требования, необходимые для установки, и для системы распространения программного обеспечения, например целевых платформ и свободного места на диске.

6. Назначьте пакеты целевому набору компьютеров и пользователей.

   По мере выполнения компьютеров клиент системы распространения программного обеспечения распознает, что новые пакеты доступны, и начнет устанавливать пакеты в соответствии с определением и требованиями. Установка должна выполняться последовательно в автоматическом режиме. Мы рекомендуем выполнять эти действия как один процесс, который не требует перезапуска, пока не будут установлены все пакеты.

7. После завершения установки перезагрузите обновленные компьютеры.

   В зависимости от системы распространения программного обеспечения вы можете запланировать перезагрузку компьютера, или конечные пользователи смогут вручную перезапустить компьютеры во время их обычной работы. После перезапуска компьютера MED-V автоматически запускается после входа пользователя в систему. В первый раз при первом запуске MED-V запускается первая Настройка.

При первом запуске программы установки может потребоваться несколько минут, в зависимости от размера указанного виртуального жесткого диска и количества политик, примененных к рабочей области MED-V при запуске. Конечный пользователь может отслеживать ход выполнения, проследите за помощью значка MED-V в области уведомлений. Дополнительные сведения о первой настройке можно найти в статье [Обзор развертывания для MED-V 2,0](med-v-20-deployment-overview.md).

**Установка рабочей области MED-V с помощью пакетного файла**

1.  Запустите установку из командной строки с учетными данными администратора.

2.  Разместите каждый компонент в одном каталоге. При запуске из общей сетевой папке требуется более длительное время для распаковки файла. MEDV.

3.  Рекомендуется указывать, что Virtual PC и Windows Virtual PC Hotfix устанавливаются после агента узла MED-V и файлов пакета MED-V Workspace. Это означает, что при установке центра обновления Windows не будет вмешательство в процесс установки, если требуется перезагрузка.

4.  Перезагрузите компьютер после завершения выполнения пакетного файла.

После перезагрузки пользователю будет предложено запустить программу установки в первый раз и завершить настройку MED-V.

В приведенном ниже примере с заданными параметрами показано, как установить 64-разрядные компоненты MED-V в одном процессе.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Аргумент</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/norestart</p></td>
<td align="left"><p>Запрещает установку виртуальных ПК под управлением Windows и Windows Virtual PC Update из перезапуска главного компьютера.</p></td>
</tr>
<tr class="even">
<td align="left"><p>параметрами</p></td>
<td align="left"><p>Установка компонентов MED-V в тихом режиме без взаимодействия с пользователем.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Qn</p></td>
<td align="left"><p>Устанавливаются компоненты MED-V без пользовательского интерфейса.</p></td>
</tr>
<tr class="even">
<td align="left"><p>IGNORE_PREREQUISITES</p></td>
<td align="left"><p>Установка без проверки на наличие Virtual PC для Windows.</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Указывайте этот аргумент только в том случае, если вы устанавливаете Windows Virtual PC в рамках этой установки.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>OVERWRITEVHD</p></td>
<td align="left"><p>Принудительно устанавливает рабочую область MED-V и предотвращает любые запросы, которые она может создать.</p></td>
</tr>
</tbody>
</table>



## Пример


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## Статьи по теме


[Обзор развертывания MED-V 2.0](med-v-20-deployment-overview.md)

[Развертывание рабочей области MED-V в образе Windows 7](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)









