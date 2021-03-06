---
title: Определение количества экземпляров MED-V
description: Определение количества экземпляров MED-V
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824259"
---
# Определение количества экземпляров MED-V


Необходимо определить количество экземпляров MED-V, а также определить область для каждого экземпляра, чтобы можно было спроектировать инфраструктуру сервера. Экземпляр MED-V включает следующее:

-   Сервер MED-V и рабочие области MED-V, хранящиеся на сервере, в том числе разрешения Active Directory.

-   База данных SQL Server, в которой хранятся клиентские события. База данных может совместно использоваться несколькими экземплярами MED-V.

-   Репозиторий изображений для упакованных изображений MED-V. Хранилище может совместно использоваться несколькими экземплярами MED-V.

-   Консоль управления, используемая для создания и упаковки изображений, а также для создания рабочих областей MED-V. Консоль нельзя использовать одновременно несколькими экземплярами MED-V, но ее можно отключить от одного сервера MED-V и затем подключиться к другому серверу MED-V.

-   Клиенты MED-V, получающие рабочие области MED-V, и авторизацию для их использования на сервере.

Отдельные экземпляры MED-V нельзя интегрировать или совместно использовать в рабочих областях MED-V. Таким образом, каждый дополнительный экземпляр децентрализует управление виртуализацией.

## Определение количества требуемых экземпляров MED-V


Начните с того, что вы используете один экземпляр MED-V. Затем Рассматривайте указанные ниже условия и добавляйте дополнительные экземпляры для каждого условия, которое применяется к вашей инфраструктуре.

-   Количество поддерживаемых пользователей (каждый из экземпляров MED-V может поддерживать до 5 000 одновременно активных клиентов). Параллельно активный означает, что клиент подключен к серверу MED-V и отправляет опросы на сервер для обновления политики и изображений, а также для событий. Если ваша инфраструктура будет включать более 5 000 активных пользователей, добавьте один экземпляр для каждого пользователя 5 000.

-   Пользователи в доменах без доверия — сервер MED-V связывает разрешения рабочей области для MED-V с пользователями и (или) группами Active Directory. Для этого требуется, чтобы пользователи MED-V существовали в пределах границы доверия сервера MED-V. Добавьте один экземпляр MED-V для каждой группы пользователей MED-V из отдельного домена, не имеющего доверия.

-   Клиенты в изолированных сетях — определяют, находятся ли клиенты в изолированных сетях, и поэтому требуют отдельного экземпляра MED-V. Например, организации часто изолируют лабораторные сети из производственных сетей. Добавьте экземпляр MED-V для каждой изолированной сети, которая будет содержать клиенты MED-V.

-   Организационные требования. организациям может потребоваться, чтобы группа клиентов управлялась отдельным экземпляром MED-V по соображениям безопасности, например при доставке конфиденциальных приложений только ограниченному набору пользователей в домене. Например, сотрудник отдела заработной платы может отказаться от доступа пользователей других отделов к экземпляру MED-V, в котором хранится политика для обработки зарплаты. Кроме того, если в организации используется модель распределенного управления, для каждой бизнес-группы с клиентами MED-V может потребоваться отдельный экземпляр MED-V, чтобы разрешить группе управлять своей виртуальной средой. Добавьте один экземпляр MED-V для каждого отдельного требования Организации.

-   Юридическая информация — вопросы, связанные с безопасностью, конфиденциальностью и Fiduciary законами, может потребоваться разделение некоторых данных или появление других данных, которые не пересекают национальные границы. При необходимости добавьте дополнительные экземпляры MED-V, чтобы решить эту необходимость.

После определения количества экземпляров MED-V, необходимых для вашей инфраструктуры, а также причины для каждой из них укажите имя для каждого экземпляра.

 

 





