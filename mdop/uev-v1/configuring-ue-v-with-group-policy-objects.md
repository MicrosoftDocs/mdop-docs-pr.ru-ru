---
title: Настройка UE-V с помощью объектов групповой политики
description: Настройка UE-V с помощью объектов групповой политики
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826699"
---
# Настройка UE-V с помощью объектов групповой политики


Некоторые параметры групповой политики Microsoft User Experience Virtualization (UE-V) можно определять для компьютеров и других пользователей. Параметры политики конфигурации агента UE-V можно определять для компьютеров и пользователей. Дополнительные сведения о том, как установить ADMX-файлы групповой политики, можно найти [в разделе Установка шаблонов ADMX групповой политики UE-v](installing-the-ue-v-group-policy-admx-templates.md).

Для UE-V можно настроить следующие параметры политики:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Имя параметра политики</strong></p></td>
<td align="left"><p><strong>Target</strong></p></td>
<td align="left"><p><strong>Описание параметра политики</strong></p></td>
<td align="left"><p><strong>Параметры конфигурации</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Использование виртуализации взаимодействия с пользователем (UE-V)</p></td>
<td align="left"><p>Компьютеры и пользователи</p></td>
<td align="left"><p>Этот параметр политики позволяет включить или отключить виртуализацию взаимодействия с пользователем (UE-V).</p></td>
<td align="left"><p>Включите или отключите этот параметр политики.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Путь к хранилищу параметров</p></td>
<td align="left"><p>Компьютеры и пользователи</p></td>
<td align="left"><p>Этот параметр политики определяет, где будут храниться параметры пользователя.</p></td>
<td align="left"><p>Укажите путь UNC и переменные (например, \Server\SettingsShare%username%.).</p></td>
</tr>
<tr class="even">
<td align="left"><p>Путь к каталогу шаблонов параметров</p></td>
<td align="left"><p>Только компьютеры</p></td>
<td align="left"><p>Этот параметр политики определяет, где хранятся пользовательские шаблоны расположений параметров. Этот параметр политики также указывает, будет ли каталог использоваться для замены используемых по умолчанию шаблонов Microsoft, установленных с помощью UE-V Agent.</p></td>
<td align="left"><p>Укажите путь UNC (Universal Naming Convention), например \Server\TemplateShare или расположение папки на компьютере.</p>
<p></p>
<p>Установите флажок, чтобы заменить используемые по умолчанию шаблоны Microsoft.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Не используйте автономные файлы</p></td>
<td align="left"><p>Компьютеры и пользователи</p></td>
<td align="left"><p>Этот параметр политики позволяет указать, будет ли UE-V использовать функцию автономных файлов Windows. Этот параметр политики также позволяет включить уведомления о задержке импорта параметров пользователя.</p></td>
<td align="left"><p>Чтобы настроить агент UE-V без использования автономных файлов, включите этот параметр.</p>
<p></p>
<p>Укажите, следует ли предоставлять уведомления о задержке импорта параметров.</p>
<p></p>
<p>Укажите интервал времени (в секундах), по истечении которого будет выводиться уведомление.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Время ожидания синхронизации</p></td>
<td align="left"><p>Компьютеры и пользователи</p></td>
<td align="left"><p>Этот параметр политики задает количество миллисекунд, в течение которых компьютер будет ждаться, прежде чем превышено время ожидания при получении параметров пользователя из расположения удаленных параметров. Если место в внешнем хранилище недоступно, запуск приложения задерживается этим количеством миллисекунд.</p></td>
<td align="left"><p>Укажите предпочтительное время ожидания синхронизации в миллисекундах. Значение по умолчанию 2000 миллисекунд.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Порог предупреждений о размере пакета</p></td>
<td align="left"><p>Компьютеры и пользователи</p></td>
<td align="left"><p>Этот параметр политики позволяет настроить агент UE-V для отчета о том, что размер файла пакета параметров достигнет определенного порогового значения.</p></td>
<td align="left"><p>Указывает предпочтительный порог для размера пакета параметров в килобайтах.</p>
<p>По умолчанию агент UE-V не имеет порогового значения размера файла пакета.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Параметры перемещаемых приложений</p></td>
<td align="left"><p>Только для пользователей</p></td>
<td align="left"><p>Этот параметр политики позволяет настроить перемещение параметров пользователя для приложений.</p></td>
<td align="left"><p>Выберите параметры Windows, которые будут перемещаться между компьютерами.</p>
<p>По умолчанию параметры пользователя для приложений с шаблоном параметров, предоставленными UE-V, перемещаются между компьютерами.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Перемещаемые параметры Windows</p></td>
<td align="left"><p>Только для пользователей</p></td>
<td align="left"><p>Этот параметр политики настраивает перемещаемые параметры Windows.</p></td>
<td align="left"><p>Выберите, какие приложения будут перемещаться между компьютерами.</p>
<p>По умолчанию темы Windows перемещаются между компьютерами одной и той же версии операционной системы. Параметры рабочего стола Windows и параметры специальных возможностей не перемещаются.</p></td>
</tr>
</tbody>
</table>

 

**Настройка политик, предназначенных для компьютера**

1.  С помощью консоли управления групповыми политиками (GPMC) или расширенного управления групповыми политиками (групповой политики) на компьютере контроллера домена, управляющего групповой политикой для компьютеров с UE-V. Перейдите к разделу **Конфигурация компьютера**, выберите **политики**, выберите **Административные шаблоны**, щелкните **компоненты Windows**, а затем выберите **Microsoft User Experience Virtualization**.

2.  Выберите параметр политики, который нужно изменить.

**Настройка политик, предназначенных для пользователей**

1.  Используйте консоль управления групповыми политиками (GPMC) или Расширенное средство управления групповыми политиками в пакете оптимизации рабочего стола (MDOP) на компьютере контроллера домена, управляющем групповой политикой для UE-V. Перейдите к разделу **Конфигурация пользователя**, выберите **политики**, выберите **Административные шаблоны**, щелкните **компоненты Windows**, а затем выберите **Microsoft User Experience Virtualization**.

2.  Выберите параметр политики, измененный.

Для определения синхронизации агент UE-V использует следующий порядок приоритетов.

**Порядок приоритетов для параметров UE-V**

1.  Целевые параметры пользователей, управляемые групповой политикой: эти параметры конфигурации хранятся в разделе реестра групповой политикой `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` .

2.  Целевые параметры компьютера, управляемые групповой политикой — эти параметры конфигурации хранятся в разделе реестра с помощью групповой политики `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` .

3.  Параметры конфигурации, определяемые текущим пользователем с помощью PowerShell или WMI — эти параметры конфигурации хранятся агентом UE-V в этом разделе `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` реестра:

4.  Параметры конфигурации, определенные для компьютера с помощью PowerShell или WMI. Эти параметры конфигурации хранятся агентом UE-V в разделе `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` .

## Статьи по теме


[Администрирование UE-V 1.0](administering-ue-v-10.md)

[Операции в UE-V 1.0](operations-for-ue-v-10.md)

 

 





