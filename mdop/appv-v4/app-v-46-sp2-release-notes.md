---
title: Заметки о выпуске App-V 4.6 с пакетом обновления 2 (SP2)
description: Заметки о выпуске App-V 4.6 с пакетом обновления 2 (SP2)
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822342"
---
# Заметки о выпуске App-V 4.6 с пакетом обновления 2 (SP2)


**Чтобы найти заметки о выпуске, нажмите клавиши CTRL + F.**

Внимательно прочтите эти заметки о выпуске, прежде чем устанавливать Microsoft Application Virtualization (App-V) 4.6 SP2.

Эти заметки о выпуске содержат сведения, необходимые для успешной установки Application Virtualization 4,6 SP2. Заметки о выпуске также содержат сведения, недоступные в документации по продукту. Если существует разница между этими заметками о выпуске и другой документацией по App-V 4.6 SP2, Последнее изменение должно считаться полномочным. Эти заметки о выпуске заменяют содержимое, которое входит в состав этого продукта.

## Сведения о документации по продукту


Дополнительные сведения о документации для App-V можно найти на странице [Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982) в Microsoft TechNet.

## Предоставление отзыва


Мы заинтересованы в ваших отзывах о приложении App-V 4.6 SP2. Вы можете отправить свой отзыв <mdopdocs@microsoft.com> .

**Примечание**  Этот адрес электронной почты не является каналом поддержки, но ваш отзыв поможет нам спланировать будущие изменения документации и выпусков продуктов.

 

Последние сведения о MDOP и дополнительных учебных материалах можно найти на странице [сведения о MDOP](https://go.microsoft.com/fwlink/p/?LinkId=236032) .

Дополнительные сведения о новых обновлениях и отзыве можно получить, выполнив следующие действия в [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) или [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a>Известные проблемы с приложением-V 4.6 SP2


### Поддержка коротких имен файлов отключена на физических дисках, не являющихся системными, при последовательном выборе

При использовании последовательности в Windows 8 или Windows Server 2012 поддержка коротких имен файлов (8,3) по умолчанию отключена для физических дисков без системы.

Основной физический диск, связанный с основным каталогом виртуальных приложений (например, "Q:\\appname") на станции виртуализации, должен предоставлять поддержку короткого имени файла (8,3), чтобы при создании пакетов виртуальных приложений для App-V 4.6 SP2 создавались короткие имена файлов. В Windows 8 и Windows Server 2012 поддержка коротких имен файлов (8,3) отключена по умолчанию для несистемных физических дисков.

**Временное решение:** Включите поддержку коротких имен файлов (8,3) на физических дисках, не являющихся системами. Вы можете использовать указанную ниже команду, чтобы включить поддержку коротких имен файлов в Windows 8 и Windows Server 2012.

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

Например, чтобы указать букву диска "Q:", выполните следующую команду:

``` syntax
fsutil 8dot3name set Q: 0
```

**Примечание**  Вам не нужно изменять этот параметр в клиенте App-V, так как в файловой системе App-V для Windows 8 или Windows Server 2012 правильно обрабатываются короткие пути.

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> Приложение App-V не переопределяет обработчик по умолчанию для связей с типами файлов и протоколов в Windows 8

Если выбрать приложение по умолчанию с помощью **программ по умолчанию** на **панели управления** в Windows 8, приложение App-V не будет переопределять сопоставлений типов файлов для этого приложения.

**Временное решение:** Ничего.

### Виртуализированные Outlook 2010 не предлагаются в качестве параметра для ссылок, которые можно щелкать по адресу mailto в Windows 8

Расширение оболочки mailto не поддерживает виртуализированное приложение Outlook 2010 в Windows 8. Например, если вы щелкните ссылку mailto: из виртуализированного Outlook 2010, работающего в Windows 8, не будет создано новое окно электронной почты. Этот параметр работает правильно в Windows 7 и более ранних версиях операционной системы Windows.

**Временное решение:** Ничего.

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> Обновление Application Virtualization 4,6 с пакетом обновления 2 (SP2) не предлагается на всех языках, использующих Microsoft Update

При использовании центра обновления Майкрософт Обновление для App-V 4.6 SP2 недоступно для языковых стандартов, указанных ниже.

-   Казахский

-   Хинди

-   Сербский (кириллица)

**Временное решение:** Если вы используете Microsoft Windows Server Update Services (WSUS), используйте английскую версию обновления или загрузите обновление из каталога Центра обновления Майкрософт.

## Сведения о заметках об авторском праве


Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune и WindowsPowerShell являются товарными знаками группы компании Microsoft. Все прочие товарные знаки являются собственностью соответствующих владельцев.



## Статьи по теме


[Сведения о системе Microsoft Application Virtualization 4.6 с пакетом обновления 2 (SP2)](about-microsoft-application-virtualization-46-sp2.md)

 

 





