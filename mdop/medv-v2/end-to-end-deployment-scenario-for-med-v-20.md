---
title: Комплексный сценарий развертывания MED-V 2.0
description: Комплексный сценарий развертывания MED-V 2.0
author: dansimp
ms.assetid: 91bb5a9a-5fb1-4743-8494-9d4dee2ec222
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6d56e70ad359ebf2d76cf3f30f54f73cd9ca1c66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826172"
---
# Комплексный сценарий развертывания MED-V 2.0


Этот пример сценария для Microsoft Enterprise Virtualization (MED-V) 2,0 помогает развертывать компоненты MED-V в Организации с помощью нескольких сценариев. Вы можете представить этот образец сценария как пример исследования, который помогает поместить отдельные сценарии и процедуры в контекст.

В этом разделе приведены основные сведения и инструкции по развертыванию компонентов MED-V в качестве комплексного решения в вашей организации.

## Пошаговые инструкции по развертыванию MED-V


Ниже приведены разделы, посвященные этим пошаговым сценарием.

-   [Конфигурации, поддерживаемые med-v 2,0](med-v-20-supported-configurations.md) , обсуждают требования, необходимые для установки и запуска Microsoft Enterprise VIRTUALIZATION (MED-V) 2.0 в среде. В этой статье указаны требования к операционной системе, требования к конфигурации и требования к рабочей области MED-V. В этой статье также содержатся сведения о локализации для языков, поддерживаемых MED-V 2,0.

-   [Обзор развертывания MED-v 2,0](med-v-20-deployment-overview.md) содержит общую информацию и инструкции, которые помогут вам установить и развернуть MED-V во всей Организации. Компоненты MED-V являются клиентскими и доставляются и управляются с помощью существующей инфраструктуры и процессов предприятия. В этой статье приведены общие сведения о решении MED-V, в том числе сведения о файлах установки для MED-V и развертываемых компонентах MED-V. В этом разделе также приводится общий обзор процесса установки и развертывания для MED-V.

-   [Подготовка среды развертывания для MED-v](prepare-the-deployment-environment-for-med-v.md) обсуждает процесс подготовки среды для развертывания MED-v 2,0. В этом разделе описаны необходимые условия, необходимые для среды MED-V, например Microsoft Windows 7 и инфраструктура Active Directory, в которой вы используете групповую политику для централизованного управления и настройки операционных систем, приложений и параметров пользователей. В этом разделе также описаны необходимые условия для установки и развертывания MED-V 2,0 для всего предприятия (например, Windows Virtual PC и обязательное обновление виртуальных компьютеров Windows).

-   [Развертывание компонентов MED-v](deploy-the-med-v-components.md) описывает различные способы установки всех необходимых файлов установки и компонентов MED-v во всей Организации. Для установки и развертывания MED-V обычно выполните указанные ниже действия.

    1.  Установите **упаковщик рабочих областей med-v** на компьютере администратора, который будет использоваться для создания пакетов рабочей области для MED-v. Дополнительные сведения можно найти [в разделе Установка диспетчера рабочих областей MED-V](how-to-install-the-med-v-workspace-packager.md).

    2.  Создание и тестирование пакетов рабочей области для MED-V. Дополнительные сведения можно найти в разделе [Создание пакета рабочей области для MED-v](create-a-med-v-workspace-package.md) и [Тестирование пакета рабочей области MED-v](testing-the-med-v-workspace-package.md).

    3.  Развертывание MED-V в масштабах Организации с помощью существующего метода компании для развертывания приложений. Дополнительные сведения можно найти [в разделе Развертывание пакета рабочей области для MED-V](deploying-the-med-v-workspace-package.md).

## Статьи по теме


[Развертывание MED-V](deployment-of-med-v.md)

[Комплексный сценарий планирования MED-V 2.0](end-to-end-planning-scenario-for-med-v-20.md)

[Комплексный сценарий эксплуатации MED-V 2.0](end-to-end-operations-scenario-for-med-v-20.md)

 

 




