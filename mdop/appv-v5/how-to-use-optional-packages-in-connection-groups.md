---
title: Использование дополнительных пакетов в группах соединений
description: Использование дополнительных пакетов в группах соединений
author: dansimp
ms.assetid: 4d08a81b-55e5-471a-91dc-9a684fb3c9a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 64a2c0758294bfa617d3d85f888cfce3a2c0d21e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813632"
---
# <span data-ttu-id="374c6-103">Использование дополнительных пакетов в группах соединений</span><span class="sxs-lookup"><span data-stu-id="374c6-103">How to Use Optional Packages in Connection Groups</span></span>


<span data-ttu-id="374c6-104">Начиная с Microsoft Application Virtualization (App-V) 5,0 с пакетом обновления 3 (SP3), вы можете добавить дополнительные пакеты в группы соединений для упрощения управления группами подключений.</span><span class="sxs-lookup"><span data-stu-id="374c6-104">Starting in Microsoft Application Virtualization (App-V) 5.0 SP3, you can add optional packages to your connection groups to simplify connection group management.</span></span> <span data-ttu-id="374c6-105">В приведенной ниже таблице кратко описаны задачи, которые можно выполнить с помощью дополнительных пакетов, и приведены ссылки на инструкции для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="374c6-105">The following table summarizes the tasks that you can complete more easily by using optional packages, and provides links to instructions for each task.</span></span>

<span data-ttu-id="374c6-106">**Примечание** 
 **Необязательные пакеты поддерживаются только в App-V 5,0 SP3.**</span><span class="sxs-lookup"><span data-stu-id="374c6-106">**Note**
