---
title: Удаление управляемого объекта групповой политики
description: Удаление управляемого объекта групповой политики
author: dansimp
ms.assetid: f51c1737-c116-4faf-a6f6-c72303f60a3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 365554d90ac13d749508edbc84dacd432ac4ceec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818712"
---
# <span data-ttu-id="f8676-103">Удаление управляемого объекта групповой политики</span><span class="sxs-lookup"><span data-stu-id="f8676-103">Delete a Controlled GPO</span></span>


<span data-ttu-id="f8676-104">Утверждающие могут удалить управляемый объект групповой политики (GPO), переместив его в корзину.</span><span class="sxs-lookup"><span data-stu-id="f8676-104">Approvers can delete a controlled Group Policy Object (GPO), moving it to the Recycle Bin.</span></span>

<span data-ttu-id="f8676-105">Для выполнения этой процедуры необходимо использовать учетную запись пользователя с ролью "полный доступ" и "Администратор расширенного управления групповыми политиками (для опытных пользователей)" или необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="f8676-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="f8676-106">Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".</span><span class="sxs-lookup"><span data-stu-id="f8676-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="f8676-107">Удаление управляемого объекта групповой политики</span><span class="sxs-lookup"><span data-stu-id="f8676-107">To delete a controlled GPO</span></span>**

1.  <span data-ttu-id="f8676-108">В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.</span><span class="sxs-lookup"><span data-stu-id="f8676-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="f8676-109">На вкладке **содержание** откройте вкладку **Управление** , чтобы отобразить управляемые объекты групповой политики.</span><span class="sxs-lookup"><span data-stu-id="f8676-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="f8676-110">Щелкните правой кнопкой мыши объект групповой политики, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f8676-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="f8676-111">Чтобы удалить GPO из архива, не открывая внедренный объект, не находясь в рабочей среде, выберите команду **Удалить GPO из архива**.</span><span class="sxs-lookup"><span data-stu-id="f8676-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="f8676-112">Чтобы удалить GPO из архивной и производственной сред, выберите команду **удалить объект групповой политики из архива и из рабочей**среды.</span><span class="sxs-lookup"><span data-stu-id="f8676-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="f8676-113">Введите Примечание, которое будет отображаться в контрольной записи для объекта групповой политики, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8676-113">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="f8676-114">После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f8676-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="f8676-115">Объект групповой политики удаляется с вкладки " **управляемые** " и отображается на вкладке " **Корзина** ", в которой ее можно восстановить или уничтожить.</span><span class="sxs-lookup"><span data-stu-id="f8676-115">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span> <span data-ttu-id="f8676-116">Если объект групповой политики был удален только из архива, он также отображается на вкладке **неуправление** .</span><span class="sxs-lookup"><span data-stu-id="f8676-116">If the GPO was deleted only from the archive, it is also displayed on the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="f8676-117">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="f8676-117">Additional considerations</span></span>

-   <span data-ttu-id="f8676-118">По умолчанию для выполнения этой процедуры необходимо быть утверждающим или администратором расширенного управления групповыми политиками (полный доступ).</span><span class="sxs-lookup"><span data-stu-id="f8676-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="f8676-119">В частности, необходимо иметь **содержимое списка** и **удалить разрешения GPO** для объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="f8676-119">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="f8676-120">Чтобы удалить неуправляемый объект групповой политики из производственной среды, не открывая его сначала, в **консоли управления групповыми политиками**нажмите кнопку **лес**, выберите \*\* &lt; пункт &gt; \*\* **домены**, а затем — пункт **объекты групповой политики**.</span><span class="sxs-lookup"><span data-stu-id="f8676-120">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="f8676-121">Щелкните ненужный объект групповой политики правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f8676-121">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="f8676-122">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="f8676-122">Additional references</span></span>

-   [<span data-ttu-id="f8676-123">Удаление, восстановление и уничтожение объекта групповой политики</span><span class="sxs-lookup"><span data-stu-id="f8676-123">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 




