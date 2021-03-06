---
title: Сведения об отчетности в App-V 5.0
description: Сведения об отчетности в App-V 5.0
author: dansimp
ms.assetid: 27c33dda-f017-41e3-8a78-1b681543ec4f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a29585886aa20233f49c85101cff570a098c69ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815022"
---
# Сведения об отчетности в App-V 5.0


Microsoft Application Virtualization (App-V) 5,0 включает встроенную функцию для создания отчетов, которая позволяет собирать сведения о компьютерах, на которых работает клиент App-V 5,0, а также сведения об использовании виртуальных пакетов приложений. Эти сведения можно использовать для создания отчетов из централизованной базы данных.

## <a href="" id="---------app-v-5-0-reporting-overview"></a> Общие сведения о создании отчетов для App-V 5,0


В списке ниже представлен рабочий процесс верхнего уровня для создания отчетов в приложении App-V 5,0.

1.  У сервера отчетов Microsoft Application Virtualization (App-V) 5,0 имеются следующие предварительные требования:

    -   Роль веб-сервера информационных служб Интернета (IIS)

    -   Роль проверки подлинности Windows (в разделе **IIS/безопасность**)

    -   SQL Server установлен и запущен с помощью служб SQL Server Reporting Services (SSRS)

    Чтобы убедиться в том, что службы SQL Server Reporting Services запущены, просмотрите `http://localhost/Reports` веб-браузер с правами администратора на сервере, на котором будут размещены отчеты App-V 5,0. Должна отобразиться домашняя страница служб SQL Server Reporting Services.

2.  Установите сервер отчетов App-V 5,0 и связанную базу данных. Дополнительные сведения об установке сервера отчетов можно найти в разделе [Установка сервера отчетов на отдельном компьютере и его подключение к базе данных](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md). Настройте время, когда компьютер, на котором работает клиент App-V 5,0, должен отправлять данные на сервер отчетов.

3.  Если вы не используете электронную систему распространения программного обеспечения, например Configuration Manager для просмотра отчетов, вы можете определить отчеты в службе SQL Server Reporting Services. Загрузите предопределенные отчеты appvshort из центра загрузки по адресу <https://go.microsoft.com/fwlink/?LinkId=397255> .

    **Примечание**  При использовании интеграции Configuration Manager с App-V 5,0 большинство отчетов создаются из Configuration Manager, а не из App-V 5,0.

     

