---
title: Проверка параметров объекта групповой политики
description: Проверка параметров объекта групповой политики
author: dansimp
ms.assetid: bed956d0-082e-4fa9-bf1e-572d0d3d02ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 23d18eb5a41b4246964b79f687eb9fa44b98b730
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818339"
---
# <span data-ttu-id="56f00-103">Проверка параметров объекта групповой политики</span><span class="sxs-lookup"><span data-stu-id="56f00-103">Review GPO Settings</span></span>


<span data-ttu-id="56f00-104">Вы можете создавать отчеты на основе HTML и XML для проверки параметров в любой версии объекта групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="56f00-104">You can generate HTML-based and XML-based reports for reviewing settings within any version of a Group Policy Object (GPO).</span></span>

<span data-ttu-id="56f00-105">Для выполнения этой процедуры требуется учетная запись пользователя с ролью "рецензент", "редактор", "Утверждающий" или "Администратор расширенного управления групповыми политиками (полный доступ") или необходимыми разрешениями в расширенном управлении групповой политикой (ГРУППОВое управление).</span><span class="sxs-lookup"><span data-stu-id="56f00-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="56f00-106">Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".</span><span class="sxs-lookup"><span data-stu-id="56f00-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="56f00-107">Просмотр параметров в любой версии GPO</span><span class="sxs-lookup"><span data-stu-id="56f00-107">To review settings in any version of a GPO</span></span>**

1.  <span data-ttu-id="56f00-108">В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.</span><span class="sxs-lookup"><span data-stu-id="56f00-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="56f00-109">На вкладке **содержание** в области сведений щелкните вкладку, чтобы отобразить объекты групповой политики.</span><span class="sxs-lookup"><span data-stu-id="56f00-109">On the **Contents** tab in the details pane, click a tab to display GPOs.</span></span>

3.  <span data-ttu-id="56f00-110">Дважды щелкните объект групповой политики, чтобы просмотреть его историю.</span><span class="sxs-lookup"><span data-stu-id="56f00-110">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="56f00-111">Щелкните правой кнопкой мыши версию объекта групповой политики, для которого нужно просмотреть параметры, выберите пункт **Параметры**, а затем — **отчет HTML** или **отчет XML** , чтобы просмотреть сводку по параметрам объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="56f00-111">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="56f00-112">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="56f00-112">Additional considerations</span></span>

-   <span data-ttu-id="56f00-113">По умолчанию для выполнения этой процедуры необходимо быть рецензентом, редактором, утверждающим или администратором расширенного управления групповыми политиками (полный доступ).</span><span class="sxs-lookup"><span data-stu-id="56f00-113">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="56f00-114">В частности, необходимо иметь **содержимое списка** и разрешения на **Чтение параметров** для GPO.</span><span class="sxs-lookup"><span data-stu-id="56f00-114">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="56f00-115">Кроме того, чтобы отобразить список объектов групповой политики, необходимо иметь разрешение " **содержимое списка** " для домена.</span><span class="sxs-lookup"><span data-stu-id="56f00-115">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="56f00-116">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="56f00-116">Additional references</span></span>

-   [<span data-ttu-id="56f00-117">Выполнение задач рецензента</span><span class="sxs-lookup"><span data-stu-id="56f00-117">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 




