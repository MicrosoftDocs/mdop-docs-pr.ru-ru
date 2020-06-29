---
title: Перенос точек расширения из пакета App-V 4.6 в преобразованный пакет App-V 5.1 для всех пользователей на указанном компьютере
description: Перенос точек расширения из пакета App-V 4.6 в преобразованный пакет App-V 5.1 для всех пользователей на указанном компьютере
author: dansimp
ms.assetid: 4ef823a5-3106-44c5-aecc-29edf69c2fbb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 7bac244804b46309a0e0a75cb3742dfe22e92e8f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813880"
---
# <span data-ttu-id="a1276-103">Перенос точек расширения из пакета App-V 4.6 в преобразованный пакет App-V 5.1 для всех пользователей на указанном компьютере</span><span class="sxs-lookup"><span data-stu-id="a1276-103">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>


<span data-ttu-id="a1276-104">Чтобы перенести точки расширения из пакета App-V версии 4.6 в пакет App-V 5,1 с помощью файла конфигурации развертывания, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a1276-104">Use the following procedure to migrate extension points from an App-V4.6 package to a App-V 5.1 package using the deployment configuration file.</span></span>

<span data-ttu-id="a1276-105">**Примечание**  В этой процедуре предполагается, что вы используете последнюю версию App-V 4,6.</span><span class="sxs-lookup"><span data-stu-id="a1276-105">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>  
<span data-ttu-id="a1276-106">Для следующей процедуры не требуется сервер управления App-V 5,1.</span><span class="sxs-lookup"><span data-stu-id="a1276-106">The following procedure does not require an App-V 5.1 management server.</span></span>

 

**<span data-ttu-id="a1276-107">Миграция точек расширения из пакета App-V 4.6 в преобразованный пакет App-v 5,1 с помощью файла конфигурации развертывания</span><span class="sxs-lookup"><span data-stu-id="a1276-107">To migrate extension points from a package from an App-V4.6 package to a converted App-V 5.1 package using the deployment configuration file</span></span>**

1. <span data-ttu-id="a1276-108">Найдите каталог, содержащий файл конфигурации развертывания для пакета, который требуется перенести.</span><span class="sxs-lookup"><span data-stu-id="a1276-108">Locate the directory that contains the deployment configuration file for the package you want to migrate.</span></span> <span data-ttu-id="a1276-109">Чтобы настроить политику, сделайте следующее обновление в разделе **userConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="a1276-109">To set the policy, make the following update to the **userConfiguration** section:</span></span>

   **<span data-ttu-id="a1276-110">ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; ИД пакета&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-110">ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;</span></span>**

   <span data-ttu-id="a1276-111">Ниже приведен пример содержимого из файла конфигурации развертывания.</span><span class="sxs-lookup"><span data-stu-id="a1276-111">The following is an example of content from a deployment configuration file:</span></span>

   <span data-ttu-id="a1276-112">&lt;? XML Version = "1.0"?&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-112">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="a1276-113">&lt;DeploymentConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1276-113">&lt;DeploymentConfiguration</span></span>

   <span data-ttu-id="a1276-114">xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; ИД пакета &gt; DisplayName = &lt; Отображаемое имя&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-114">xmlns="<https://schemas.microsoft.com/appv/2010/deploymentconfiguration>" PackageId=&lt;Package ID&gt; DisplayName=&lt;Display Name&gt;</span></span>

   <span data-ttu-id="a1276-115">&lt;MachineConfiguration/&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-115">&lt;MachineConfiguration/&gt;</span></span>

   <span data-ttu-id="a1276-116">&lt;UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-116">&lt;UserConfiguration&gt;</span></span>

   <span data-ttu-id="a1276-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "истина"</span><span class="sxs-lookup"><span data-stu-id="a1276-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="a1276-118">PackageName = &lt; ИД пакета&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-118">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="a1276-119">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-119">&lt;/UserConfiguration&gt;</span></span>

   <span data-ttu-id="a1276-120">&lt;/DeploymentConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-120">&lt;/DeploymentConfiguration&gt;</span></span>

2. <span data-ttu-id="a1276-121">Чтобы добавить пакет App-V 5,1, введите в командной строке с повышенными привилегиями PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a1276-121">To add the App-V 5.1 package, in an elevated PowerShell command prompt type:</span></span>

   <span data-ttu-id="a1276-122">PS &gt; **$pkg = Add-AppvClientPackage** **—** путь к &lt; местоположению пакета &gt;  - **DynamicDeploymentConfiguration** &lt; путь к файлу конфигурации развертывания&gt;</span><span class="sxs-lookup"><span data-stu-id="a1276-122">PS&gt;**$pkg= Add-AppvClientPackage** **–Path** &lt;Path to package location&gt; -**DynamicDeploymentConfiguration** &lt;Path to the deployment configuration file&gt;</span></span>

   <span data-ttu-id="a1276-123">PS &gt; **AppVClientPackage $pkg**</span><span class="sxs-lookup"><span data-stu-id="a1276-123">PS&gt;**Publish-AppVClientPackage $pkg**</span></span>

3. <span data-ttu-id="a1276-124">Чтобы протестировать миграцию, откройте виртуальное приложение с помощью связанного FTAs или сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="a1276-124">To test the migration, open the virtual application using associated FTAs or shortcuts.</span></span> <span data-ttu-id="a1276-125">Приложение откроется с приложением-V 5,1.</span><span class="sxs-lookup"><span data-stu-id="a1276-125">The application opens with App-V 5.1.</span></span> <span data-ttu-id="a1276-126">Оба: пакет App-V 4,6 и преобразованный пакет App-V 5,1 публикуются для пользователя, но FTAs и сочетания клавиш для приложений предполагались в пакете App-V 5,1.</span><span class="sxs-lookup"><span data-stu-id="a1276-126">Both, the App-V 4.6 package and the converted App-V 5.1 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.1 package.</span></span>

   <span data-ttu-id="a1276-127">**У вас есть предложение App-V**?</span><span class="sxs-lookup"><span data-stu-id="a1276-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a1276-128">Здесь вы можете добавить предложения и проголосовать [здесь](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span><span class="sxs-lookup"><span data-stu-id="a1276-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a1276-129">У вас возникла ошибка App-V?</span><span class="sxs-lookup"><span data-stu-id="a1276-129">Got an App-V issue?</span></span>** <span data-ttu-id="a1276-130">Используйте [Форум TechNet App-V](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span><span class="sxs-lookup"><span data-stu-id="a1276-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a1276-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a1276-131">Related topics</span></span>


[<span data-ttu-id="a1276-132">Возврат точек расширения из пакета App-V 5.1 в пакет App-V 4.6 для всех пользователей на указанном компьютере</span><span class="sxs-lookup"><span data-stu-id="a1276-132">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="a1276-133">Операции, связанные с администрированием и использованием App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="a1276-133">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 




