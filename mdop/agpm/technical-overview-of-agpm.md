---
title: Технический обзор AGPM
description: Технический обзор AGPM
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818299"
---
# Технический обзор AGPM


Расширенное управление групповыми политиками Microsoft — это клиентское и серверное приложение. Сервер политики доменных групп (в том есть не в архиве), который создается с помощью РАСШИРЕНного использования файловой системы сервера. Администраторы групповых политик используют оснастку РАСШИРЕНного управления групповыми политиками для работы с объектами групповой политики на сервере, на котором размещается Архив. Общие сведения об элементах управления групповыми политиками и связанных с ними элементах, о том, как они хранят объекты групповой политики в файловой системе, а также о том, как разрешения на доступ к действиям для каждой роли пользователей могут улучшить эффективность администраторов групповых политик.

## Терминология


Ниже описаны основные термины РАСШИРЕНного использования.

-   **Клиент с расширенными политиками.** Компьютер, на котором запущена оснастка расширенного управления групповыми политиками (GPMC), и администраторы групповых политик управляют объектами групповой политики.

-   **Оснастка "расширенная работа с групповыми политиками"** Программный компонент расширенного управления групповыми политиками, установленный на клиентах с расширенным управлением групповыми политиками.

-   **Сервер расширенного на:** Сервер, на котором запущена служба управления групповыми политиками и управляющий Архив. Каждый сервер расширенного управления групповыми политиками может управлять только одним архивом, но один из них может управлять архивными данными для нескольких доменов в одном архиве. Архив может быть размещен на компьютере, отличном от сервера с расширенным управлением групповыми политиками.

-   **Служба расширенного обслуживания:** Программный компонент, который выполняется на сервере РАСШИРЕНного использования в качестве службы. Служба управляет объектами групповой политики в архиве и в рабочей среде в этом лесу.

-   **Архивировать:** В разделе управления групповыми политиками — центральное хранилище, содержащее управляемые объекты групповой политики, которые управляются с помощью соответствующего сервера РАСШИРЕНных данных, в дополнение к журналу для каждого из этих объектов групповой политики. Сюда входят все предыдущие контрольные версии каждого объекта групповой политики. Архив состоит из архивного индекса и связанных с ними архивных данных, которые могут содержать данные для GPO в нескольких доменах. Архив может быть размещен на компьютере, отличном от сервера с расширенным управлением групповыми политиками.

-   **Управляемый объект групповой политики:** Объект групповой политики, управляемый с помощью расширенного управления групповыми политиками. Управление групповыми политиками управляет журналом и разрешениями управляемых объектов групповой политики, которые хранятся в архиве.

-   **Неконтрольный объект групповой политики:** Объект групповой политики в рабочей среде для домена и не управляется с помощью расширенного управления групповыми политиками.

## Как выполняется установка, создание и влияние на


На сервере с РАСШИРЕНным интерфейсом, программа установки РАСШИРЕНного обновления Windows устанавливает службу РАСШИРЕНного включения. РАСШИРЕНная аналитика не изменяет службу каталогов Active Directory® или схему. По умолчанию файлы программного сервера с РАСШИРЕНным языком и установленными в%ProgramFiles%\\Microsoft\\AGPM\\Server. Вы можете установить на контроллере домена службу расширенного управления групповыми политиками, если это необходимо; Тем не менее, мы рекомендуем установить службу РАСШИРЕНного разрешения на рядовой сервер.

В клиенте расширенного управления групповыми политиками программа установки расширенного управления групповыми политиками устанавливает оснастку " **Управление** групповыми политиками", добавляя к каждому домену, который отображается в GPMC, папку По умолчанию файлы клиентской программы с РАСШИРЕНным управлением разрядом установлены в%ProgramFiles%\\Microsoft\\AGPM\\Client.

В таблице 1 описаны элементы, которые вы устанавливаете и создаете с помощью РАСШИРЕНного вида, и компоненты операционной системы, влияющие на работу с помощью РАСШИРЕНного вида.

