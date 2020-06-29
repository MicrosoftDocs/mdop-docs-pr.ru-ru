---
title: Подготовка среды для UE-V
description: Подготовка среды для UE-V
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824649"
---
# <span data-ttu-id="3459f-103">Подготовка среды для UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-103">Preparing Your Environment for UE-V</span></span>


<span data-ttu-id="3459f-104">Microsoft User Experience Virtualization (UE-V) перемещает параметры между компьютерами, используя место хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="3459f-104">Microsoft User Experience Virtualization (UE-V) roams settings between computers by the use of a settings storage location.</span></span> <span data-ttu-id="3459f-105">Место хранения параметров — это файловый ресурс, который должен быть настроен во время развертывания агента UE-V.</span><span class="sxs-lookup"><span data-stu-id="3459f-105">The settings storage location is a file share and should be configured during the UE-V Agent deployment.</span></span> <span data-ttu-id="3459f-106">Он должен быть определен либо как место хранения параметров, либо как основной каталог Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3459f-106">It must be defined either as a settings storage location or as an Active Directory home directory.</span></span> <span data-ttu-id="3459f-107">Кроме того, администратор должен настроить сервер времени таким образом, чтобы он поддерживал единую синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="3459f-107">In addition, the administrator should configure a time server to support consistent synchronization.</span></span> <span data-ttu-id="3459f-108">Для подготовки среды для UE-V вы должны иметь в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="3459f-108">To prepare your environment for UE-V, you should consider the following:</span></span>

