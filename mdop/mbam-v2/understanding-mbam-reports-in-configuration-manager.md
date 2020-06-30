---
title: Расшифровка отчетов MBAM в диспетчере конфигураций
description: Расшифровка отчетов MBAM в диспетчере конфигураций
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823822"
---
# Расшифровка отчетов MBAM в диспетчере конфигураций


При установке Microsoft BitLocker Administration и Monitoring (MBAM) с помощью встроенной топологии Configuration Manager, функции соответствия требованиям к оборудованию и отчетов переносятся в инфраструктуру Configuration Manager и из MBAM. При использовании топологии Configuration Manager вы запускаете отчеты из Configuration Manager, а не из MBAM, за исключением отчета аудита восстановления, доступ к которому можно получить с помощью веб-сайта администрирования и мониторинга.

Отчеты для интегрированной топологии Configuration Manager показывают соответствие требованиям BitLocker для предприятия и для отдельных компьютеров и устройств, которые MBAM управлять. Отчеты предоставляют как табличные данные, так и диаграммы и позволяют фильтровать отчеты для просмотра данных с разных точек зрения.

В этой статье описаны отчеты MBAM, которые выполняются из Configuration Manager. Сведения об отчетах MBAM для изолированной топологии можно найти в разделе [Общие сведения о MBAMх](understanding-mbam-reports-mbam-2.md).

## Доступ к отчетам в Configuration Manager


Чтобы получить доступ к компоненту отчеты в диспетчере конфигураций, откройте **консоль Configuration Manager**. Чтобы отобразить список доступных отчетов, выполните указанные ниже действия.

-   В Configuration Manager 2007 разверните узел **Управление компьютером** , а затем разверните узел **отчеты** .

-   В SystemCenter2012 ConfigurationManager в рабочей области мониторинг в разделе **Обзор**разверните узел **отчеты** и выберите пункт **отчеты**.

### Панель мониторинга соответствия требованиям для предприятия BitLocker

На панели мониторинга "соответствие требованиям" для предприятий BitLocker доступны следующие графы, которые показывают состояние соответствия требованиям BitLocker в масштабах предприятия.

-   Распространение состояния соответствия требованиям

-   Распространение ошибок, не отвечающих требованиям

-   Распределение состояния соответствия по типу диска

**Распространение состояния соответствия требованиям**

Эта круговая диаграмма показывает состояние соответствия требованиям компьютера в рамках предприятия и показывает процент компьютеров в сравнении с общим количеством компьютеров в выбранной коллекции, имеющим это состояние соответствия требованиям. Также отображается фактическое количество компьютеров с каждым состоянием. Круговая диаграмма показывает следующее состояние соответствия требованиям:

-   SDMI

-   Не соответствует требованиям

-   Освобождение от пользователя

-   Временный освобождаемый от пользователя

-   Политика не принудительно применена

-   Неизвестные — компьютеры, состояние которых сообщило об ошибке, или устройства, которые являются частью коллекции, но не сообщали о состоянии соответствия требованиям, например если они отключены от Организации.

**Распространение ошибок, не отвечающих требованиям**

Эта круговая диаграмма показывает категории компьютеров в сети, которые не соответствуют политике шифрования диска BitLocker, и показывают количество компьютеров в каждой категории. Каждая категория процентов рассчитывается на основе общего количества компьютеров, не отвечающих требованиям, в семействе.

-   Отложенное шифрование пользователя

-   Не удается найти совместимый доверенный платформенный модуль

-   Системный раздел недоступен или достаточен

-   Конфликт политики

-   Ожидание автоматической подготовки доверенного платформенного модуля

-   Произошла неизвестная ошибка