**Таблица 1: элементы, установленные, созданные и затрагиваемые РАСШИРЕНным пользователем.**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Элемент</th>
<th align="left">Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Служба РАСШИРЕНного обслуживания</p></td>
<td align="left"><p>Служба РАСШИРЕНного выполнения операций выполняется на сервере с расширенным управлением групповыми политиками. Служба управляет архивом, который включает автономные объекты групповой политики, а также управляемые объекты групповой политики в рабочей среде. По умолчанию в качестве конфигурации службы РАСШИРЕНной настройки используется следующее:</p>
<ul>
<li><p><strong>Имя службы: </strong> Служба расширенного</p></li>
<li><p><strong>Отображаемое имя: </strong> Служба расширенного просмотра</p></li>
<li><p><strong>Путь к исполняемому файлу: </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</p></li>
<li><p><strong>Автозапуск: </strong> Автоматический</p></li>
<li><p><strong>Вход в </strong> учетную запись службы расширенного управления групповыми политиками, заданной во время установки сервера с расширенным доступом, который можно изменить с помощью <strong> программ и компонентов </strong> на <strong> панели управления </strong> .</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Архивация в РАСШИРЕНном</p></td>
<td align="left"><p>По умолчанию в расширенном управлении групповыми политиками создается архив на%ProgramData%\Microsoft\AGPM на сервере РАСШИРЕНного включения. Архив предоставляет хранилище для автономных объектов групповой политики и может хранить несколько версий каждого объекта групповой политики. Изменения, вносимые в параметры РАСШИРЕНного использования групповой политики в архиве, не влияют на производственную среду, пока администратор и утверждающий не развернут объект групповой политики в рабочей среде и не связывает GPO с подразделением (OU).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Брандмауэр Windows</p></td>
<td align="left"><p>Во время установки с помощью РАСШИРЕНного ключа политики для Windows можно настроить для него связь с сервером с расширенным управлением групповыми политиками. Правило брандмауэра Windows по умолчанию имеет следующие значения:</p>
<ul>
<li><p><strong>Name (имя): </strong> Служба расширенного обслуживания</p></li>
<li><p><strong>Действие: </strong> Разрешить подключение</p></li>
<li><p><strong>Программы: </strong> все программы, отвечающие заданным условиям</p></li>
<li><p><strong>Тип протокола: </strong> TCP</p></li>
<li><p><strong>Локальный порт: </strong> 4600</p></li>
<li><p><strong>Удаленный порт: </strong> все порты</p></li>
<li><p><strong>Локальный IP-адрес: </strong> любой</p></li>
<li><p><strong>Удаленный IP-адрес: </strong> любой</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Сервер электронной почты</p></td>
<td align="left"><p>Функция РАСШИРЕНного доступа к данным использует протокол SMTP для отправки запросов по электронной почте на адреса, настроенные на <strong> вкладке "Делегирование домена </strong> ". Например, когда редактор запрашивает создание объекта групповой политики, он уведомляет каждый адрес электронной почты, указанный на <strong> вкладке "Делегирование домена </strong> ".</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Оснастка РАСШИРЕНного режима</p></td>
<td align="left"><p>Оснастка управления ГРУППОВыми политиками для GPMC работает на клиентах с РАСШИРЕНными правами и используется администраторами групповых политик для управления объектами групповой политики. Эта оснастка появится в консоли управления групповыми политиками в качестве <strong> папки для контроля изменений </strong> в каждом домене.</p></td>
</tr>
</tbody>
</table>

 

### Дополнительные ссылки

