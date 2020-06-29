---
title: Определение типа приложения для последовательной последовательности (App-V 4,6 SP1)
description: Определение типа приложения для последовательной последовательности (App-V 4,6 SP1)
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817489"
---
# <span data-ttu-id="4769f-103">Определение типа приложения для последовательной последовательности (App-V 4,6 SP1)</span><span class="sxs-lookup"><span data-stu-id="4769f-103">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>


<span data-ttu-id="4769f-104">Вы можете поочередно использовать три основных типа приложений с помощью секвенсора Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="4769f-104">You can sequence three basic types of applications by using Microsoft Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="4769f-105">Определение типа приложения для последовательной последовательности</span><span class="sxs-lookup"><span data-stu-id="4769f-105">To determine which type of application to sequence</span></span>


<span data-ttu-id="4769f-106">Ниже приведена таблица, в которой определяется тип приложения, который нужно последовательное, а также приведены дополнительные сведения о том, как последовательное приложение.</span><span class="sxs-lookup"><span data-stu-id="4769f-106">Use the following table to determine which type of application you should sequence and to obtain more information about how to sequence the application.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4769f-107">Тип приложения</span><span class="sxs-lookup"><span data-stu-id="4769f-107">Application Type</span></span></th>
<th align="left"><span data-ttu-id="4769f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4769f-108">Description</span></span></th>
<th align="left"><span data-ttu-id="4769f-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4769f-109">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4769f-110">Standard</span><span class="sxs-lookup"><span data-stu-id="4769f-110">Standard</span></span></p></td>
<td align="left"><p><span data-ttu-id="4769f-111">Выберите этот параметр, чтобы создать пакет, который будет содержать приложение или набор приложений.</span><span class="sxs-lookup"><span data-stu-id="4769f-111">Select this option to create a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="4769f-112">Этот параметр необходимо выбрать для большинства приложений, которые планируется поочередно.</span><span class="sxs-lookup"><span data-stu-id="4769f-112">You should select this option for most applications that you plan to sequence.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)"><span data-ttu-id="4769f-113">Виртуализация нового стандартного приложения (App-V 4.6 с пакетом обновления 1 (SP1))</span><span class="sxs-lookup"><span data-stu-id="4769f-113">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4769f-114">Надстройка или плагин</span><span class="sxs-lookup"><span data-stu-id="4769f-114">Add-on or Plug-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="4769f-115">Выберите этот параметр, чтобы создать пакет, который расширяет функциональные возможности стандартного приложения, например плагин для Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4769f-115">Select this option to create a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="4769f-116">Кроме того, вы можете использовать подключаемые модули для приложений, установленных в собственном коде, или другой пакет, связанный с помощью динамической композиции наборов.</span><span class="sxs-lookup"><span data-stu-id="4769f-116">Additionally, you can use plug-ins for natively installed applications, or another package that is linked by using Dynamic Suite Composition.</span></span> <span data-ttu-id="4769f-117">Дополнительные сведения о композиции динамических наборов вы узнаете, <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> как использовать динамическую композицию набора </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ).</span><span class="sxs-lookup"><span data-stu-id="4769f-117">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)"><span data-ttu-id="4769f-118">Виртуализация нового надстройки или подключаемого модуля (App-V 4.6 с пакетом обновления 1 (SP1))</span><span class="sxs-lookup"><span data-stu-id="4769f-118">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4769f-119">Старые</span><span class="sxs-lookup"><span data-stu-id="4769f-119">Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="4769f-120">Выберите этот параметр, чтобы создать пакет, который необходим стандартному приложению, например Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4769f-120">Select this option to create a package that is required by a standard application, for example, the Microsoft .NET Framework.</span></span> <span data-ttu-id="4769f-121">Пакеты по промежуточного слоя используются для связывания с другими пакетами с помощью композиции динамических наборов.</span><span class="sxs-lookup"><span data-stu-id="4769f-121">Middleware packages are used for linking to other packages by using Dynamic Suite Composition.</span></span> <span data-ttu-id="4769f-122">Дополнительные сведения о композиции динамических наборов вы узнаете, <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> как использовать динамическую композицию набора </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ).</span><span class="sxs-lookup"><span data-stu-id="4769f-122">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)"><span data-ttu-id="4769f-123">Виртуализация нового ПО промежуточного слоя (App-V 4.6 с пакетом обновления 1 (SP1))</span><span class="sxs-lookup"><span data-stu-id="4769f-123">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4769f-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4769f-124">Related topics</span></span>


[<span data-ttu-id="4769f-125">Задачи для Application Virtualization Sequencer (App-V 4.6 с пакетом обновления 1 (SP1))</span><span class="sxs-lookup"><span data-stu-id="4769f-125">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 




