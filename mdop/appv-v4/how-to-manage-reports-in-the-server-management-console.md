---
title: Управление отчетами на консоли управления серверами
description: Управление отчетами на консоли управления серверами
author: dansimp
ms.assetid: 28d99620-6339-43f6-9288-4aa958607c59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3d70734be04df380e6ce3f4ee8de126503e482e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817142"
---
# <span data-ttu-id="adf79-103">Управление отчетами на консоли управления серверами</span><span class="sxs-lookup"><span data-stu-id="adf79-103">How to Manage Reports in the Server Management Console</span></span>


<span data-ttu-id="adf79-104">Для эффективного управления системой виртуализации приложений вы можете использовать консоль управления сервером Application Virtualization для создания разнообразных отчетов, которые предоставляют сведения о системе.</span><span class="sxs-lookup"><span data-stu-id="adf79-104">To effectively manage the Application Virtualization System, you can use the Application Virtualization Server Management Console to generate a variety of reports that provide information about the system.</span></span> <span data-ttu-id="adf79-105">Эти сведения включают ежедневные сведения об использовании определенного приложения или всех приложений, а также об ошибках системного отслеживания.</span><span class="sxs-lookup"><span data-stu-id="adf79-105">This information includes daily usage information for a specific application or all applications, and system error tracking.</span></span>

**<span data-ttu-id="adf79-106">Примечание.</span><span class="sxs-lookup"><span data-stu-id="adf79-106">Note</span></span>**  
-   <span data-ttu-id="adf79-107">Во время установки установочный сценарий устанавливает только версию средства просмотра отчетов на английском языке.</span><span class="sxs-lookup"><span data-stu-id="adf79-107">During installation, the installation script installs only the English language version of report viewer.</span></span> <span data-ttu-id="adf79-108">Чтобы средство просмотра отчетов отображало правильные сведения на других языках, необходимо установить языковой пакет в следующем расположении: <https://go.microsoft.com/fwlink/?LinkId=131645> .</span><span class="sxs-lookup"><span data-stu-id="adf79-108">For the report viewer to display the correct information in other languages, it is necessary to install a language pack from the following location: <https://go.microsoft.com/fwlink/?LinkId=131645>.</span></span>

-   <span data-ttu-id="adf79-109">Когда вы добавляете или редактируете приложение в консоли управления сервером, необходимо убедиться, что имена и версии приложения точно соответствуют этим файлам в OSD.</span><span class="sxs-lookup"><span data-stu-id="adf79-109">When you add or edit an application in the Server Management Console, you must make sure that the application names and versions exactly match those in the OSD files.</span></span> <span data-ttu-id="adf79-110">Функция отчетов использует поля данных "имя приложения" и "версия", если он определяет данные об использовании приложения, о которых нужно сообщить.</span><span class="sxs-lookup"><span data-stu-id="adf79-110">The reporting feature uses the application names and versions data fields when it identifies application usage data on which to report.</span></span> <span data-ttu-id="adf79-111">Если поля данных не совпадают, записи об использовании будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="adf79-111">If the data fields do not match, the usage records will be skipped.</span></span>

 

## <span data-ttu-id="adf79-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="adf79-112">In This Section</span></span>


<a href="" id="application-virtualization-report-types"></a>[<span data-ttu-id="adf79-113">Типы отчетов Application Virtualization</span><span class="sxs-lookup"><span data-stu-id="adf79-113">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)  
<span data-ttu-id="adf79-114">Представлена информация о доступных типах отчетов.</span><span class="sxs-lookup"><span data-stu-id="adf79-114">Contains information about the available report types.</span></span>

<a href="" id="how-to-create-a-report"></a>[<span data-ttu-id="adf79-115">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="adf79-115">How to Create a Report</span></span>](how-to-create-a-reportserver.md)  
<span data-ttu-id="adf79-116">Пошаговые инструкции по созданию отчета.</span><span class="sxs-lookup"><span data-stu-id="adf79-116">Provides a step-by-step process for creating a report.</span></span>

<a href="" id="how-to-run-a-report"></a>[<span data-ttu-id="adf79-117">Запуск отчета</span><span class="sxs-lookup"><span data-stu-id="adf79-117">How to Run a Report</span></span>](how-to-run-a-reportserver.md)  
<span data-ttu-id="adf79-118">Пошаговые инструкции по запуску отчета.</span><span class="sxs-lookup"><span data-stu-id="adf79-118">Provides a step-by-step process for running a report.</span></span>

<a href="" id="how-to-print-a-report"></a>[<span data-ttu-id="adf79-119">Печать отчета</span><span class="sxs-lookup"><span data-stu-id="adf79-119">How to Print a Report</span></span>](how-to-print-a-reportserver.md)  
<span data-ttu-id="adf79-120">Пошаговые инструкции по печати отчета.</span><span class="sxs-lookup"><span data-stu-id="adf79-120">Provides a step-by-step process for printing a report.</span></span>

<a href="" id="how-to-export-a-report"></a>[<span data-ttu-id="adf79-121">Экспорт отчета</span><span class="sxs-lookup"><span data-stu-id="adf79-121">How to Export a Report</span></span>](how-to-export-a-reportserver.md)  
<span data-ttu-id="adf79-122">Содержит пошаговые инструкции по экспорту отчета.</span><span class="sxs-lookup"><span data-stu-id="adf79-122">Provides a step-by-step process for exporting a report.</span></span>

<a href="" id="how-to-delete-a-report"></a>[<span data-ttu-id="adf79-123">Удаление отчета</span><span class="sxs-lookup"><span data-stu-id="adf79-123">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)  
<span data-ttu-id="adf79-124">Пошаговые инструкции по удалению отчета.</span><span class="sxs-lookup"><span data-stu-id="adf79-124">Provides a step-by-step process for deleting a report.</span></span>

## <span data-ttu-id="adf79-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="adf79-125">Related topics</span></span>


[<span data-ttu-id="adf79-126">Отчет об использовании приложений</span><span class="sxs-lookup"><span data-stu-id="adf79-126">Application Utilization Report</span></span>](application-utilization-reportserver.md)

[<span data-ttu-id="adf79-127">Выполнение задач администрирования на консоли управления серверами Application Virtualization</span><span class="sxs-lookup"><span data-stu-id="adf79-127">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="adf79-128">Отчет об аудите программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="adf79-128">Software Audit Report</span></span>](software-audit-reportserver.md)

[<span data-ttu-id="adf79-129">Отчет об ошибках системы</span><span class="sxs-lookup"><span data-stu-id="adf79-129">System Error Report</span></span>](system-error-reportserver.md)

[<span data-ttu-id="adf79-130">Отчет об использовании системы</span><span class="sxs-lookup"><span data-stu-id="adf79-130">System Utilization Report</span></span>](system-utilization-reportserver.md)

 

 