**Optional packages are supported only in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="374c6-107">Прежде чем использовать дополнительные пакеты, ознакомьтесь [с требованиями для использования необязательных пакетов в группах соединений](#bkmk-reqs-using-cg).</span><span class="sxs-lookup"><span data-stu-id="374c6-107">Before using optional packages, see [Requirements for using optional packages in connection groups](#bkmk-reqs-using-cg).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-108">Ссылка на инструкции</span><span class="sxs-lookup"><span data-stu-id="374c6-108">Link to instructions</span></span></th>
<th align="left"><span data-ttu-id="374c6-109">Задача</span><span class="sxs-lookup"><span data-stu-id="374c6-109">Task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)"><span data-ttu-id="374c6-110">Использование одной группы подключения с необязательными пакетами для нескольких пользователей, у которых есть разные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-110">Use one connection group, with optional packages, for multiple users who have different packages entitled to them</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="374c6-111">Используйте одну группу подключения, чтобы сделать различные группы приложений и подключаемых модулей доступными для разных конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="374c6-111">Use a single connection group to make different groups of applications and plug-ins available to different end users.</span></span></p>
<p><span data-ttu-id="374c6-112">Например, вы хотите распространить Microsoft Office для всех конечных пользователей, но распространите различные подключаемые модули для разных подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="374c6-112">For example, you want to distribute Microsoft Office to all end users, but distribute different plug-ins to different subsets of users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)"><span data-ttu-id="374c6-113">Отменить публикацию или удалить дополнительный пакет или отменить публикацию дополнительного пакета, а затем повторно опубликовать его позже без изменения группы подключения</span><span class="sxs-lookup"><span data-stu-id="374c6-113">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="374c6-114">Отменить публикацию, удалить или повторно опубликовать необязательный пакет, не отключая, удаляя, изменяя, добавляйте и заново включайте группу соединения в клиенте App-V.</span><span class="sxs-lookup"><span data-stu-id="374c6-114">Unpublish, delete, or republish an optional package without having to disable, remove, edit, add, and re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="374c6-115">Кроме того, вы можете отменить публикацию дополнительного пакета и повторно опубликовать его позже, не отключая и не перепубликуя группу подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-115">You can also unpublish the optional package and republish it later without having to disable or republish the connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a><span data-ttu-id="374c6-116">Использование одной группы подключения с необязательными пакетами для нескольких пользователей с разными пакетами.</span><span class="sxs-lookup"><span data-stu-id="374c6-116">Use one connection group, with optional packages, for multiple users with different packages entitled to them</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-117">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="374c6-117">Task description</span></span></th>
<th align="left"><span data-ttu-id="374c6-118">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="374c6-118">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="374c6-119">С помощью App-V 5,0 SP3</span><span class="sxs-lookup"><span data-stu-id="374c6-119">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="374c6-120">Вы можете добавлять в группы соединений дополнительные пакеты, что позволяет использовать различные сочетания приложений и подключаемые модули для разных конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="374c6-120">You can add optional packages to connection groups, which enables you to provide different combinations of applications and plug-ins to different end users.</span></span></p>
<p><strong><span data-ttu-id="374c6-121">Пример </strong> : вы хотите распространить приложение Microsoft Office для конечных пользователей, но включите определенный плагин для всего набора пользователей.</span><span class="sxs-lookup"><span data-stu-id="374c6-121">Example</strong>: You want to distribute Microsoft Office to your end users, but enable a certain plug-in for only a subset of users.</span></span></p>
<p><span data-ttu-id="374c6-122">Для этого создайте группу подключений, которая включает пакет с Office, и другой пакет с подключаемыми модулями Office, а затем сделайте пакет подключаемым модулем необязательным.</span><span class="sxs-lookup"><span data-stu-id="374c6-122">To do this, create a connection group that contains a package with Office, and another package with Office plug-ins, and then make the plug-ins package optional.</span></span></p>
<p><span data-ttu-id="374c6-123">Конечные пользователи, у которых нет прав на доступ к пакету для подключения к плагину, по-прежнему смогут запускать Office.</span><span class="sxs-lookup"><span data-stu-id="374c6-123">End users who are not entitled to the plug-in package will still be able to run Office.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-124">Метод</span><span class="sxs-lookup"><span data-stu-id="374c6-124">Method</span></span></th>
<th align="left"><span data-ttu-id="374c6-125">Действия</span><span class="sxs-lookup"><span data-stu-id="374c6-125">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="374c6-126">Сервер App-V Server — консоль управления</span><span class="sxs-lookup"><span data-stu-id="374c6-126">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="374c6-127">На консоли управления выберите пакеты, <strong> </strong> чтобы открыть страницу пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-127">In the Management Console, select <strong>PACKAGES</strong> to open the PACKAGES page.</span></span></p></li>
<li><p><span data-ttu-id="374c6-128">Выберите <strong> группы подключений </strong> , чтобы отобразить библиотеку групп подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-128">Select <strong>CONNECTION GROUPS</strong> to display the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="374c6-129">Выберите нужную группу подключений в библиотеке групп соединений.</span><span class="sxs-lookup"><span data-stu-id="374c6-129">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="374c6-130">Нажмите кнопку <strong> изменить </strong> в области подключенные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-130">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="374c6-131"><strong> </strong> Рядом с названием пакета выберите пункт необязательный.</span><span class="sxs-lookup"><span data-stu-id="374c6-131">Select <strong>Optional</strong> next to the package name.</span></span></p></li>
<li><p><span data-ttu-id="374c6-132">Установите <strong> флажок Добавить пакет для доступа к группе </strong> .</span><span class="sxs-lookup"><span data-stu-id="374c6-132">Select the <strong>ADD PACKAGE ACCESS TO GROUP ACCESS</strong> check box.</span></span> <span data-ttu-id="374c6-133">Этот обязательный этап добавляет в группу подключения данные, которые вы настроили ранее, когда вы назначили пакеты группам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="374c6-133">This required step adds to the connection group the package entitlements that you configured earlier when you assigned packages to Active Directory groups.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="374c6-134">Сервер App-V-командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="374c6-134">App-V Server - PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="374c6-135">Используйте следующий командлет и укажите <strong> параметр-Optional </strong> :</span><span class="sxs-lookup"><span data-stu-id="374c6-135">Use the following cmdlet, and specify the <strong>-Optional</strong> parameter:</span></span></p>
<p><strong><span data-ttu-id="374c6-136">Add-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="374c6-136">Add-AppvServerConnectionGroupPackage</span></span></strong></p>
<p><strong><span data-ttu-id="374c6-137">Максимальное</span><span class="sxs-lookup"><span data-stu-id="374c6-137">Syntax:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong><span data-ttu-id="374c6-138">Пример.</span><span class="sxs-lookup"><span data-stu-id="374c6-138">Example:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="374c6-139">Клиент App-V на отдельном компьютере</span><span class="sxs-lookup"><span data-stu-id="374c6-139">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="374c6-140">Создайте XML-документ группы подключения и задайте <strong> </strong> для атрибута "тег пакета <strong> </strong> <strong> " параметр "истина".</span><span class="sxs-lookup"><span data-stu-id="374c6-140">Create the connection group XML document, and set the <strong>Package</strong> tag attribute <strong>IsOptional</strong> to <strong>“true”.</span></span></strong></p></li>
<li><p><span data-ttu-id="374c6-141">Чтобы добавить и включить группу подключения, используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="374c6-141">Use the following cmdlets to add and enable the connection group:</span></span></p>
<ul>
<li><p><span data-ttu-id="374c6-142">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="374c6-142">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="374c6-143">Enable-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="374c6-143">Enable-AppvClientConnectionGroup</span></span></p></li>
</ul></li>
</ol>
<p><strong><span data-ttu-id="374c6-144">Пример XML-документа группы подключения с дополнительными пакетами:</span><span class="sxs-lookup"><span data-stu-id="374c6-144">Example connection group XML document with optional packages:</span></span></strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="374c6-145">В версиях, предшествующих App-V 5,0 с пакетом обновления 3 (SP3)</span><span class="sxs-lookup"><span data-stu-id="374c6-145">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="374c6-146">Чтобы сделать определенные пользователи доступными для конкретных пользователей, вам пришлось создать большое количество групп соединений.</span><span class="sxs-lookup"><span data-stu-id="374c6-146">You had to create many connection groups to make specific application and plug-in combinations available to specific users.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a><span data-ttu-id="374c6-147">Отменить публикацию или удалить дополнительный пакет или отменить публикацию дополнительного пакета, а затем повторно опубликовать его позже без изменения группы подключения</span><span class="sxs-lookup"><span data-stu-id="374c6-147">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-148">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="374c6-148">Task description</span></span></th>
<th align="left"><span data-ttu-id="374c6-149">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="374c6-149">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="374c6-150">С помощью App-V 5,0 SP3</span><span class="sxs-lookup"><span data-stu-id="374c6-150">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="374c6-151">Вы можете отменить публикацию, удалить или повторно опубликовать необязательный пакет, который находится в группе подключения, не отключая и не перезапуская группу соединения в клиенте App-V.</span><span class="sxs-lookup"><span data-stu-id="374c6-151">You can unpublish, delete, or republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="374c6-152">Кроме того, вы можете отменить публикацию дополнительного пакета и повторно опубликовать его позже, не отключая и не перепубликуя группу подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-152">You can also unpublish an optional package and republish it later without having to disable or republish the connection group.</span></span></p>
<p><strong><span data-ttu-id="374c6-153">Пример </strong> : Если вы публикуете дополнительный пакет, содержащий надстройку Microsoft Office, и хотите удалить его, вы можете отменить публикацию пакета, не отключая группу подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-153">Example</strong>: If you publish an optional package that contains a Microsoft Office plug-in, and you want to remove the plug-in, you can unpublish the package without having to disable the connection group.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-154">Метод</span><span class="sxs-lookup"><span data-stu-id="374c6-154">Method</span></span></th>
<th align="left"><span data-ttu-id="374c6-155">Действия</span><span class="sxs-lookup"><span data-stu-id="374c6-155">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="374c6-156">Сервер App-V Server — консоль управления</span><span class="sxs-lookup"><span data-stu-id="374c6-156">App-V Server – Management Console</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="374c6-157">Чтобы отменить публикацию пакета: на консоли управления выберите пункт выбрать <strong> </strong> страницу пакетов, щелкните правой кнопкой мыши пакет, который нужно отменить, и выберите команду <strong> отменить публикацию </strong> .</span><span class="sxs-lookup"><span data-stu-id="374c6-157">To unpublish the package: In the Management Console, select elect the <strong>PACKAGES</strong> page, right-click the package that you want to unpublish, and click <strong>unpublish</strong>.</span></span></p></li>
<li><p><span data-ttu-id="374c6-158">Чтобы удалить дополнительный пакет из группы подключения, <strong> </strong> выберите пакет, который вы хотите удалить, и щелкните стрелку вправо, чтобы удалить пакет из области групп подключений в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="374c6-158">To remove an optional package from a connection group: On the <strong>CONNECTION GROUPS</strong> page, select the package that you want to remove, and click the right arrow to remove the package from the connection group pane on the bottom left.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="374c6-159">Клиент App-V на отдельном компьютере</span><span class="sxs-lookup"><span data-stu-id="374c6-159">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="374c6-160">Используйте следующие существующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="374c6-160">Use the following existing cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="374c6-161">Отмена публикации — AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="374c6-161">Unpublish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="374c6-162">Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="374c6-162">Remove-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="374c6-163">Дополнительные сведения <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> можно найти в разделе Управление пакетами приложений App-V 5,0, запущенными на отдельном компьютере с помощью PowerShell </a> .</span><span class="sxs-lookup"><span data-stu-id="374c6-163">For more information, see <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="374c6-164">В версиях, предшествующих App-V 5,0 с пакетом обновления 3 (SP3)</span><span class="sxs-lookup"><span data-stu-id="374c6-164">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="374c6-165">Вам пришлось:</span><span class="sxs-lookup"><span data-stu-id="374c6-165">You had to:</span></span></p>
<ol>
<li><p><span data-ttu-id="374c6-166">Удалите группу подключений с каждого клиентского компьютера App-V, на котором он был включен.</span><span class="sxs-lookup"><span data-stu-id="374c6-166">Remove the connection group from each App-V Client computer where it was enabled.</span></span></p></li>
<li><p><span data-ttu-id="374c6-167">Отмена публикации пакета.</span><span class="sxs-lookup"><span data-stu-id="374c6-167">Unpublish the package.</span></span></p></li>
<li><p><span data-ttu-id="374c6-168">Удалите пакет из определения группы подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-168">Remove the package from the connection group’s definition.</span></span></p></li>
<li><p><span data-ttu-id="374c6-169">Повторно опубликуйте группу подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-169">Republish the connection group.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a><span data-ttu-id="374c6-170">Требования для использования необязательных пакетов в группах соединений</span><span class="sxs-lookup"><span data-stu-id="374c6-170">Requirements for using optional packages in connection groups</span></span>


