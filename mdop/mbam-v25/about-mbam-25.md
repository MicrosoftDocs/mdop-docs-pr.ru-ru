---
title: О программе MBAM 2.5
description: О программе MBAM 2.5
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824212"
---
# О программе MBAM 2.5


Администрирование и мониторинг Microsoft BitLocker (MBAM) 2,5 обеспечивает упрощенный интерфейс администрирования для шифрования диска BitLocker. BitLocker поддерживает улучшенную защиту от кражи данных и уязвимости данных для потерянных или похищенных компьютеров. BitLocker шифрует все данные, хранящиеся на томах и дисках операционной системы Windows, а также на настроенных дисках данных.

## Общие сведения о MBAM


MBAM 2,5 обладает следующими возможностями:

-   позволяет администраторам автоматизировать процедуру шифрования томов на клиентских компьютерах в организации;

-   позволяет специалистам по безопасности быстро определять состояние соответствия требованиям отдельных компьютеров или всей организации;

-   обеспечивает возможность централизованного составления отчетности и управления оборудованием с использованием Microsoft System Center Configuration Manager;

-   Сокращает рабочую нагрузку на службу поддержки, чтобы помочь конечным пользователям использовать ПИН-код BitLocker и ключи восстановления.

-   позволяет конечным пользователям восстанавливать зашифрованные устройства независимо, используя портал самообслуживания;

-   Позволяет подвергать аудиту безопасности доступ к восстановлению сведений о ключе.

-   позволяет пользователям Windows Корпоративная продолжать работать в любом месте, не беспокоясь о защите данных организации;

MBAM применяет параметры политики шифрования BitLocker, заданные для Организации, отслеживает соответствие клиентских компьютеров этим политикам и сообщает о состоянии шифрования компьютеров предприятия и индивидуальных пользователей. Кроме того, MBAM позволяет получить доступ к сведениям о ключе восстановления, когда пользователь забыл свой PIN-код или пароль, а также при изменении BIOS или загрузочных записей.

Управление BitLocker может заинтересовать следующие группы: MBAM

-   Администраторы, ИТ-специалисты и руководителей соответствия требованиям, ответственные за обеспечение того, что конфиденциальные данные не будут закрыты без авторизации.

-   Администраторы, ответственные за безопасность компьютеров в удаленных и филиалах

-   Администраторы, ответственные за клиентские компьютеры под управлением Windows

**Примечание**  BitLocker не подробно описан в этой MBAM документации. Дополнительные сведения можно найти в разделе [Обзор шифрования диска BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=225013).

 

## <a href="" id="what-s-new-in-mbam-2-5"></a>Новые возможности MBAM 2,5


В этом разделе описаны новые возможности в MBAM 2,5.

### Поддержка Microsoft SQL Server 2014

MBAM добавляет поддержку для Microsoft SQL Server 2014 в дополнение к тому же программному обеспечению, которое поддерживается в более ранних версиях MBAM.

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> Шаблоны групповой политики MBAM скачаны отдельно