4.  После импорта модуля PowerShell App-V 5,0 с помощью `Import-Module AppvClient` учетной записи администратора включите клиент App-v 5,0. Этот образец командлета PowerShell включает отчетность App-V 5,0:

    ``` syntax
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    Чтобы немедленно отправить данные отчета App-V 5,0, запустите `Send-AppvClientReport` клиент App-v 5,0.

    Дополнительные сведения об установке клиента App-V 5,0 с поддержкой отчетов можно найти в разделе [Параметры конфигурации клиента](about-client-configuration-settings.md). Чтобы настроить отчеты App-V 5,0 с помощью Windows PowerShell, ознакомьтесь со [сведениями о том, как включить отчеты в клиенте App-v 5,0 с использованием PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md).

5.  После того как сервер отчетов получает данные из клиента App-V 5,0, он отправляет данные в базу данных отчетов. Когда база данных получает и обрабатывает данные клиента, успешный ответ отправляется на сервер отчетов, а затем на клиент App-V 5,0 отправляется уведомление.

6.  Когда клиент App-V 5,0 получает уведомление об успешном завершении, оно очищает кэш данных для экономии места.

    **Примечание**  По умолчанию кэш очищается после того, как сервер подтвердит получение данных. Вы можете вручную настроить клиент для сохранения кэша данных.

     

~~~
If the App-V 5.0 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval. Clients continue to collect data and add it to the cache.
~~~

### <a href="" id="-------------app-v-5-0-reporting-server-frequently-asked-questions"></a> Ответы на часто задаваемые вопросы о приложении App-V 5,0

В следующей таблице приведены ответы на часто задаваемые вопросы об использовании отчетов App-V 5,0.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Вопрос</th>
<th align="left">Дополнительные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Какова частота отправки данных отчетов в базу данных отчетов?</p></td>
<td align="left"><p>Частота зависит от того, как настроена задача создания отчетов на компьютере, на котором запущен клиент App-V 5,0. Вы должны настроить частоту и интервал для отправки данных отчета. Служба отчетов App-V 5,0 по умолчанию не включена.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Какие данные хранятся в базе данных сервера отчетов?</p></td>
<td align="left"><p>В следующем списке приведены сведения, хранящиеся в базе данных отчетов.</p>
<ul>
<li><p>Операционная система, запущенная на компьютере с клиентским приложением App-V 5,0: имя узла, версия, пакет обновления, тип-клиент, сервер, архитектура процессора.</p></li>
<li><p>Сведения о клиенте App-V 5,0: Version.</p></li>
<li><p>Список опубликованных пакетов: GUID, версия GUID, имя.</p></li>
<li><p>Сведения об использовании приложения: имя, версия, потоковый сервер, пользователь (domain\alias), версия пакета, состояние и время завершения работы.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>Каков средний объем данных, отправляемых на сервер отчетов?</p></td>
<td align="left"><p>Смотря как. В списке ниже перечислены три набора данных, отправляемых на сервер отчетов.</p>
<ol>
<li><p>Сведения об операционной системе и клиенте App-V 5,0. ~ 150 байт, каждый раз, когда эти данные отправляются.</p></li>
<li><p>Список опубликованных пакетов. ~ 7 КБ для 30 пакетов. Это сообщение отправляется только в том случае, если список пакетов обновляется с обновлением публикации, которое выполняется нечасто. При отсутствии изменений эти сведения не отправляются.</p></li>
<li><p>Сведения об использовании виртуальных приложений — около 0,25 КБ на каждое событие. Открываются и закрываются как одно событие, которое выполняется, прежде чем отправлять информацию. При отправке с помощью запланированной задачи данные отправляются на сервер только с момента последней успешной отправки. При отправке вручную с помощью командлета PowerShell есть необязательный аргумент, который определяет, нужно ли повторно отправлять данные в следующий раз — этот аргумент является <strong> DeleteOnSuccess </strong> .</p>
<p></p>
<p>Например, если у вас есть двадцать приложений и вы закрыли данные отчетов, а отчеты будут отправляться ежедневно, то типичный ежедневный трафик должен составлять примерно 0.15 KB + 20 x 0,25 КБ или около 5KB/User.</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>Можно ли планировать отчетность?</p></td>
<td align="left"><p>Да. Помимо отправки отчетов вручную с помощью командлетов PowerShell ( <strong> Send-AppvClientReport </strong> ), задачу можно запланировать таким образом, чтобы она выполнялась автоматически. Существует два способа планирования создания отчетов.</p>
<ol>
<li><p>С помощью командлетов PowerShell — <strong> Set-AppvClientConfiguration </strong> . Пример</p>
<p>Set-AppvClientConfiguration-ReportingEnabled 1-ReportingServerURL<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</a></p>
<p></p>
<p>Полный список параметров конфигурации клиента можно найти в разделе <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)"> Параметры конфигурации клиента </a> и найти следующие элементы: <strong> ReportingEnabled </strong> , <strong> ReportingServerURL </strong> , <strong> ReportingDataCacheLimit </strong> , <strong> ReportingDataBlockSize </strong> , <strong> ReportingStartTime </strong> , <strong> ReportingRandomDelay, ReportingInterval </strong> <strong> </strong> .</p>
<p></p></li>
<li><p>С помощью групповой политики. При распределении с помощью контроллера домена эти параметры совпадают с указанными выше.</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Параметры групповой политики переопределяют локальные параметры, настроенные с помощью PowerShell.</p>
</div>
<div>

</div></li>
</ol></td>
</tr>
</tbody>
</table>
 


## <a href="" id="---------app-v-5-0-client-reporting"></a> Создание отчетов о клиентах для App-V 5,0


Для использования отчетов App-V 5,0 необходимо установить и настроить клиент App-V 5,0. После установки клиента используйте командлет PowerShell **Set-AppVClientConfiguration** или **шаблон ADMX** для настройки отчетов. Командлеты функций для отчетов можно получить, перейдя по следующей ссылке и предваряя их **отчетами**. Полный список параметров конфигурации клиента см. в разделе [Параметры конфигурации клиента](about-client-configuration-settings.md). В следующем разделе приведены примеры конфигурации отчетов клиента App-V 5,0 с помощью PowerShell.

### Настройка отчетов клиента App-V с помощью PowerShell

В приведенных ниже примерах показано, как параметры PowerShell могут настраивать функции отчетов в клиенте App-V 5,0.

**Примечание.**  
Кроме того, с помощью параметров групповой политики в шаблоне App-V 5,0 ADMX можно настроить следующую задачу конфигурации. Дополнительные сведения об использовании шаблона ADMX приведены [в разделе изменение конфигурации клиента App-V 5,0 с помощью шаблона ADMX и групповой политики](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md).
 


**Чтобы включить создание отчетов и инициировать сбор данных на компьютере с клиентом App-V 5,0,** выполните указанные ниже действия.

`Set-AppVClientConfiguration –ReportingEnabled 1`

**Чтобы настроить клиент на автоматическую отправку данных на определенный сервер отчетов**, выполните указанные ниже действия.

``` syntax
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30
```

`-ReportingInterval 1 -ReportingRandomDelay 30`

В этом примере клиент настраивается на автоматическую отправку данных отчетов по URL-адресу сервера отчетов <strong> http://MyReportingServer:MyPort/ </strong> . Кроме того, данные отчетов будут отправляться ежедневно между 8:00 и 8:30 PM в зависимости от случайной задержки, созданной для сеанса.

**Чтобы ограничить размер кэша данных на клиентском компьютере,** выполните указанные ниже действия.

`Set-AppvClientConfiguration –ReportingDataCacheLimit 100`

Настройка максимального размера кэша отчетов на компьютере с клиентом App-V 5,0 и 100 МБ. Если достигнут предел кэша до отправки данных на сервер, Журнал переводится и данные при необходимости будут перезаписаны.

**Чтобы настроить размер блока данных, передаваемый по сети между клиентом и сервером**:

`Set-AppvClientConfiguration –ReportingDataBlockSize 10240`

Указывает максимальный блок данных, отправляемый клиентом в 10240 МБ.

### Типы собираемых данных

В следующей таблице представлены типы данных, которые можно собирать с помощью отчетов App-V 5,0.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Сведения о клиенте</th>
<th align="left">Сведения о пакете</th>
<th align="left">Использование приложения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Имя узла</p></td>
<td align="left"><p>Имя пакета</p></td>
<td align="left"><p>Временем начала и окончания</p></td>
</tr>
<tr class="even">
<td align="left"><p>Версия клиента App-V 5,0</p></td>
<td align="left"><p>Версия пакета</p></td>
<td align="left"><p>Состояние выполнения</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Архитектура процессора</p></td>
<td align="left"><p>Источник пакета</p></td>
<td align="left"><p>Состояние завершения работы</p></td>
</tr>
<tr class="even">
<td align="left"><p>Версия операционной системы</p></td>
<td align="left"><p>Процент кэшированных данных</p></td>
<td align="left"><p>Имя приложения</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Уровень пакета обновления</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Версия приложения</p></td>
</tr>
<tr class="even">
<td align="left"><p>Тип операционной системы</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Имя пользователя</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>Группа "соединение"</p></td>
</tr>
</tbody>
</table>
 


Клиент собирает и сохраняет эти данные в формате **XML** . Кэш данных скрыт по умолчанию и требует наличия прав администратора для открытия XML-файла.

### Отправка данных на сервер

Вы можете настроить компьютер, на котором запущен клиент App-V 5,0, для автоматической отправки данных на указанный сервер отчетов. Чтобы указать сервер, используйте командлет **Set-AppvClientConfiguration** со следующими параметрами:

-   ReportingEnabled

-   ReportingServerURL

-   ReportingStartTime

-   ReportingInterval

-   ReportingRandomDelay

После настройки предыдущих параметров необходимо создать запланированную задачу. Запланированная задача будет обращаться к серверу, указанному в параметре **ReportingServerURL** , и начнет передачу. Если вы хотите отправить данные вручную за пределами запланированного времени, используйте следующий командлет PowerShell:

`Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess`

Если сервер отчетов уже настроен, параметр **– URL** можно опустить. Кроме того, если данные должны отправляться в альтернативное расположение, укажите другой URL-адрес для переопределения настроенного **ReportingServerURL** для этого набора данных.

Параметр **-DeleteOnSuccess** указывает на то, что при успешном передаче кэш данных очищается. Если этот элемент не указан, кэш не будет очищен.

### Сбор данных вручную

Вы также можете использовать командлет **Send-AppVClientReport** , чтобы вручную собирать данные. Это решение полезно с существующим сервером отчетов или без него. В следующем списке приведены сведения о сборе данных с сервера отчетов или без него.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">С сервером отчетов</th>
<th align="left">Без сервера отчетов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Если у вас уже есть сервер отчетов App-V 5,0, создайте настраиваемое запланированное задание или сценарий. Указывает, что клиент отправляет данные в указанное расположение с нужной частотой.</p></td>
<td align="left"><p>Если у вас нет существующего сервера отчетов App-V 5,0, используйте <strong> параметр – URL-адрес </strong> для отправки данных в указанный общий доступ. Пример</p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p>В предыдущем примере данные отчетов отправляются в <strong> Расположение \MyShare\MyData/strong, которое &lt; &gt; определяется <strong> </strong> параметром-URL. После отправки данных кэш очищается.</p>
<div class="alert">
<strong>Примечание.</strong><br/><p>Если задано расположение, отличное от сервера отчетов, данные отправляются в <strong> формате XML без </strong> дополнительной обработки.</p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### Создание отчетов

Для получения сведений о отчете и создания отчетов с помощью App-V 5,0 необходимо использовать один из указанных ниже способов.

-   **Службы Microsoft SQL Server Reporting Services (SSRS)** — Microsoft SQL Server Reporting Services доступны в Microsoft SQL Server. Служба SSRS не устанавливается при установке сервера отчетов App-V 5,0. Он должен быть развернут отдельно для создания связанных отчетов.

    Для получения дополнительных сведений об использовании [служб Microsoft SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)воспользуйтесь следующей ссылкой.

-   **Написание сценариев** — вы можете создавать отчеты, используя сценарии непосредственно для базы данных отчетов App-V 5,0. Пример

    **Хранимая процедура:**

    для **spProcessClientReport** запланировано выполнение в полночь или 12:00 AM.

    Для выполнения запланированной хранимой процедуры Microsoft SQL Server необходимо, чтобы был запущен агент Microsoft SQL Server. Убедитесь, что для агента Microsoft SQL Server задано значение " **Автозагрузка**". Дополнительные сведения см. в разделе [автозапуска агента SQL Server (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045).

    Хранимая процедура также создается при использовании скриптов базы данных App-V 5,0.

Кроме того, необходимо убедиться в том, что **Максимальное количество одновременных подключений** веб-службы сервера отчетов установлено равным значению, которое может управлять сервер без воздействия на доступность. Рекомендуемое количество **одновременных подключений** для **веб-службы отчетов** — **10 000**.






## Статьи по теме


[Развертывание сервера App-V 5.0](deploying-the-app-v-50-server.md)

[Установка сервера отчетности на отдельном компьютере и подключение его к базе данных](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

 

 





