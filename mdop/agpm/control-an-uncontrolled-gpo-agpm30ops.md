---
title: Управление неконтролируемым объектом групповой политики
description: Управление неконтролируемым объектом групповой политики
author: dansimp
ms.assetid: 603f00f9-1e65-4b2f-902a-e53dafedbd8d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 904c3f76ce89f3814b739ee958fc14198899fb14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818882"
---
# <span data-ttu-id="9adc1-103">Управление неконтролируемым объектом групповой политики</span><span class="sxs-lookup"><span data-stu-id="9adc1-103">Control an Uncontrolled GPO</span></span>


<span data-ttu-id="9adc1-104">Чтобы предоставить управление изменениями для объекта групповой политики (GPO), необходимо сначала управлять этим объектом.</span><span class="sxs-lookup"><span data-stu-id="9adc1-104">To provide change control for a Group Policy Object (GPO), you must first control the GPO.</span></span>

<span data-ttu-id="9adc1-105">Для выполнения этой процедуры необходимо использовать учетную запись пользователя с ролью "полный доступ" и "Администратор расширенного управления групповыми политиками (для опытных пользователей)" или необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="9adc1-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="9adc1-106">Ознакомьтесь с подробными сведениями в разделе "Дополнительные сведения".</span><span class="sxs-lookup"><span data-stu-id="9adc1-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="9adc1-107">Управление неподдерживаемым объектом групповой политики</span><span class="sxs-lookup"><span data-stu-id="9adc1-107">To control an uncontrolled GPO</span></span>**

1.  <span data-ttu-id="9adc1-108">В дереве **консоли управления групповыми политиками** нажмите кнопку **изменить элемент управления** в лесу и домене, в котором вы хотите управлять объектами групповой политики.</span><span class="sxs-lookup"><span data-stu-id="9adc1-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="9adc1-109">На вкладке **содержание** в области сведений щелкните вкладку **неконтрольные** значения, чтобы отобразить неконтрольные объекты групповой политики.</span><span class="sxs-lookup"><span data-stu-id="9adc1-109">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="9adc1-110">Щелкните правой кнопкой мыши объект групповой политики, для которого нужно настроить управление групповыми политиками, и выберите пункт **элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="9adc1-110">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="9adc1-111">Введите Примечание, которое будет отображаться в журнале объекта групповой политики, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9adc1-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="9adc1-112">После того как окно **прогресса** показывает, что весь ход выполнения завершен, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9adc1-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="9adc1-113">Объект групповой политики удаляется из списка на вкладке " **неуправляемый** " и добавляется на вкладку " **управляемые** ".</span><span class="sxs-lookup"><span data-stu-id="9adc1-113">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Controlled** tab.</span></span>

### <span data-ttu-id="9adc1-114">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="9adc1-114">Additional considerations</span></span>

-   <span data-ttu-id="9adc1-115">По умолчанию для выполнения этой процедуры необходимо быть утверждающим или администратором расширенного управления групповыми политиками (полный доступ).</span><span class="sxs-lookup"><span data-stu-id="9adc1-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="9adc1-116">В частности, необходимо иметь **содержимое списка** и **создать разрешения GPO** для домена.</span><span class="sxs-lookup"><span data-stu-id="9adc1-116">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="9adc1-117">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="9adc1-117">Additional references</span></span>

-   [<span data-ttu-id="9adc1-118">Создание, администрирование и импорт объекта групповой политики</span><span class="sxs-lookup"><span data-stu-id="9adc1-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

 

 