-   <span data-ttu-id="3459f-109">[Хранилище параметров ue-V](#bkmk-uevsettingsstorage):</span><span class="sxs-lookup"><span data-stu-id="3459f-109">[UE-V Settings Storage](#bkmk-uevsettingsstorage):</span></span>

    -   [<span data-ttu-id="3459f-110">Определение места хранения параметров</span><span class="sxs-lookup"><span data-stu-id="3459f-110">Defining a Settings Storage Location</span></span>](#bkmk-definingsettingsstoragelocation)

    -   [<span data-ttu-id="3459f-111">Использование основного каталога Active Directory с UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-111">Using Active Directory Home Directory with UE-V</span></span>](#bkmk-usingactivedirectoryhomedirectory)

-   [<span data-ttu-id="3459f-112">Синхронизация часов компьютера для синхронизации параметров UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-112">Synchronize Computer Clocks for UE-V Settings Synchronization</span></span>](#bkmk-synchronizecomputerclocks)

-   [<span data-ttu-id="3459f-113">Планирование производительности и пропускной способности</span><span class="sxs-lookup"><span data-stu-id="3459f-113">Performance and Capacity Planning</span></span>](#bkmk-performancecapacityplanning)

<span data-ttu-id="3459f-114">Дополнительные сведения о требованиях к операционной системе и компьютеру можно найти в разделе [Поддерживаемые конфигурации UE-V 1,0](supported-configurations-for-ue-v-10.md).</span><span class="sxs-lookup"><span data-stu-id="3459f-114">For more information about operating system and computer requirements, see [Supported Configurations for UE-V 1.0](supported-configurations-for-ue-v-10.md).</span></span>

## <a href="" id="bkmk-uevsettingsstorage"></a><span data-ttu-id="3459f-115">Хранилище параметров UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-115">UE-V settings storage</span></span>


<span data-ttu-id="3459f-116">Вы можете определить хранилище параметров виртуализации взаимодействия с пользователем в одной из двух конфигураций: расположение хранилища параметров или корневой каталог Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3459f-116">You can define the User Experience Virtualization settings storage in one of two configurations: a settings storage location or an Active Directory home directory.</span></span>

### <a href="" id="bkmk-definingsettingsstoragelocation"></a><span data-ttu-id="3459f-117">Определение места хранения параметров</span><span class="sxs-lookup"><span data-stu-id="3459f-117">Define a settings storage location</span></span>

<span data-ttu-id="3459f-118">Путь к хранилищу параметров UE-V — это стандартная сетевая папка, доступная для пользователей UE-V.</span><span class="sxs-lookup"><span data-stu-id="3459f-118">The UE-V settings storage location is a standard network share that is accessible by UE-V users.</span></span> <span data-ttu-id="3459f-119">Перед определением места хранения параметров необходимо создать корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="3459f-119">Before you define the settings storage location, you must create a root directory.</span></span> <span data-ttu-id="3459f-120">Пользователи, которые будут хранить параметры в общем доступе, должны иметь разрешения на чтение и запись в месте хранения.</span><span class="sxs-lookup"><span data-stu-id="3459f-120">Users who will store settings on the share must have read/write permissions to the storage location.</span></span> <span data-ttu-id="3459f-121">Агент UE-V создаст пользовательские папки под этим корневым каталогом.</span><span class="sxs-lookup"><span data-stu-id="3459f-121">The UE-V Agent will create user-specific folders under this root directory.</span></span> <span data-ttu-id="3459f-122">Место хранения параметров определяется с помощью параметра конфигурации **SettingsStoragePath** .</span><span class="sxs-lookup"><span data-stu-id="3459f-122">The settings storage location is defined by setting the **SettingsStoragePath** configuration option.</span></span> <span data-ttu-id="3459f-123">Этот параметр можно настроить указанными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="3459f-123">This option can be configured in the following ways:</span></span>

-   <span data-ttu-id="3459f-124">При установке агента UE-V с помощью параметра командной строки или пакетного сценария.</span><span class="sxs-lookup"><span data-stu-id="3459f-124">During the installation of the UE-V agent through a command-line parameter or in a batch script.</span></span>

-   <span data-ttu-id="3459f-125">С помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="3459f-125">Using Group Policy.</span></span>

-   <span data-ttu-id="3459f-126">После установки с помощью PowerShell или WMI.</span><span class="sxs-lookup"><span data-stu-id="3459f-126">After installation, by using PowerShell or WMI.</span></span>

<span data-ttu-id="3459f-127">Путь должен быть указан в формате UNC сервера и общего доступа.</span><span class="sxs-lookup"><span data-stu-id="3459f-127">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="3459f-128">Например, **\\\\server\\settingsshare\\**.</span><span class="sxs-lookup"><span data-stu-id="3459f-128">For example, **\\\\server\\settingsshare\\**.</span></span> <span data-ttu-id="3459f-129">Этот параметр конфигурации поддерживает использование переменных для включения конкретных сценариев перемещения.</span><span class="sxs-lookup"><span data-stu-id="3459f-129">This configuration option supports the use of variables to enable specific roaming scenarios.</span></span>

<span data-ttu-id="3459f-130">Вы можете использовать `%username%` переменную с путем UNC для сервера и общего доступа.</span><span class="sxs-lookup"><span data-stu-id="3459f-130">You can use the `%username%` variable with the UNC path of the server and share.</span></span> <span data-ttu-id="3459f-131">Это обеспечит одинаковый набор параметров на всех компьютерах или сеансах, в которых пользователь входит в систему.</span><span class="sxs-lookup"><span data-stu-id="3459f-131">This will provide the same settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="3459f-132">Ниже перечислены сценарии, которые можно использовать для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="3459f-132">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="3459f-133">У пользователей в предприятии есть несколько, аналогично настроенных физических компьютеров и параметры каждого пользователя на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3459f-133">Users in the enterprise have multiple, similarly configured physical computers and each user’s settings should be the same across all computers.</span></span>

2.  <span data-ttu-id="3459f-134">Пользователи в корпоративной среде используют пулы инфраструктуры виртуальных рабочих столов (VDI), где параметры должны храниться в сеансах VDI каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3459f-134">Users in the enterprise use virtual desktop infrastructure (VDI) pools where settings should be retained across each user’s VDI sessions.</span></span>

3.  <span data-ttu-id="3459f-135">У пользователей в предприятии есть один физический компьютер и дополнительно используется VDI.</span><span class="sxs-lookup"><span data-stu-id="3459f-135">Users in the enterprise have one physical computer and additionally use a VDI.</span></span> <span data-ttu-id="3459f-136">Параметры каждого пользователя должны быть одинаковыми при использовании физического компьютера или сеанса VDI.</span><span class="sxs-lookup"><span data-stu-id="3459f-136">Each user’s settings experience should be the same whether using the physical computer or VDI session.</span></span>

4.  <span data-ttu-id="3459f-137">Несколько пользователей используют несколько корпоративных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3459f-137">Multiple enterprise computers are used by multiple users.</span></span> <span data-ttu-id="3459f-138">Параметры каждого пользователя должны быть одинаковыми для всех компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3459f-138">Each user’s settings experience should be the same across all computers.</span></span>

<span data-ttu-id="3459f-139">Вы можете использовать переменные **%username%\\%ComputerName%** с путем UNC для сервера и общего доступа.</span><span class="sxs-lookup"><span data-stu-id="3459f-139">You can use the **%username%\\%computername%** variables with the UNC path of the server and share.</span></span> <span data-ttu-id="3459f-140">Это сохранит параметры для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3459f-140">This will preserve the settings experience for each computer.</span></span> <span data-ttu-id="3459f-141">Ниже перечислены сценарии, которые можно использовать для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="3459f-141">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="3459f-142">У пользователей в предприятии есть несколько физических компьютеров, и вы хотите сохранить параметры для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3459f-142">Users in the enterprise have multiple physical computers and you want to preserve the settings experience for each computer.</span></span>

2.  <span data-ttu-id="3459f-143">Корпоративные компьютеры используются несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="3459f-143">The enterprise computers are used by multiple users.</span></span> <span data-ttu-id="3459f-144">Параметры будут сохранены для каждого компьютера, на котором пользователь входит в систему.</span><span class="sxs-lookup"><span data-stu-id="3459f-144">The settings experience should be preserved for each computer that the user logs into.</span></span>

<span data-ttu-id="3459f-145">Агент UE-V динамически создает путь к хранилищу параметров для определенного пользователя в соответствии с `SettingsStoragePath` параметром конфигурации UE-v и определенными переменными.</span><span class="sxs-lookup"><span data-stu-id="3459f-145">The UE-V agent dynamically creates the user-specific settings storage path based on a UE-V `SettingsStoragePath` configuration setting and the variables that are defined.</span></span>

<span data-ttu-id="3459f-146">Агент UE-V динамически создает скрытую системную папку `SettingsPackages` в каждом пользовательском местоположении хранения.</span><span class="sxs-lookup"><span data-stu-id="3459f-146">The UE-V agent dynamically creates a hidden system folder named `SettingsPackages` within each user-specific storage location.</span></span> <span data-ttu-id="3459f-147">Агент UE-V производит чтение и запись параметров в это расположение, как определено в зарегистрированных шаблонах расположения параметров UE-V.</span><span class="sxs-lookup"><span data-stu-id="3459f-147">The UE-V agent reads and writes settings to this location as defined by registered UE-V settings location templates.</span></span>

<span data-ttu-id="3459f-148">Если место хранения параметров одинаково для набора управляемых компьютеров пользователя, соответствующие параметры UE-V определяются правилом "Последнее запись WINS".</span><span class="sxs-lookup"><span data-stu-id="3459f-148">If the settings storage location is the same for a set of managed computers of a user, the applicable UE-V settings are determined by a “Last write wins” rule.</span></span> <span data-ttu-id="3459f-149">Агент, который запускается на одном компьютере, считывает и записывает в расположение параметров независимо от агентов, которые выполняются на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3459f-149">The agent that runs on one computer reads and writes to the settings location independently of agents that run on other computers.</span></span> <span data-ttu-id="3459f-150">Последними параметрами и значениями записаны параметры, которые применяются при считывании следующего агента из места хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="3459f-150">The last settings and values written are the settings that are applied when the next agent reads from the settings storage location.</span></span> <span data-ttu-id="3459f-151">Дополнительные сведения можно найти [в разделе Развертывание места хранения параметров для UE-V 1,0](deploying-the-settings-storage-location-for-ue-v-10.md).</span><span class="sxs-lookup"><span data-stu-id="3459f-151">For more information, see [Deploying the Settings Storage Location for UE-V 1.0](deploying-the-settings-storage-location-for-ue-v-10.md).</span></span>

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a><span data-ttu-id="3459f-152">Использование основного каталога Active Directory с UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-152">Use Active Directory home directory with UE-V</span></span>

<span data-ttu-id="3459f-153">Если расположение хранилища параметров не настроено для UE-V при развертывании агента, для хранения параметров пакетов расположений используется корневой каталог пользователя Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="3459f-153">If no settings storage location is configured for UE-V when the agent is deployed, then the user’s Active Directory (AD) home directory is used to store settings location packages.</span></span> <span data-ttu-id="3459f-154">Агент UE-V динамически создает папку хранения параметров под корнем основного каталога рекламных объявлений каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3459f-154">The UE-V agent dynamically creates the settings storage folder below the root of the AD home directory of each user.</span></span> <span data-ttu-id="3459f-155">Агент использует корневой каталог Active Directory только в том случае, если место хранения параметров (SettingsStoragePath) в противном случае не определено.</span><span class="sxs-lookup"><span data-stu-id="3459f-155">The agent only uses the Active Directory home directory if a settings storage location (SettingsStoragePath) is not otherwise defined.</span></span>

## <a href="" id="bkmk-synchronizecomputerclocks"></a><span data-ttu-id="3459f-156">Синхронизация часов компьютера для синхронизации параметров UE-V</span><span class="sxs-lookup"><span data-stu-id="3459f-156">Synchronize computer clocks for UE-V settings synchronization</span></span>


<span data-ttu-id="3459f-157">Компьютеры, на которых запущен агент UE-V Agent для синхронизации параметров, должны использовать сервер времени.</span><span class="sxs-lookup"><span data-stu-id="3459f-157">Computers that run the UE-V agent to synchronize settings must use a time server.</span></span> <span data-ttu-id="3459f-158">Метки времени используются для определения необходимости синхронизации параметров из места хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="3459f-158">Time stamps are used to determine if settings need to be synchronized from the settings storage location.</span></span> <span data-ttu-id="3459f-159">Если часы компьютера неверны, более старые параметры могут переопределять более новые параметры, или новые параметры могут быть не сохранены в хранилище параметров.</span><span class="sxs-lookup"><span data-stu-id="3459f-159">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span> <span data-ttu-id="3459f-160">Использование сервера времени позволяет UE-V поддерживать единообразные параметры.</span><span class="sxs-lookup"><span data-stu-id="3459f-160">The use of a time server enables UE-V to maintain a consistent settings experience.</span></span>

## <a href="" id="bkmk-performancecapacityplanning"></a><span data-ttu-id="3459f-161">Планирование производительности и пропускной способности</span><span class="sxs-lookup"><span data-stu-id="3459f-161">Performance and capacity planning</span></span>


<span data-ttu-id="3459f-162">Требования к мощности для UE-V можно определить с помощью стандартной емкости диска и мониторинга работоспособности сети.</span><span class="sxs-lookup"><span data-stu-id="3459f-162">Capacity requirements for UE-V can be determined by use of standard disk capacity and network health monitoring.</span></span> <span data-ttu-id="3459f-163">UE-V использует общий доступ к блоку сообщений сервера (SMB) для хранения пакетов параметров.</span><span class="sxs-lookup"><span data-stu-id="3459f-163">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="3459f-164">Размер пакетов параметров зависит от параметров, заданных для определенного приложения.</span><span class="sxs-lookup"><span data-stu-id="3459f-164">The size of settings packages varies depending on the settings information for a specific application.</span></span> <span data-ttu-id="3459f-165">Несмотря на то, что большая часть пакетов параметров очень мала, синхронизация потенциально больших файлов, например изображений рабочего стола, может привести к снижению производительности, особенно в медленных сетях.</span><span class="sxs-lookup"><span data-stu-id="3459f-165">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span> <span data-ttu-id="3459f-166">Чтобы свести к минимуму проблемы с задержкой сети, необходимо создать места хранения параметров в тех же локальных сетях, где находятся компьютеры пользователей.</span><span class="sxs-lookup"><span data-stu-id="3459f-166">To minimize problems with network latency, you should create settings storage locations on the same local networks where the users’ computers reside.</span></span>

<span data-ttu-id="3459f-167">По умолчанию синхронизация UE-V выполняется через 2 секунды, если сеть работает медленно или пакет параметров имеет большой размер.</span><span class="sxs-lookup"><span data-stu-id="3459f-167">By default, the UE-V synchronization will time out after 2 seconds if the network is slow or the settings package is large.</span></span> <span data-ttu-id="3459f-168">Время ожидания можно настроить с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="3459f-168">You can configure the timeout with Group Policy.</span></span> <span data-ttu-id="3459f-169">Дополнительные сведения о том, как настроить время ожидания, приведены в разделе [Настройка UE-V с объектами групповой политики](configuring-ue-v-with-group-policy-objects.md).</span><span class="sxs-lookup"><span data-stu-id="3459f-169">For more information about how to set the timeout, see [Configuring UE-V with Group Policy Objects](configuring-ue-v-with-group-policy-objects.md).</span></span>

## <span data-ttu-id="3459f-170">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3459f-170">Related topics</span></span>


[<span data-ttu-id="3459f-171">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="3459f-171">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="3459f-172">Планирование UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="3459f-172">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="3459f-173">Поддерживаемые конфигурации UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="3459f-173">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

 

 




