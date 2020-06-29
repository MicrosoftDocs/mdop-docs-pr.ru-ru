---
title: Назначение правильных учетных данных для Windows XP
description: Назначение правильных учетных данных для Windows XP
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819322"
---
# <span data-ttu-id="749f8-103">Назначение правильных учетных данных для Windows XP</span><span class="sxs-lookup"><span data-stu-id="749f8-103">How to Assign the Proper Credentials for Windows XP</span></span>


<span data-ttu-id="749f8-104">Чтобы настроить клиент App-V для настольных компьютеров с надлежащими учетными данными WindowsXP, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="749f8-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsXP credentials.</span></span>

<span data-ttu-id="749f8-105">**Примечание**  После завершения этой процедуры клиент, не подключенный к домену, может выполнить обновление публикации без соединения с доменом.</span><span class="sxs-lookup"><span data-stu-id="749f8-105">**Note** After finishing this procedure, the non-domain joined client can perform a publishing refresh without being joined to a domain.</span></span>

 

**<span data-ttu-id="749f8-106">Чтобы назначить правильные учетные данные для клиентов App-V, использующих WindowsXP</span><span class="sxs-lookup"><span data-stu-id="749f8-106">To assign the proper credentials for App-V clients running WindowsXP</span></span>**

1.  <span data-ttu-id="749f8-107">С правами администратора на клиентском компьютере App-V под управлением WindowsXP откройте панель управления **учетные записи пользователей** (классическая панель управления).</span><span class="sxs-lookup"><span data-stu-id="749f8-107">With administrator privileges on the App-V Client running WindowsXP, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="749f8-108">Откройте **вкладку Дополнительно**и выберите **Управление паролями**.</span><span class="sxs-lookup"><span data-stu-id="749f8-108">Click the **Advanced Tab**, and select **Manage Passwords**.</span></span>

3.  <span data-ttu-id="749f8-109">На экране " **Сохранение имен пользователей и паролей** " нажмите кнопку " **Добавить**".</span><span class="sxs-lookup"><span data-stu-id="749f8-109">On the **Stored User Names and Passwords** screen, click **Add**.</span></span>

4.  <span data-ttu-id="749f8-110">На экране **Свойства сведения для входа** заполните следующие поля: сведения из инфраструктуры App-V.</span><span class="sxs-lookup"><span data-stu-id="749f8-110">On the **Logon Information Properties** screen, fill out the following fields with information from the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="749f8-111">**Сервер:** Имя внешнего имени сервера публикации.</span><span class="sxs-lookup"><span data-stu-id="749f8-111">**Server:** Name of publishing server external name.</span></span>

    2.  <span data-ttu-id="749f8-112">**Имя пользователя:** Имя пользователя для внешнего пользователя в форме Domain\\username.</span><span class="sxs-lookup"><span data-stu-id="749f8-112">**User name:** User name for external user in the form Domain\\username.</span></span>

    3.  <span data-ttu-id="749f8-113">**Password (пароль):** Пароль учетной записи пользователя, введенной в поле **имя пользователя** .</span><span class="sxs-lookup"><span data-stu-id="749f8-113">**Password:** Password for the user account entered in the **User name** field.</span></span>

5.  <span data-ttu-id="749f8-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="749f8-114">Click **OK**.</span></span> <span data-ttu-id="749f8-115">Учетные данные будут храниться на клиенте.</span><span class="sxs-lookup"><span data-stu-id="749f8-115">The credentials will be stored on the client.</span></span>

## <span data-ttu-id="749f8-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="749f8-116">Related topics</span></span>


[<span data-ttu-id="749f8-117">Присоединенные к домену и не присоединенные к домену клиенты</span><span class="sxs-lookup"><span data-stu-id="749f8-117">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="749f8-118">Назначение правильных учетных данных для Windows Vista</span><span class="sxs-lookup"><span data-stu-id="749f8-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