Шаблоны групповой политики MBAM должны быть загружены отдельно из установки MBAM. В предыдущих версиях MBAM установщик MBAM включил шаблон политики MBAM, который содержал необходимые MBAM объекты групповой политики (GPO), которые определяют параметры MBAM реализации для шифрования диска BitLocker. Эти GPO были удалены из MBAM установщика. Теперь вы можете скачать объекты групповой [политики (ADMX)](https://go.microsoft.com/fwlink/p/?LinkId=393941) и скопировать их на сервер или рабочую станцию, прежде чем приступить к установке клиента MBAM. Вы можете скопировать шаблоны групповой политики на любой сервер или рабочую станцию, на которой работает поддерживаемая версия операционной системы Windows Server или Windows.

**Важно!**  Не изменяйте параметры групповой политики в разделе " **Шифрование диска BitLocker** " или MBAM будут работать неправильно. При настройке параметров групповой политики на узле **MDOP MBAM (Управление BitLocker)** MBAM автоматически настраивает параметры шифрования диска для BitLocker.

 

Файлы шаблонов, которые необходимо скопировать на сервер или на рабочую станцию:

-   BitLockerManagement. ADML

-   BitLockerManagement. ADMX

-   BitLockerUserManagement. ADML

-   BitLockerUserManagement. ADMX

Скопируйте файлы шаблонов в то место, которое наилучшим образом соответствует вашим потребностям. Для файлов, относящихся к определенному языку, которые необходимо скопировать в папку для определенного языка, для просмотра файлов требуется консоль управления групповыми политиками.

- Чтобы установить файлы шаблонов локально на сервер или рабочую станцию, скопируйте их в одно из указанных ниже расположений.

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">Тип файла</th>
  <th align="left">Расположение файла</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>язык, не зависящий от языка (ADMX)</p></td>
  <td align="left"><p><em>% SystemRoot% </em> \policyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>специфичный для определенного языка (ADML)</p></td>
  <td align="left"><p><em>% SystemRoot% </em> \policyDefinitions [ <em> MUIculture </em> ] (например, файл в формате для английского языка (США) будет храниться в <em> каталоге% systemroot% &lt; /EM &gt; policyDefinitions\en-US)</p></td>
  </tr>
  </tbody>
  </table>

     

- Чтобы шаблоны были доступны всем администраторам групповых политик в домене, скопируйте файлы в одно из указанных ниже расположений на контроллере домена.

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">Тип файла</th>
  <th align="left">Расположение файла контроллера домена</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>Язык, не зависящий от языка (ADMX)</p></td>
  <td align="left"><p><em>% SystemRoot% </em> sysvol\domain\policies\PolicyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>Специфичный для определенного языка (ADML)</p></td>
  <td align="left"><p><em>% SystemRoot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] (например, файл, зависящий от английского языка, будет храниться в <em> папке% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions\en-US)</p></td>
  </tr>
  </tbody>
  </table>

     