-   Нет сведений (на компьютерах, на которых не установлен клиент MBAM или у которого установлен клиент MBAM, но активация не выполнена, например, служба не работает

**Распределение состояния соответствия по типу диска**

На этой линейчатой диаграмме показано текущее состояние соответствия требованиям BitLocker по типу диска. Состояния "совместимо" и "не соответствует требованиям". Панели отображаются для несъемных дисков с данными и дисков операционной системы. Компьютеры, на которых не установлен фиксированный диск с данными, включаются и отображают значение только на панели дисков операционной системы. Диаграмма не содержит пользователей, которым было предоставлено исключение из политики шифрования диска BitLocker или из категории "нет политики".

### Отчет об соответствиях требованиям для предприятий BitLocker

В этом отчете выводятся сведения об общем соответствии с требованиями к BitLocker в рамках предприятия для коллекции компьютеров, предназначенных для использования BitLocker.

**Поля отчета о соответствии требованиям в BitLocker для предприятий**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя столбца</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Управляемые компьютеры</p></td>
<td align="left"><p>Количество компьютеров, которым MBAM управлять.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Соответствия требованиям</p></td>
<td align="left"><p>Процент соответствия требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% Не соответствует требованиям</p></td>
<td align="left"><p>Процент несоответствующих требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Неизвестное соответствие требованиям</p></td>
<td align="left"><p>Процент компьютеров, состояние соответствия которых неизвестно.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% Исключении</p></td>
<td align="left"><p>Процент компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Без исключения</p></td>
<td align="left"><p>Процент компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SDMI</p></td>
<td align="left"><p>Процент соответствия требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Не соответствует требованиям</p></td>
<td align="left"><p>Процент несоответствующих требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Неизвестное соответствие</p></td>
<td align="left"><p>Процент компьютеров, состояние соответствия которых неизвестно.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Облагаемый</p></td>
<td align="left"><p>Общее количество компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Без исключения</p></td>
<td align="left"><p>Общее количество компьютеров без исключения из требований шифрования BitLocker.</p></td>
</tr>
</tbody>
</table>

 

**Отчет "сведения о соответствии требованиям в корпоративной среде BitLocker" — состояния соответствия требованиям**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Состояние соответствия требованиям</th>
<th align="left">Исключение</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Несоответствующих</p></td>
<td align="left"><p>Не исключено</p></td>
<td align="left"><p>Компьютер не соответствует политике в соответствии с указанной политикой.</p></td>
</tr>
<tr class="even">
<td align="left"><p>SDMI</p></td>
<td align="left"><p>Не исключено</p></td>
<td align="left"><p>Компьютер соответствует требованиям указанной политики.</p></td>
</tr>
</tbody>
</table>

 

### Сводный отчет о соответствиях требованиям для предприятий BitLocker

Этот тип отчета используется для отображения сведений о соответствии общего соответствия требованиям BitLocker для всего предприятия и для отображения соответствия требованиям для отдельных компьютеров, которые находятся в семействе компьютеров, предназначенных для использования BitLocker.

**Поля сводного отчета о соответствиях требованиям для предприятий BitLocker**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя столбца</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Управляемые компьютеры</p></td>
<td align="left"><p>Количество компьютеров, которым MBAM управлять.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Соответствия требованиям</p></td>
<td align="left"><p>Процент соответствия требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% Не соответствует требованиям</p></td>
<td align="left"><p>Процент несоответствующих требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Неизвестное соответствие требованиям</p></td>
<td align="left"><p>Процент компьютеров, состояние соответствия которых неизвестно.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% Исключении</p></td>
<td align="left"><p>Процент компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="even">
<td align="left"><p>% Без исключения</p></td>
<td align="left"><p>Процент компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SDMI</p></td>
<td align="left"><p>Процент соответствия требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Не соответствует требованиям</p></td>
<td align="left"><p>Процент несоответствующих требованиям компьютеров в масштабах предприятия.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Неизвестное соответствие</p></td>
<td align="left"><p>Процент компьютеров, состояние соответствия которых неизвестно.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Облагаемый</p></td>
<td align="left"><p>Общее количество компьютеров, исключаемых из требования шифрования BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Без исключения</p></td>
<td align="left"><p>Общее количество компьютеров без исключения из требований шифрования BitLocker.</p></td>
</tr>
</tbody>
</table>

 

**Сводный отчет о соответствиях требованиям для предприятий BitLocker — сведения о компьютере**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя столбца</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Имя компьютера</p></td>
<td align="left"><p>Указанное пользователем DNS-имя компьютера, которое управляется MBAM.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Доменное имя</p></td>
<td align="left"><p>Полное доменное имя, в котором находится клиентский компьютер и управляется MBAM.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Состояние соответствия требованиям</p></td>
<td align="left"><p>Общее состояние соответствия требованиям компьютера, управляемого с помощью MBAM. Допустимые состояния соответствуют требованиям и не соответствуют требованиям. Обратите внимание, что состояние соответствия для каждого диска (приведенная ниже таблица) может указывать на разные состояния соответствия требованиям. Однако это поле представляет состояние соответствия требованиям в соответствии с указанной политикой.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Исключение</p></td>
<td align="left"><p>Состояние, указывающее на то, является ли пользователь исключенным или неисключением из политики BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Пользователи устройств</p></td>
<td align="left"><p>Пользователь устройства.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Сведения о статусе соответствия требованиям</p></td>
<td align="left"><p>Сообщения об ошибках и состоянии соответствия требованиям компьютера согласно указанной политике.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Последний контакт</p></td>
<td align="left"><p>Дата и время последнего обращения компьютера к серверу для отправки отчета о состоянии соответствия требованиям. Частота контактов настраивается (см. раздел Параметры политики MBAM).</p></td>
</tr>
</tbody>
</table>

 

### Отчет о соответствии компьютера BitLocker

Этот тип отчета используется для сбора сведений, относящихся к компьютеру. Отчет о соответствии компьютера содержит подробные сведения о шифровании каждого диска (операционной системы и фиксированных дисков с данными) на компьютере, а также сведения о политике, применяемой к каждому типу дисков на компьютере. Чтобы просмотреть сведения о каждом диске, разверните элемент имя компьютера.

**Примечание**  Состояние шифрования тома съемных данных не отображается в отчете.

 

**Отчет о соответствии компьютера BitLocker — поля сведений о компьютере**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя столбца</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Имя компьютера</p></td>
<td align="left"><p>Указанное пользователем DNS-имя компьютера, которое управляется MBAM.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Доменное имя</p></td>
<td align="left"><p>Полное доменное имя, в котором находится клиентский компьютер и управляется MBAM.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Тип компьютера</p></td>
<td align="left"><p>Тип компьютера. Допустимые типы не являются переносимыми и переносимыми.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Операционная система</p></td>
<td align="left"><p>Тип операционной системы на клиентском компьютере с управляемым MBAM.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Общее соответствие требованиям</p></td>
<td align="left"><p>Общее состояние соответствия требованиям компьютера, управляемого с помощью MBAM. Допустимые состояния соответствуют требованиям и не соответствуют требованиям. Обратите внимание, что состояние соответствия для каждого диска (приведенная ниже таблица) может указывать на разные состояния соответствия требованиям. Однако это поле представляет состояние соответствия требованиям в соответствии с указанной политикой.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Соответствие требованиям операционной системы</p></td>
<td align="left"><p>Состояние соответствия требованиям операционной системы, управляемой MBAM. Допустимые состояния соответствуют требованиям и не соответствуют требованиям.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Соответствие фиксированному диску с данными</p></td>
<td align="left"><p>Состояние соответствия фиксированному диску с данными, управляемому с помощью MBAM. Допустимые состояния соответствуют требованиям и не соответствуют требованиям.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Дата последнего обновления</p></td>
<td align="left"><p>Дата и время последнего обращения компьютера к серверу для отправки отчета о состоянии соответствия требованиям. Частота контактов настраивается (см. раздел Параметры политики MBAM).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Исключение</p></td>
<td align="left"><p>Состояние, указывающее на то, является ли пользователь исключенным или неисключением из политики BitLocker.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Исключенный пользователь</p></td>
<td align="left"><p>Пользователь, исключаемый из политики BitLocker.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Дата освобождения</p></td>
<td align="left"><p>Дата, когда был предоставлен доступ к исключению.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Сведения о статусе соответствия требованиям</p></td>
<td align="left"><p>Сообщения об ошибках и состоянии соответствия требованиям компьютера согласно указанной политике.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Стойкость шифра политики</p></td>
<td align="left"><p>Стойкость шифра, выбранная администратором в течение MBAM политики. (например, 128-бит с диффузором).</p></td>
</tr>
<tr class="even">
<td align="left"><p>Политика: диск операционной системы</p></td>
<td align="left"><p>Указывает, требуется ли шифрование для O/S и соответствующего типа предохранителя.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Политика: несъемный диск с данными</p></td>
<td align="left"><p>Указывает, требуется ли шифрование для жесткого диска.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Изготовитель</p></td>
<td align="left"><p>Название изготовителя компьютера, которое отображается в BIOS компьютера.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Модель</p></td>
<td align="left"><p>Название модели изготовителя компьютера, которое отображается в BIOS компьютера.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Пользователи устройств</p></td>
<td align="left"><p>Известные пользователи на компьютере, управляемом с помощью MBAM.</p></td>
</tr>
</tbody>
</table>

 

**Отчет о соответствии компьютера BitLocker — поля громкости компьютера**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Имя столбца</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Буква диска</p></td>
<td align="left"><p>Буква диска компьютера, назначенная пользователем на определенный диск.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Тип диска</p></td>
<td align="left"><p>Тип диска. Допустимые значения: диск операционной системы и фиксированный диск с данными. Это физические диски, а не логические тома.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Стойкость шифра</p></td>
<td align="left"><p>Стойкость шифра, выбранная администратором в течение MBAM политики.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Типы предохранителей</p></td>
<td align="left"><p>Тип предохранителя, выбранный с помощью политики, используемой для шифрования операционной системы или фиксированного тома. Допустимые типы предохранителей в операционной системе являются доверенными платформенными модулями или TPM + PIN-кодом и для фиксированного тома данных — Password (пароль).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Состояние предохранителя</p></td>
<td align="left"><p>Указывает на то, что на компьютере, управляемом MBAM, включен тип предохранителя, указанный в политике. Допустимые состояния: ON и OFF.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Состояние шифрования</p></td>
<td align="left"><p>Состояние шифрования диска. Допустимые состояния шифруются, а не шифруются и шифруются.</p></td>
</tr>
</tbody>
</table>

 

## Статьи по теме


[Использование MBAM с диспетчером конфигураций](using-mbam-with-configuration-manager.md)

 

 




