---
title: Сведения о User Experience Virtualization 1.0 с пакетом обновления 1 (SP1)
description: Сведения о User Experience Virtualization 1.0 с пакетом обновления 1 (SP1)
author: dansimp
ms.assetid: 0212d3fb-e882-476c-9496-9eb52301703d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a480ac5d4f4083fc15a724b7cc79390b0caef14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826892"
---
# Сведения о User Experience Virtualization 1.0 с пакетом обновления 1 (SP1)


Microsoft User Experience Virtualization (UE-V) 1,0 с пакетом обновления 1 изменяет версию с 1.0.414 на 1.0.520. Когда запускается агент UE-V setup.exe или UE-V setup.exe, он обнаружит необходимость в обновлении и обновит агент или генератор UE-V.

## Теперь поддерживаются дополнительные языки


UE-V 1,0 с пакетом обновления 1 (SP1) предоставляет обновления для агента UE-V и генератора UE-V, поддерживающих дополнительные языки. При запуске программы установки устанавливаются все поддерживаемые языки. Следующие языки включены в пакет обновления 1 (SP1) для UE-V:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Агент UE-V</th>
<th align="left">Генератор UE-V</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>Китайская упрощенная (КНР) zh-CN</p></li>
</ul>
<ul>
<li><p>Китайский (традиционное письмо-Тайвань, zh-TW)</p></li>
</ul>
<ul>
<li><p>Чешский (Чешская Республика) cs-CZ</p></li>
</ul>
<ul>
<li><p>Датский (Дания) da-DK</p></li>
</ul>
<ul>
<li><p>Нидерландский (Нидерланды) nl-NL</p></li>
</ul>
<ul>
<li><p>Финский (Финляндия) Fi-FI</p></li>
</ul>
<ul>
<li><p>Французский (Франция) fr-FR</p></li>
</ul>
<ul>
<li><p>Немецкий (Германия) de-DE</p></li>
</ul>
<ul>
<li><p>Греческий (Греция) Эль-GR</p></li>
</ul>
<ul>
<li><p>Венгерский (Венгрия) hu-HU</p></li>
</ul>
<ul>
<li><p>Итальянский (Италия) IT-IT</p></li>
</ul>
<ul>
<li><p>Японский (Япония) ja-JP</p></li>
</ul>
<ul>
<li><p>Корейский (Корея) ko-KR</p></li>
</ul>
<ul>
<li><p>Норвежский (Норвегия букмол, без за(-а)</p></li>
</ul>
<ul>
<li><p>Польский (Польша) PL-PL</p></li>
</ul>
<ul>
<li><p>Португальский (Бразилия) Пт — BR</p></li>
</ul>
<ul>
<li><p>Португальский (Португалия), пт</p></li>
</ul>
<ul>
<li><p>Русский (Россия) ru-RU</p></li>
</ul>
<ul>
<li><p>Словацкий (Словакия) sk-SK</p></li>
</ul>
<ul>
<li><p>Словенский (Словения) SL-SL</p></li>
</ul>
<ul>
<li><p>Испанский, Международная Сортировка (Испания) ES-ES</p></li>
</ul>
<ul>
<li><p>Шведский (Швеция) SV-SE</p></li>
</ul>
<ul>
<li><p>Турецкий (Турция) tr-TR</p></li>
</ul>
<p></p></td>
<td align="left"><ul>
<li><p>Китайская упрощенная (КНР) zh-CN</p></li>
</ul>
<ul>
<li><p>Китайский (традиционное письмо-Тайвань, zh-TW)</p></li>
</ul>
<ul>
<li><p>Французский (Франция) fr-FR</p></li>
</ul>
<ul>
<li><p>Немецкий (Германия) de-DE</p></li>
</ul>
<ul>
<li><p>Итальянский (Италия) IT-IT</p></li>
</ul>
<ul>
<li><p>Японский (Япония) ja-JP</p></li>
</ul>
<ul>
<li><p>Корейский (Корея) ko-KR</p></li>
</ul>
<ul>
<li><p>Португальский (Бразилия) Пт — BR</p></li>
</ul>
<ul>
<li><p>Русский (Россия) ru-RU</p></li>
</ul>
<ul>
<li><p>Испанский, Международная Сортировка (Испания) ES-ES</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**Важно!**  Несмотря на то, что программа установки агента UE-V (AgentSetup.exe) и программа установки для генератора UE-V (ToolSetup.exe) переводятся на указанные выше языки, файлы установщика Windows (MSI) доступны только на английском языке.

 

## Шаблоны расположений параметров Office 2007


Программа установки агента UE-V устанавливает агент и регистрирует стандартную группу шаблонов расположения параметров для распространенных приложений Майкрософт. Microsoft Office 2007 теперь является частью этих приложений. Существует два шаблона Office 2007: MicrosoftOffice2007.xml и MicrosoftCommunicator2007.xml. Эти параметры захватывают шаблоны расположений в Microsoft Office 2007 для следующих приложений:

-   Microsoft Access 2007

-   Microsoft Communicator 2007

-   Microsoft Excel 2007

-   Microsoft InfoPath 2007

-   Microsoft OneNote 2007

-   Microsoft Outlook 2007

-   Microsoft PowerPoint 2007

-   Microsoft Project 2007

-   Microsoft Publisher 2007

-   Microsoft SharePoint Designer 2007

-   Microsoft Visio 2007

-   Microsoft Word 2007

### Обновления шаблонов расположений параметров Office 2010

Вы также сделали обновление шаблонов расположения параметров. К этим изменениям относятся:

-   Добавлена поддержка Microsoft SharePoint Designer 2010 путем добавления нового шаблона в шаблоны Office 2010 (MicrosoftOffice2010Win32.xml и MicrosoftOffice2010Win64.xml)

-   Исправления незначительных ошибок, в том числе Настройка строки состояния — Word, Excel и PowerPoint

## Запланированная задача для обновления каталога стала случайной.


Задача "автоматическое обновление шаблона" проверяет каталог шаблонов параметров на предмет новых, обновленных или удаленных шаблонов. Эта задача выполняется только в том случае, если настроена SettingsTemplateCatalog. Задача "автоматическое обновление шаблона" запускает ApplySettingsCatalog.exe файл, расположенный в каталоге установки агента UE-V и с помощью UE-V SP1, для случайного изменения в течение одного часового периода.

## Поддержка Citrix EdgeSight


Обнаружен конфликт с UE-V, запущенным на сервере Citrix EdgeSight. UE-V 1,0 SP1 устраняет эту проблему.

## Индексирование избранного Internet Explorer


После того, как UE-V перемещает Избранное Internet Explorer с одного компьютера на другой, будет обновлена индексация избранных адресов из адресной строки на синхронизированном компьютере. Когда пользователь вводит в адресную строку, перемещенное Избранное будет отображаться как доступное результат поиска на синхронизированных компьютерах.

## Новые параметры командной строки setup.exe для агента UE-V и UE-V Generator


При выпуске UE-V 1,0 SP1 setup.exe для агента UE-V и генератора UE-V были обновлены, чтобы иметь возможность использовать следующие дополнительные параметры командной строки:

1.  `CEIPENABLED` – Позволяет программе установки принимать параметр, включаемый в программу улучшения качества программного обеспечения Майкрософт.

2.  `INSTALLFOLDER` – Позволяет настроить для агента или генератора другую папку установки.

3.  `MUENABLED` – Позволяет программе установки принимать параметр, включаемый в программу центра обновления Майкрософт.

## Новые коды ошибок для настройки


При запуске программы установки UE-V для агента UE-V (AgentSetup.exe) указанные ниже коды возврата можно просмотреть в журнале установки "/log &lt;log.txt" &gt; .

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>до</p></td>
<td align="left"><p>Установка выполнена успешно.</p></td>
</tr>
<tr class="even">
<td align="left"><p>2</p></td>
<td align="left"><p>При попытке удаления была использована старая версия UE-V. Чтобы удалить UE-V, используйте ту же версию UE-V, которая использовалась для установки.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Трехконтактный</p></td>
<td align="left"><p>Для удаления была использована более новая версия UE-V. Чтобы удалить UE-V, используйте ту же версию UE-V, которая использовалась для установки.</p></td>
</tr>
<tr class="even">
<td align="left"><p>четырехпроцессорном</p></td>
<td align="left"><p>Из программы установки произошла непредвиденная ошибка.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>5</p></td>
<td align="left"><p>Полную версию UE-V нельзя установить поверх пробной (ознакомительной) версии. Удалите пробную версию и повторите попытку.</p></td>
</tr>
<tr class="even">
<td align="left"><p>152</p></td>
<td align="left"><p>При установке произошла непредвиденная ошибка.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>5-7</p></td>
<td align="left"><p>Платформа .NET 3,5 Framework не обнаружена на компьютере с Windows 7 или Windows Server2008 R2.</p></td>
</tr>
<tr class="even">
<td align="left"><p>No8</p></td>
<td align="left"><p>Функция автономных файлов не включена.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>@</p></td>
<td align="left"><p>Программа установки UE-V не может определить, установлен ли UE-V, или произошла ошибка в файле установки.</p></td>
</tr>
</tbody>
</table>

 

 

 





