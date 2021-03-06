---
title: Проверка перенаправления URL-адресов
description: Проверка перенаправления URL-адресов
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824449"
---
# Проверка перенаправления URL-адресов


После завершения первоначальной проверки правильности работы функции перенаправления URL-адресов можно проверить, выполнив указанные ниже действия.

**Важно!**  Для правильной работы перенаправления URL-адреса необходимо, чтобы был запущен агент узла MED-V.

<a href="" id="bkmk-urlredir"></a>**Проверка перенаправления URL-адреса**

1.  Откройте браузер Internet Explorer на главном компьютере и введите URL-адрес, указанный для перенаправления.

2.  Убедитесь в том, что веб-страница открыта в Internet Explorer на гостевой виртуальной машине.

3.  Повторите эти действия для каждого URL-адреса, который вы хотите протестировать.

**Проверка возможности добавления или удаления URL-адреса**

1.  Добавьте или удалите URL-адрес из рабочей области MED-V.

    Сведения о том, как добавлять и удалять URL-адреса для перенаправления в рабочей области MED-V, можно найти в разделе [Управление перенаправлением URL-адресов](manage-med-v-url-redirection.md)в MED-v.

2.  Если вы добавили URL-адрес в список перенаправления, повторите действия, описанные в разделе [Проверка перенаправления URL-адреса](#bkmk-urlredir) , чтобы убедиться, что новый URL-адрес перенаправляется надлежащим образом.

3.  Если вы удалили URL-адрес из списка перенаправления, убедитесь, что он удален, выполнив указанные ниже действия.

    1.  Откройте браузер Internet Explorer на главном компьютере и введите URL-адрес, который вы удалили из списка перенаправления.

    2.  Убедитесь, что веб-страница открыта в Internet Explorer на главном компьютере, а не на гостевой виртуальной машине.

        **Примечание**  Изменение перенаправления URL-адреса может занять несколько секунд.

**Примечание**  Если при проверке параметров перенаправления URL-адресов возникли проблемы, ознакомьтесь с разделом [Устранение неполадок](operations-troubleshooting-medv2.md)при использовании операций.

После того как вы закончите тестирование перенаправления URL-адресов в рабочей области MED-V, вы можете протестировать другие конфигурации, чтобы убедиться, что они правильно выполняются.

После завершения тестирования пакета рабочей области для MED-V и проверки его работоспособности вы можете развернуть рабочую область MED-V в своей организации.

## Статьи по теме

[Проверка публикации приложений](how-to-test-application-publishing.md)

[Проверка параметров первой установки](how-to-verify-first-time-setup-settings.md)

[Развертывание пакета рабочих областей MED-V](deploying-the-med-v-workspace-package.md)

 

 





