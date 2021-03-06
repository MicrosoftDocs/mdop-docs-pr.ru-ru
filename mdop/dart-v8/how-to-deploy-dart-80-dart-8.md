---
title: Развертывание DaRT 8.0
description: Развертывание DaRT 8.0
author: dansimp
ms.assetid: ab772e7a-c02f-4847-acdf-8bd362769a77
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e7d64297f7687ebc0a23add3aa749ee4719beee4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824299"
---
# Развертывание DaRT 8.0


Ниже приведены инструкции по развертыванию набора средств диагностики и восстановления Microsoft (DaRT) 8,0 в среде. Для получения программного обеспечения DaRT ознакомьтесь [со статьей получение MDOP](https://go.microsoft.com/fwlink/?LinkId=322049). Предполагается, что все возможности устанавливаются на одном компьютере администратора. Если вам нужно развернуть или удалить DaRT 8,0 на нескольких компьютерах, используя электронную систему распространения программного обеспечения, например, вы можете использовать параметры установки из командной строки. В этом разделе приведены описания и примеры доступных параметров командной строки.

**Важно!**  Перед установкой DaRT ознакомьтесь с разрядом [конфигураций dart 8,0](dart-80-supported-configurations-dart-8.md) , чтобы убедиться, что вы установили все необходимое программное обеспечение и что компьютер отвечает минимальным требованиям к системе. На компьютере, на котором вы хотите установить DaRT, должна быть установлена операционная система Windows 8 или Windows Server 2012.

 

Вы можете установить DaRT с помощью одной из двух различных конфигураций.

-   Установите DaRT и все инструменты DaRT на компьютере администратора.

-   Установите на компьютере администратора только те инструменты, которые необходимы для создания изображения для восстановления DaRT, а затем установите **средство просмотра удаленных подключений** и, при необходимости, **анализатор аварийных сбоев** на компьютере службы поддержки.

Файл установки DaRT доступен как в 32-, так и в 64-разрядных версиях. Установите версию, совпадающую с архитектурой компьютера, на котором запущен мастер изображений для восстановления DaRT, а не архитектурой компьютера для создаваемого образа восстановления.

Вы можете использовать любую из версий установочного файла DaRT для создания образа восстановления для 32 или 64-разрядных компьютеров, но вы не можете создать один образ восстановления как для 32, так и для 64-разрядных компьютеров.

**Установка и удаление DaRT и всех инструментов DaRT на компьютере администратора**

1.  Загрузите файл установщика DaRT 8,0 (32-разрядная версия или 64-разр.). Выберите архитектуру, соответствующую компьютеру, на котором вы хотите установить DaRT, и запустите мастер переноса изображений с помощью DaRT Recovery.

2.  В папке, в которую вы загрузили DaRT 8,0, запустите установочный файл **MSDaRT80.msi** , соответствующий вашим требованиям к системе.

3.  На странице **Добро пожаловать на страницу мастера настройки Microsoft DaRT 8,0** нажмите кнопку **Далее**.

4.  Приняв условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт, а затем нажмите кнопку **Далее**.

5.  На странице **центра обновления Майкрософт** установите флажок **использовать Microsoft Update после проверки обновлений**и нажмите кнопку **Далее**.

6.  На странице " **Выбор папки для установки** " выберите папку или нажмите кнопку " **Далее** ", чтобы установить DART в папке для установки по умолчанию.

7.  На странице **Параметры настройки** выберите компоненты DART, которые вы хотите установить, или нажмите кнопку **Далее** , чтобы установить DART вместе со всеми функциями.

8.  Чтобы начать установку, нажмите кнопку **установить**.

9.  После успешного завершения установки нажмите кнопку **Готово** , чтобы завершить работу мастера.

## Установка и удаление DaRT и всех инструментов DaRT на компьютере с администратором с помощью командной строки


При установке или удалении DaRT вы сможете запускать установочные файлы в командной строке. В этом разделе описаны некоторые примеры различных параметров, которые можно указать при установке или удалении DaRT в командной строке.

В следующем примере показано, как установить все функции DaRT.

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

В следующем примере показано, как установить только мастер переноса изображений для восстановления DaRT.

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

В следующем примере показано, как установить только анализатор аварийного восстановления и средство просмотра удаленных подключений DaRT.

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

В следующем примере создается журнал установки для установщика Windows. Это полезно для отладки.

``` syntax
msiexec.exe /i MSDaRT80.msi /l*v log.txt 
```

**Примечание**  Вы можете добавить/Qn или/QB для выполнения автоматической установки.

 

**Проверка установки DaRT**

1.  Нажмите кнопку **Пуск**и выберите **набор средств диагностики и восстановления**.

    Откроется окно **инструментов Диагностика и восстановление** .

2.  Убедитесь, что все инструменты DaRT, выбранные для установки, успешно установлены.

## Статьи по теме


[Развертывание DaRT 8.0 на компьютерах администраторов](deploying-dart-80-to-administrator-computers-dart-8.md)

 

 