Дополнительные сведения о файлах, установленных с помощью РАСШИРЕНного администрирования, можно найти в [руководстве по планированию для расширенного](https://go.microsoft.com/fwlink/?LinkId=160060)набора данных.

## Archive


По умолчанию при установке сервера РАСШИРЕНного анализа данных на локальном жестком диске сервера с РАСШИРЕНным набором (%ProgramData%\\Microsoft\\AGPM.) создается архив. Однако вы можете изменить путь во время установки и даже создать его на сервере, отличном от сервера РАСШИРЕНного поиска.

Архив имеет вложенную папку для каждой версии каждого объекта групповой политики, содержащегося в архиве. Имя каждой вложенной папки — идентификатор GUID, обозначающий версию объекта групповой политики.

Файл gpostate.xml записывает состояние каждого объекта групповой политики в архиве. Файл — это манифест, описывающий содержимое архива. Например, объект GPO может иметь много версий, и каждая версия находится в своей собственной папке в архиве. Файл gpostate.xml указывает, какие вложенные папки содержат различные версии одного объекта групповой политики. Кроме того, у шаблонов объектов групповой политики есть вложенные папки в архиве, но gpostate.xml указывает на то, что они являются шаблонами, а не управляемыми объектами GPO. Аналогичным образом, когда администраторы групповой политики удаляют GPO, они изменяют состояние в gpostate.xml, чтобы показать, что они находятся в **корзине** , но фактически не удаляют вложенные папки GPO из архива.

**Внимание!**  Не изменяйте вручную gpostate.xml или объекты групповой политики, которые содержатся в архиве. Эта информация предоставляется только для понимания того, как будет расширено общее представление о архиве РАСШИРЕНного анализа данных. Вместо этого используйте оснастку "ГРУППОВое преобразование" для изменения GPO.

 

Если вы создаете архив с помощью РАСШИРЕНного управления правами, он предоставляет полный контроль над системой, администраторами и учетной записью службы РАСШИРЕНного доступа (указанной в разделе Настройка сервера управления групповыми политиками). Изменение разрешений на доступ к архиву с помощью пользовательского интерфейса с расширенным управлением групповыми политиками не влияет на эти разрешения, так как учетная запись службы РАСШИРЕНного доступа выполняет все операции от имени пользователя, выполнившего вход.

### Дополнительные ссылки

Сведения о том, как создать резервную копию архива, восстановить архив из резервной копии или переместить оба сервера РАСШИРЕНного использования (и архивов), можно найти в разделе "выполнение задач администратора РАСШИРЕНного администрирования для расширенного состояния" в руководстве по управлению [групповыми политиками](https://go.microsoft.com/fwlink/?LinkId=160061).

## Роли и разрешения


Роли упрощают делегирование. Вместо того чтобы назначать администраторам группового политики детальные разрешения, администраторы РАСШИРЕНного доступа могут назначить одной из четырех ролей администраторам групповой политики, чтобы они могли выполнять задачи, связанные с этой ролью.

-   **Администратор расширенного администрирования:** Администраторы групповой политики, которым назначена роль администратора РАСШИРЕНного доступа (полный доступ), могут выполнять любые задачи в РАСШИРЕНном режимах. Администраторы РАСШИРЕНного доступа к данным могут настраивать параметры уровня домена и делегировать разрешения другим администраторам групповой политики.

-   **Утверждающий:** Администраторы групповой политики, которым назначена роль утверждающего, могут развернуть GPO в рабочей среде домена. Кроме того, утверждающие могут создавать и удалять объекты групповой политики, а также утверждать и отклонять запросы от редакторов. Утверждающие могут просматривать список объектов групповой политики в домене, просматривать параметры политики в GPO и создавать и просматривать отчеты о параметрах политики в объекте групповой политики. Они не могут изменять параметры политики в GPO, если им не назначена роль редактора.

-   **Редактор:** Администраторы групповой политики, которым назначена роль "редактор", могут просматривать список GPO в домене, просматривать параметры политики в объектах GPO, изменять параметры политики в GPO, а также создавать и просматривать отчеты о параметрах политики в GPO. Если им не назначена роль утверждающего, редакторы не могут создавать, развертывать и удалять GPO. Однако они могут запрашивать создание, развертывание и удаление объектов групповой политики.

-   **Рецензент:** Администраторы групповой политики, которым назначена роль рецензента, могут просматривать список GPO в домене и создавать и просматривать отчеты о параметрах политики в объекте групповой политики. Если им не назначена роль редактора, они не могут изменять параметры политики в объекте групповой политики.

С помощью оснастки РАСШИРЕНного доступа администраторы не смогут настраивать разрешения на более подробном уровне, чем роли. В таблице 2 описаны эти разрешения и указаны разрешения, предоставленные каждой роли по умолчанию.

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Разрешение</th>
<th align="left">Описание</th>
<th align="left">Администратор РАСШИРЕНного администрирования</th>
<th align="left">Утверждающий</th>
<th align="left">Editor</th>
<th align="left">Рецензента</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Полный доступ</strong></p></td>
<td align="left"><p>У вас есть все разрешения.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Создание объекта групповой политики</strong></p></td>
<td align="left"><p>Создание объектов групповой политики в домене.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Содержимое списка</strong></p></td>
<td align="left"><p>Перечислите объекты GPO в домене.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Чтение параметров</strong></p></td>
<td align="left"><p>Чтение параметров политики в объекте групповой политики.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Изменить параметры</strong></p></td>
<td align="left"><p>Изменение параметров политики в объекте групповой политики.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Удаление объекта групповой политики</strong></p></td>
<td align="left"><p>Удаление объекта групповой политики.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Изменение параметров безопасности</strong></p></td>
<td align="left"><p>Передача доступа на уровне домена, делегирование доступа к одному GPO и передача доступа в производственную среду.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Развертывание объекта групповой политики</strong></p></td>
<td align="left"><p>Развертывание объекта групповой политики из архива в производственную среду.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Создание шаблона</strong></p></td>
<td align="left"><p>Создание шаблона GPO в РАСШИРЕНном наборе групповой политики.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Изменение параметров</strong></p></td>
<td align="left"><p>Настройте уведомления по электронной почте с помощью РАСШИРЕНного задания и ограничьте версии GPO, хранящиеся в архиве.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Экспорт GPO</strong></p></td>
<td align="left"><p>Экспортируйте объект групповой политики в файл.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Импорт объекта групповой политики</strong></p></td>
<td align="left"><p>Импорт объекта групповой политики из файла.</p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
<td align="left"><p>Да</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**Примечание** 
 Разрешения на **Экспорт GPO** и **импорт GPO** недоступны в расширенном расположении, 3,0 или 2,5.

Возможность делегирования доступа к GPO в рабочей среде для домена и возможность ограничения количества сохраненных версий GPO недоступны в РАСШИРЕНном расположении 2,5.

 

### Дополнительные ссылки

Сведения о том, какие задачи могут выполнять администраторы групповой политики, которым назначена определенная роль, или о том, какие разрешения необходимы для выполнения конкретной задачи, можно найти в [руководстве по эксплуатации для расширенного](https://go.microsoft.com/fwlink/?LinkId=160061)доступа к данным.

 

 