Дополнительные сведения о файлах шаблонов можно найти [в статье Управление файлами ADMX с](https://go.microsoft.com/fwlink/?LinkId=392818)пошаговыми инструкциями.

### Возможность применять политики шифрования для операционной системы и несъемных дисков с данными

MBAM 2.5 позволяет применять политики шифрования на операционных системах и фиксированных дисках с данными для компьютеров в вашей организации, а также ограничивать количество дней, в течение которых конечные пользователи могут запрашивать отсрочку требования для обеспечения соответствия требованиям политик шифрования MBAM.

Чтобы включить настройку принудительного применения политики шифрования, для дисков операционной системы и несъемных дисков с данными была добавлена новая настройка групповой политики, называемая параметрами применения политики шифрования. Эта политика описана в приведенной ниже таблице.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Параметр групповой политики</th>
<th align="left">Описание</th>
<th align="left">Узел групповой политики, используемый для настройки этого параметра</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Параметры применения политики шифрования (диск операционной системы)</p></td>
<td align="left"><p>Для этого параметра с помощью параметра <strong> Настройте количество дней льготного периода несоответствия для дисков операционной системы </strong> , чтобы настроить льготный период.</p>
<p>Льготный период определяет количество дней, в течение которых конечные пользователи могут откладывать соответствие требованиям с помощью политик MBAM для жесткого диска операционной системы после того, как диск впервые обнаружен как несоответствующий.</p>
<p>По истечении настроенного льготного периода пользователи не могут откладывать необходимые действия или запрашивать исключение от него.</p>
<p>Если требуется вмешательство пользователя (например, при использовании доверенного платформенного модуля (TPM) + PIN-кода или с помощью предохранителя пароля), появится диалоговое окно, и пользователи не смогут закрыть его, пока не предоставит нужные сведения. Если предохранитель является исключительно TPM, шифрование начинается немедленно в фоновом режиме без ввода данных пользователем.</p>
<p>Пользователи не могут запрашивать исключения с помощью мастера шифрования BitLocker. Вместо этого они должны обратиться в службу технической поддержки или использовать любой процесс, используемый их организациями для запросов на освобождение.</p></td>
<td align="left"><p>Политики конфигурации компьютера: &gt; &gt; Административные шаблоны &gt; компоненты &gt; Windows MDOP MBAM (Управление BitLocker) &gt; диск операционной системы</p></td>
</tr>
<tr class="even">
<td align="left"><p>Параметры принудительного применения политики шифрования (несъемные диски с данными)</p></td>
<td align="left"><p>Для этого параметра с помощью параметра <strong> Настройте количество дней льготного периода несоответствия для фиксированных дисков </strong> , чтобы настроить льготный период.</p>
<p>Льготный период определяет количество дней, в течение которых конечные пользователи могут откладывать соответствие требованиям с помощью политик MBAM для фиксированных дисков, после того как диск впервые обнаружен как несоответствующий.</p>
<p>Льготный период начинается, когда фиксированный диск определен как несоответствующий. Если вы используете автоматическое снятие блокировки, политика не будет применяться, пока диск операционной системы не станет совместимым. Тем не менее, если вы не используете автоматическое снятие блокировки, шифрование фиксированного диска с данными может начаться, прежде чем диск операционной системы полностью шифруется.</p>
<p>По истечении настроенного льготного периода пользователи не могут откладывать необходимые действия или запрашивать исключение от него. Если требуется вмешательство пользователя, появится диалоговое окно, и пользователи не смогут закрыть его, пока он не предоставит нужные сведения.</p></td>
<td align="left"><p>Политики конфигурации компьютера: &gt; &gt; Административные шаблоны &gt; компоненты Windows &gt; MBAM (Управление BitLocker) &gt; съемный диск</p></td>
</tr>
</tbody>
</table>

 

### Возможность предоставления URL-адреса в мастере шифрования диска BitLocker для указания на политику безопасности

Новый параметр групповой политики: **URL-адрес ссылки на политику безопасности**позволяет настроить URL-адрес, который будет использоваться для конечных пользователей в качестве ссылки, которая называется **политикой безопасности компании**. Эта ссылка появится в том случае, если MBAM предложит пользователям зашифровать том.

Если вы включаете этот параметр политики, вы можете настроить URL-адрес ссылки на **политику безопасности компании** . Если вы отключаете или не настраиваете этот параметр политики, ссылка " **Политика безопасности Организации** " не отображается для пользователей.

Параметр "Новая групповая политика" находится на следующем узле GPO: **политики конфигурации компьютера** . &gt; **Policies** &gt; **Административные шаблоны** &gt; **компоненты Windows** &gt; **MBAM (Управление BitLocker) &gt; MDOP**.

### Поддержка ключей восстановления, совместимых с FIPS

MBAM 2.5 поддерживает ключи восстановления, совместимые со стандартом FIPS, на устройствах под управлением операционной системы Windows 8.1. Ключ восстановления не соответствует требованиям FIPS в более ранних версиях Windows. Это расширение улучшает процесс восстановления диска в организациях, требующих соответствия требованиям FIPS, так как позволяет конечным пользователям использовать портал самообслуживания и веб-сайт администрирования и наблюдения (служба поддержки) для восстановления дисков в случае утери ПИН-кода или пароля, а также для блокировки компьютеров. Новая функция соответствия требованиям FIPS не распространяется на предохранители пароля.

Чтобы включить соответствие требованиям FIPS в вашей организации, необходимо настроить параметры групповой политики для федеральной обработки информации (FIPS). Инструкции по настройке можно найти в разделе [Параметры групповой политики BitLocker](https://go.microsoft.com/fwlink/?LinkId=393560).

Для клиентских компьютеров, использующих операционные системы Windows8 или Windows7 без [установленного исправления BitLocker](https://support.microsoft.com/kb/3015477), ИТ-администраторы продолжат использовать предохранитель агента восстановления данных (DRA) в средах, совместимых с FIPS. Сведения о DRA см. в разделе [использование агентов восстановления данных с помощью BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).

Чтобы скачать и установить исправление BitLocker для Windows 7 и Windows 8, ознакомьтесь с [пакетом исправлений 2 для администрирования BitLocker и мониторинга 2,5](https://support.microsoft.com/kb/3015477) .

### Поддержка развертываний с высокой степенью доступности

MBAM поддерживает следующие сценарии высокой доступности в дополнение к стандартным топологиям интеграции двух серверов и Configuration Manager:

-   Группы доступности SQL Server AlwaysOn

-   Кластеризация SQL Server

-   Балансировка сетевой нагрузки (NLB)

-   Зеркальное отображение SQL Server

-   Резервное копирование службы теневого копирования тома (VSS)

Подробнее об этих функциях смотрите в разделе [планирование MBAM 2,5 высокой доступности](planning-for-mbam-25-high-availability.md).

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a>Изменилось управление ролями для администрирования и веб-сайта наблюдения

В MBAM 2.5 для управления ролями, которые предоставляют права доступа к веб-сайту администрирования и мониторинга, необходимо создать группы безопасности в доменных службах Active Directory (ADDS). Роли позволяют пользователям, которые относятся к определенным группам безопасности, выполнять различные задачи на веб-сайте, например просматривать отчеты или помогать пользователям восстанавливать зашифрованные диски. В предыдущих версиях MBAM для управления ролями использовалась локальная группа.

В MBAM 2.5 термин "роли" заменяет термин "роли администратора", который использовался в более ранних версиях MBAM. Кроме того, в MBAM 2.5 роль "Администраторы системы" была удалена.

В следующей таблице перечислены группы безопасности, которые необходимо создать в доменных СЛУЖБах Active Directory. Вы можете использовать любое имя для групп безопасности.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Роль</th>
<th align="left">Права доступа для этой роли на веб-сайте администрирования и мониторинга</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Пользователи службы поддержки MBAM</p></td>
<td align="left"><p>Предоставляет доступ к разделу Управление областями восстановления доверенных платформенных устройств и дисков на веб-сайте администрирования и мониторинга MBAM. Пользователи, у которых есть доступ к этим областям, должны заполнить все поля при использовании любой области.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Пользователи отчетов MBAM</p></td>
<td align="left"><p>Предоставляет доступ к отчетам на веб-сайте администрирования и наблюдения.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM опытных пользователей службы поддержки</p></td>
<td align="left"><p>Предоставляет доступ ко всем областям на веб-сайте администрирования и наблюдения. Пользователи в этой группе должны вводить только ключ восстановления, а не домен и имя пользователя конечного пользователя, при помощи которых пользователи будут восстанавливать свои диски. Если пользователь является членом группы "Пользователи службы поддержки MBAM" и "Пользователи расширенной справочной службы MBAM", то разрешения группы "Пользователи расширенной справочной службы" переопределяют разрешения на доступ к группе "MBAM" для пользователей службы поддержки.</p></td>
</tr>
</tbody>
</table>

 

После создания групп безопасности в разделе "Добавление" Назначьте пользователям и (или) группам соответствующую группу безопасности, чтобы обеспечить соответствующий уровень доступа к веб-сайту администрирования и мониторинга. Чтобы разрешить отдельным пользователям ролей доступ к веб-сайту администрирования и наблюдения, необходимо также указать каждую группу безопасности при настройке веб-сайта администрирования и мониторинга.

### Командлеты Windows PowerShell для настройки функций сервера MBAM

Командлеты Windows PowerShell для MBAM 2.5 позволяют настраивать и управлять функциями сервера MBAM. Каждый компонент имеет соответствующий командлет Windows PowerShell, который можно использовать для включения или отключения функций, а также для получения сведений о компоненте.

Необходимые условия и необходимые условия для использования Windows PowerShell приведены в разделе [Настройка функций сервера MBAM 2,5 с помощью Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).

**Загрузка справки по MBAM 2,5 для командлетов Windows PowerShell после установки серверного программного обеспечения MBAM**

1.  Откройте Windows PowerShell или интегрированную среду сценариев Windows PowerShell (ISE).

2.  Введите **Update-Help-Module Microsoft. MBAM**.

Справка по Windows PowerShell для MBAM доступна в следующих форматах:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Формат справки Windows PowerShell</th>
<th align="left">Дополнительные сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>В командной строке Windows PowerShell введите <strong> </strong> &lt; <em> командлет Get-Help</em>&gt;</p></td>
<td align="left"><p>Чтобы загрузить последние командлеты Windows PowerShell, следуйте инструкциям, приведенным в предыдущем разделе о том, как загрузить справку Windows PowerShell для MBAM.</p></td>
</tr>
<tr class="even">
<td align="left"><p>На веб-страницах TechNet.</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>В центре загрузки как файл Word. docx</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>В центре загрузки в виде PDF-файла</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### Поддержка ПИН-кодов и расширенных контактов и возможность предотвращения последовательного и повторяющегося символа

**Разрешить расширенные контакты для параметра групповой политики автозагрузки**

Параметр групповой политики, **разрешающий Расширенные ПИН-коды для запуска**, позволяет настроить использование расширенных ПИН-кодов при запуске BitLocker. Улучшенные ПИН-коды запуска позволяют пользователям вводить клавиши на полных клавиатурах, в том числе прописные и строчные буквы, символы, цифры и пробелы. Если вы включаете этот параметр политики, все новые ПИН-коды запуска BitLocker, заданные в качестве контактов, будут расширены. Если вы отключаете или не настраиваете этот параметр политики, расширенные контакты использовать нельзя.

Не все компьютеры поддерживают ввод расширенных контактов в среде предзагрузочной среды выполнения (PXE). Прежде чем включать этот параметр групповой политики для Организации, запустите проверку системы во время процесса настройки BitLocker, чтобы убедиться, что BIOS компьютера поддерживает использование полной клавиатуры в среде PXE. Дополнительные сведения можно найти в разделе [Планирование требований к групповой политике MBAM 2,5](planning-for-mbam-25-group-policy-requirements.md).

**Флажок "Запрашивать ПИН-коды только для ASCII"**

Кроме того, параметр **Allowed Pins для** групповой политики автозагрузки включает в себя флажок **требовать ПИН-коды только для ASCII** . Если компьютеры в вашей организации не поддерживают использование полной клавиатуры в PXE, вы можете включить параметр **Allowed Pins для** групповой политики, а затем установить флажок **требовать ввода ПИН-кодов только** для тех, для которых расширенные контакты должны использовать только печатаемые символы ASCII.

**Принудительное использование непоследовательных и неповторяющихся знаков**

MBAM 2.5 предотвращает создание контактных данных для конечных пользователей, состоящих из повторяющихся номеров (например, 1111) или последовательных номеров (например, 1234). Если конечные пользователи пытаются ввести пароль с тремя или более повторяющимися или последовательными числами, мастер шифрования диска BitLocker отобразит сообщение об ошибке и не позволит пользователям вводить PIN-код с запрещенными символами.

### Добавление сертификата DRA в отчет о соответствии требованиям компьютера BitLocker

Новый тип предохранителя, сертификат агента восстановления данных (DRA), добавлен в отчет о соответствии компьютера BitLocker в Configuration Manager. Этот тип предохранителя применим к дискам операционной системы и отображается в разделе **тома компьютера** в столбце **типы предохранителей** .

### Поддержка развертывания с несколькими лесами

MBAM 2,5 поддерживает следующие типы развертываний с несколькими лесами:

-   Один лес с одним доменом

-   Один лес с одним деревом и несколькими доменами

-   Один лес с несколькими деревьями и непересекающимися пространствами имен

-   Несколько лесов в топологии центрального леса

-   Несколько лесов в топологии леса ресурсов

Не поддерживается миграция лесов (от одного до нескольких, с разными ресурсами в лесу и т. д.) или обновление или переход на предыдущую версию.

Для развертывания MBAM в нескольких лесах используются следующие требования:

-   Лес должен работать на поддерживаемых версиях Windows Server.

-   Требуется двухстороннее или одностороннее отношение доверия. Односторонние доверительные отношения требуют, чтобы домен сервера доверял домену клиента. Другими словами, домен сервера указывает на домен клиента.

### Поддержка зашифрованных жестких дисков в клиенте MBAM

MBAM поддерживает BitLocker на зашифрованных жестких дисках, отвечающих требованиям к спецификации TCG для Opalis и стандарту IEEE 1667. Если на этих устройствах включена функция BitLocker, она будет создавать ключи и выполнять функции управления на зашифрованном диске. Более подробную информацию вы видите на [жестком диске с шифрованием](https://technet.microsoft.com/library/hh831627.aspx) .

## Получение технологий для MDOP


MBAM является частью пакета оптимизации рабочего стола Майкрософт (MDOP). MDOP является частью программы Software Assurance (Майкрософт). Дополнительные сведения о программе Microsoft Software Assurance и о том, как приобрести MDOP, приведены в [статье как получить MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).

## <a href="" id="---------mbam-2-5-release-notes"></a> Заметки о выпуске MBAM 2,5


Чтобы получить дополнительные сведения и последние новости, не включенные в эту документацию, ознакомьтесь с [заметками о выпуске для MBAM 2,5](release-notes-for-mbam-25.md).

## У вас есть предложение MBAM?
- Отправьте свой отзыв [здесь](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub). 
- Для MBAM проблемы используйте [MBAM Форум TechNet](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).

## Статьи по теме


[Microsoft BitLocker Administration and Monitoring 2.5](index.md)

[Начало работы с MBAM 2.5](getting-started-with-mbam-25.md)

 

 