<span data-ttu-id="374c6-171">Прежде чем использовать дополнительные пакеты в группах соединений, ознакомьтесь с приведенными ниже требованиями.</span><span class="sxs-lookup"><span data-stu-id="374c6-171">Review the following requirements before using optional packages in connection groups:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374c6-172">Требование</span><span class="sxs-lookup"><span data-stu-id="374c6-172">Requirement</span></span></th>
<th align="left"><span data-ttu-id="374c6-173">Сведения</span><span class="sxs-lookup"><span data-stu-id="374c6-173">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="374c6-174">Группы соединения должны содержать по крайней мере один необязательный пакет.</span><span class="sxs-lookup"><span data-stu-id="374c6-174">Connection groups must contain at least one non-optional package.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="374c6-175">Убедитесь, что вы удовлетворены этим требованием, так как сервер App-V и командлет PowerShell не проверяют выполнение требования.</span><span class="sxs-lookup"><span data-stu-id="374c6-175">Check carefully that you meet this requirement, as the App-V Server and the PowerShell cmdlet don’t validate that the requirement has been met.</span></span></p></li>
<li><p><span data-ttu-id="374c6-176">Если вы случайно создали группу подключений, которая не содержит по крайней мере один необязательный пакет, и пользователь попытается открыть упакованное приложение в этой группе, произойдет сбой группы подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-176">If you accidentally create a connection group that does not contain at least one non-optional package, and the end user tries to open a packaged application in that connection group, the connection group will fail.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="374c6-177">Опубликованные пользователем группы подключения могут содержать пакеты, опубликованные глобально или для пользователей.</span><span class="sxs-lookup"><span data-stu-id="374c6-177">User-published connection groups can contain packages that are published globally or to the user.</span></span></p></li>
<li><p><span data-ttu-id="374c6-178">Глобальные опубликованные группы подключения должны содержать только глобально опубликованные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-178">Globally published connection groups must contain only globally published packages.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="374c6-179">Глобальные опубликованные группы подключения должны содержать пакеты, которые публикуются глобально, чтобы обеспечить доступность пакетов при запуске виртуальной среды группы подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-179">Globally published connection groups must contain packages that are published globally to ensure that the packages will be available when starting the connection group’s virtual environment.</span></span></p>
<p><span data-ttu-id="374c6-180">При попытке добавления или включения глобальных опубликованных групп подключений, содержащих опубликованные пользователем пакеты, произойдет сбой группы подключения.</span><span class="sxs-lookup"><span data-stu-id="374c6-180">If you try to add or enable globally published connection groups that contain user-published packages, the connection group will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="374c6-181">Перед публикацией группы подключения, содержащей эти пакеты, необходимо опубликовать все необязательные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-181">You must publish all non-optional packages before publishing the connection group that contains those packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="374c6-182">Виртуальная среда группы соединения не может быть запущена, если не указаны необязательные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-182">A connection group’s virtual environment cannot start if any non-optional packages are missing.</span></span></p>
<p><span data-ttu-id="374c6-183">Клиент App-V не может добавить или включить группу соединения, если не были опубликованы какие-либо необязательные пакеты.</span><span class="sxs-lookup"><span data-stu-id="374c6-183">The App-V Client fails to add or enable a connection group if any non-optional packages have not been published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="374c6-184">Прежде чем отменять публикацию глобально опубликованного пакета, убедитесь в том, что для групп подключения, которые имеют право для всех пользователей на этом компьютере, больше не требуется пакет.</span><span class="sxs-lookup"><span data-stu-id="374c6-184">Before you unpublish a globally published package, ensure that the connection groups that are entitled to all the users on that computer no longer require the package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="374c6-185">Система не проверяет, является ли пакет частью группы подключения другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="374c6-185">The system does not check whether the package is part of another user’s connection group.</span></span> <span data-ttu-id="374c6-186">После отмены публикации глобального пакета он будет недоступен каждому пользователю компьютера, поэтому убедитесь, что группы подключений пользователей больше не содержат пакет, или сделайте пакет необязательным.</span><span class="sxs-lookup"><span data-stu-id="374c6-186">Unpublishing a global package will make it unavailable to every user on that computer, so make sure that each user’s connection groups no longer contain the package, or alternatively make the package optional.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="374c6-187">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="374c6-187">Related topics</span></span>


[<span data-ttu-id="374c6-188">Управление связывающими группами</span><span class="sxs-lookup"><span data-stu-id="374c6-188">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





