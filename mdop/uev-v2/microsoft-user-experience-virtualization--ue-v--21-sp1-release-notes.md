---
title: Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 2.1 с пакетом обновления 1 (SP1)
description: Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 2.1 с пакетом обновления 1 (SP1)
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825532"
---
# <span data-ttu-id="147e7-103">Заметки о выпуске для Microsoft User Experience Virtualization (UE-V) 2.1 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="147e7-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>


<span data-ttu-id="147e7-104">Чтобы найти заметки о выпуске Microsoft User Experience Virtualization 2,1 с пакетом обновления 1 (SP1), нажмите Ctrl + F.</span><span class="sxs-lookup"><span data-stu-id="147e7-104">To search Microsoft User Experience Virtualization 2.1 SP1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="147e7-105">Перед установкой UE-V вы должны внимательно прочитать эти заметки о выпуске.</span><span class="sxs-lookup"><span data-stu-id="147e7-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="147e7-106">Заметки о выпуске содержат сведения, необходимые для успешной установки виртуализации взаимодействия с пользователем, и содержат дополнительные сведения, недоступные в документации по продукту.</span><span class="sxs-lookup"><span data-stu-id="147e7-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="147e7-107">Если между этими заметками о выпуске и другой документацией UE-V есть различия, Последнее изменение должно считаться полномочным.</span><span class="sxs-lookup"><span data-stu-id="147e7-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="147e7-108">Эти заметки о выпуске заменяют содержимое, которое входит в состав этого продукта.</span><span class="sxs-lookup"><span data-stu-id="147e7-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="147e7-109">Предоставление отзыва</span><span class="sxs-lookup"><span data-stu-id="147e7-109">Providing feedback</span></span>


<span data-ttu-id="147e7-110">Расскажите нам, что вы думаете о нашей документации для MDOP, предоставив нам свой отзыв и комментарии.</span><span class="sxs-lookup"><span data-stu-id="147e7-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="147e7-111">Отправьте отзыв о документации в [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span><span class="sxs-lookup"><span data-stu-id="147e7-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="147e7-112">Известные проблемы UE-V</span><span class="sxs-lookup"><span data-stu-id="147e7-112">UE-V known issues</span></span>


<span data-ttu-id="147e7-113">В этом разделе содержатся заметки о выпуске для функции User Experience Virtualization 2,1 SP1.</span><span class="sxs-lookup"><span data-stu-id="147e7-113">This section contains release notes for User Experience Virtualization 2.1 SP1.</span></span>

### <span data-ttu-id="147e7-114">Шаблоны расположения параметров UE-V для Skype приводят к сбою в работе Skype</span><span class="sxs-lookup"><span data-stu-id="147e7-114">UE-V settings location templates for Skype cause Skype to crash</span></span>

<span data-ttu-id="147e7-115">Если пользователь создает допустимый шаблон расположения параметров для классического приложения Skype, регистрирует его, а затем запускает классическое приложение Skype, и Skype завершает работу со сбоем.</span><span class="sxs-lookup"><span data-stu-id="147e7-115">When a user generates a valid settings location template for the Skype desktop application, registers it, and then launches the Skype desktop application, Skype crashes.</span></span> <span data-ttu-id="147e7-116">ACCESS \ _VIOLATION записывается в журнал событий приложений.</span><span class="sxs-lookup"><span data-stu-id="147e7-116">An ACCESS\_VIOLATION is recorded in the Application Event Log.</span></span>

<span data-ttu-id="147e7-117">ВРЕМЕННОе решение: удаление и Отмена регистрации шаблона Skype для обеспечения повторной работы Skype.</span><span class="sxs-lookup"><span data-stu-id="147e7-117">WORKAROUND: Remove or unregister the Skype template to allow Skype to work again.</span></span>

### <span data-ttu-id="147e7-118">Возможны ошибки в существующих сценариях для автоматической установки UE-V</span><span class="sxs-lookup"><span data-stu-id="147e7-118">Existing scripts for silent installations of UE-V may fail</span></span>

<span data-ttu-id="147e7-119">Два изменения, внесенные в установщик UE-V, могут привести к сбою в сценариях установки UE-v 2,1 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="147e7-119">Two changes made to the UE-V installer can cause silent installation scripts that worked for previous versions of UE-V to fail when installing UE-V 2.1 SP1.</span></span> <span data-ttu-id="147e7-120">Первый является новым требованием, согласно которому пользователи должны принять условия лицензионного соглашения и принять или отклонить участие в программе улучшения качества программного обеспечения (CEIP), даже при автоматической установке.</span><span class="sxs-lookup"><span data-stu-id="147e7-120">The first is a new requirement that users must accept the license terms and agree to or decline participation in the Customer Experience Improvement Program (CEIP), even during a silent installation.</span></span> <span data-ttu-id="147e7-121">Использование параметра/q больше не подходит для указания принятия условий лицензии и соглашения для участия в программе улучшения качества программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="147e7-121">Using the /q parameter is no longer sufficient to indicate acceptance of the license terms and agreement to participate in CEIP.</span></span>

<span data-ttu-id="147e7-122">Во-вторых, установщик теперь принудительно перезапускает компьютер после установки UE-V Agent.</span><span class="sxs-lookup"><span data-stu-id="147e7-122">Second, the installer now forces a computer restart after installing the UE-V Agent.</span></span> <span data-ttu-id="147e7-123">Это может привести к сбою сценария установки, если он не ожидается перезапуском (например, он сначала устанавливает агент UE-V Agent, а затем немедленно устанавливает генератор).</span><span class="sxs-lookup"><span data-stu-id="147e7-123">This can cause an install script to fail if it is not expecting the restart (for example, it installs the UE-V Agent first and then immediately installs the generator).</span></span>

<span data-ttu-id="147e7-124">ВРЕМЕННОе решение: в установщике UE-V (MSI) есть два новых параметра командной строки, поддерживающих автоматическое установка.</span><span class="sxs-lookup"><span data-stu-id="147e7-124">WORKAROUND: The UE-V installer (.msi) has two new command-line parameters that support silent installations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="147e7-125">Параметр</span><span class="sxs-lookup"><span data-stu-id="147e7-125">Parameter</span></span></th>
<th align="left"><span data-ttu-id="147e7-126">Описание</span><span class="sxs-lookup"><span data-stu-id="147e7-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="147e7-127">/ACCEPTLICENSETERMS = true</span><span class="sxs-lookup"><span data-stu-id="147e7-127">/ACCEPTLICENSETERMS=True</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="147e7-128">Установите для этого параметра <strong> значение истина </strong> , чтобы автоматически установить UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-128">Set this parameter to <strong>True</strong> to install UE-V silently.</span></span> <span data-ttu-id="147e7-129">Добавление этого параметра означает, что пользователь принимает условия лицензии UE-V (по умолчанию):%ProgramFiles%\Microsoft User Experience Virtualization\Agent</span><span class="sxs-lookup"><span data-stu-id="147e7-129">Adding this parameter implies that the user accepts the UE-V license terms, which are found (by default) here: %ProgramFiles%\Microsoft User Experience Virtualization\Agent</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="147e7-130">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="147e7-130">/NORESTART</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="147e7-131">Этот параметр предотвращает обязательную перезагрузку после установки агента UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-131">This parameter prevents the mandatory restart after the UE-V agent is installed.</span></span> <span data-ttu-id="147e7-132">Код возврата 3010 указывает на то, что требуется перезагрузка перед использованием UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-132">A return code of 3010 indicates that a restart is required prior to using UE-V.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="147e7-133">Параметры реестра не синхронизируются между приложением App-V и приложениями машинного кода на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="147e7-133">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="147e7-134">Если на компьютере установлено приложение, установленное как с помощью Application Virtualization (App-V), так и локально с помощью установщика Windows (MSI-файла), параметры, основанные на реестре, не синхронизируются между этими технологиями.</span><span class="sxs-lookup"><span data-stu-id="147e7-134">When a computer has an application that is installed through both Application Virtualization (App-V) and locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="147e7-135">ВРЕМЕННОе решение: чтобы устранить эту проблему, запустите приложение, выбрав одну из двух технологий, но не то, и другое.</span><span class="sxs-lookup"><span data-stu-id="147e7-135">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="147e7-136">Непредсказуемые результаты с установленными приложениями Office 2010 и Office 2013</span><span class="sxs-lookup"><span data-stu-id="147e7-136">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="147e7-137">Если у пользователя установлен и Office 2010, и Office 2013, все общие параметры, которые поддерживаются двумя версиями Office, перемещаются UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-137">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="147e7-138">Это может привести к тому, что размер пакета Office 2010 станет довольно большим или привести к непредсказуемым конфликтам с 2013, особенно если используется Office 365.</span><span class="sxs-lookup"><span data-stu-id="147e7-138">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="147e7-139">ВРЕМЕННОе решение: Установите только одну версию Office или ограничьте параметры, синхронизируемые агентом UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-139">WORKAROUND: Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="147e7-140">Удаление и повторная установка приложения для Windows 8 восстанавливает исходное состояние параметров</span><span class="sxs-lookup"><span data-stu-id="147e7-140">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="147e7-141">При использовании синхронизации параметров UE-V для приложения Windows 8, если пользователь удаляет приложение, а затем переустанавливает приложение, параметры приложения возвращаются к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="147e7-141">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="147e7-142">Это происходит из-за того, что при удалении удаляется локальная (кэшированная) копия параметров приложения, но не удаляется локальный пакет параметров UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-142"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="147e7-143">После повторной установки и запуска приложения UE-V собирает параметры приложения, которые были восстановлены в приложении по умолчанию, а затем загружают параметры по умолчанию в центральное место хранения.</span><span class="sxs-lookup"><span data-stu-id="147e7-143"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="147e7-144">Другие компьютеры, на которых запущено приложение, затем скачайте параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="147e7-144"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="147e7-145">Такое поведение аналогично поведению классических приложений.</span><span class="sxs-lookup"><span data-stu-id="147e7-145"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="147e7-146">ВРЕМЕННОе решение: нет.</span><span class="sxs-lookup"><span data-stu-id="147e7-146">WORKAROUND: None.</span></span>

### <span data-ttu-id="147e7-147">UE-V не поддерживает перемещаемые параметры между 32-битным и 64-разрядными версиями Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="147e7-147">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="147e7-148">Мы рекомендуем установить 32-разрядную версию Microsoft Office для 32-и 64-разрядных операционных систем.</span><span class="sxs-lookup"><span data-stu-id="147e7-148">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="147e7-149">Чтобы выбрать нужную вам версию Microsoft Office, щелкните здесь.</span><span class="sxs-lookup"><span data-stu-id="147e7-149">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="147e7-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="147e7-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="147e7-151">UE-V поддерживает перемещаемые параметры между идентичными версиями Office.</span><span class="sxs-lookup"><span data-stu-id="147e7-151">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="147e7-152">Например, 32-разрядные параметры Office будут перемещаться между всеми 32-разрядными экземплярами Office.</span><span class="sxs-lookup"><span data-stu-id="147e7-152">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="147e7-153">UE-V не поддерживает перемещаемые параметры между 32-битным и 64-разрядными версиями Office.</span><span class="sxs-lookup"><span data-stu-id="147e7-153">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="147e7-154">ВРЕМЕННОе решение: нет</span><span class="sxs-lookup"><span data-stu-id="147e7-154">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="147e7-155">MSI не локализованы</span><span class="sxs-lookup"><span data-stu-id="147e7-155">MSI’s are not localized</span></span>

<span data-ttu-id="147e7-156">UE-V включает локализованную программу установки для агента UE-V и генератора UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-156">UE-V includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="147e7-157">Эти файлы MSI по-прежнему доступны, но пользовательский интерфейс минимизирован и отображается только на английском языке.</span><span class="sxs-lookup"><span data-stu-id="147e7-157">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="147e7-158">Несмотря на то, что файл находится на английском языке, во время установки программа установки устанавливает все поддерживаемые языки.</span><span class="sxs-lookup"><span data-stu-id="147e7-158">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="147e7-159">ВРЕМЕННОе решение: нет</span><span class="sxs-lookup"><span data-stu-id="147e7-159">WORKAROUND: None</span></span>

### <span data-ttu-id="147e7-160">Favicons, связанные с браузером Internet Explorer 9, не перемещаются</span><span class="sxs-lookup"><span data-stu-id="147e7-160">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="147e7-161">Favicons, связанные с браузером Internet Explorer 9, не перемещаются с помощью виртуализации взаимодействия с пользователем и не отображаются при первом появлении этого списка на новом компьютере.</span><span class="sxs-lookup"><span data-stu-id="147e7-161">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="147e7-162">ВРЕМЕННОе решение: при использовании закладки и кэшировании в браузере Internet Explorer 9 появится Favicons с соответствующими избранными.</span><span class="sxs-lookup"><span data-stu-id="147e7-162">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="147e7-163">Пути к параметрам файла хранятся в реестре</span><span class="sxs-lookup"><span data-stu-id="147e7-163">File settings paths are stored in registry</span></span>

<span data-ttu-id="147e7-164">Некоторые параметры приложения хранят пути файлов конфигурации и параметров в виде значений в реестре.</span><span class="sxs-lookup"><span data-stu-id="147e7-164">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="147e7-165">Файлы, на которые указывают ссылки в реестре, должны быть синхронизированы при перемещении параметров между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="147e7-165">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="147e7-166">ВРЕМЕННОе решение: используйте перенаправление папок или другие технологии, чтобы убедиться в том, что файлы, на которые указывают ссылки, находятся в том же расположении на всех компьютерах, где параметры перемещаются.</span><span class="sxs-lookup"><span data-stu-id="147e7-166">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="147e7-167">Путь к хранилищу с длинными параметрами может вызвать ошибку</span><span class="sxs-lookup"><span data-stu-id="147e7-167">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="147e7-168">Храните пути к хранилищу параметров как можно короче.</span><span class="sxs-lookup"><span data-stu-id="147e7-168">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="147e7-169">Длинные пути могут не допускать разрешения и синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="147e7-169">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="147e7-170">UE-V использует путь к хранилищу параметров как часть расчетного пути для хранения параметров.</span><span class="sxs-lookup"><span data-stu-id="147e7-170">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="147e7-171">Этот путь вычисляется следующим образом: параметры путь к хранилищу и "settingspackages" + Dir (ИД шаблона) + имя пакета (идентификатор шаблона) +. pkgx.</span><span class="sxs-lookup"><span data-stu-id="147e7-171">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="147e7-172">Если размер вычисляемого пути превышает 260 символов, в журнале событий UE-V память пакета завершается сбоем и генерируется следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="147e7-172">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="147e7-173">Для проверки событий журнала в журнале откройте средство просмотра событий и перейдите в раздел Журналы приложений и служб/Microsoft/пользовательский интерфейс, виртуализация и ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="147e7-173">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="147e7-174">ВРЕМЕННОе решение: нет.</span><span class="sxs-lookup"><span data-stu-id="147e7-174">WORKAROUND: None.</span></span>

### <span data-ttu-id="147e7-175">Некоторые параметры операционной системы перемещаются только в том случае, если они есть в версиях операционной системы</span><span class="sxs-lookup"><span data-stu-id="147e7-175">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="147e7-176">Параметры операционной системы для символов экранного диктора и денежных единиц, относящихся к национальной настройке (например, язык и региональные стандарты), будут перемещаться только в версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="147e7-176">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="147e7-177">Например, символы денежных единиц не будут перемещаться между Windows 7 и Windows 8.</span><span class="sxs-lookup"><span data-stu-id="147e7-177">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="147e7-178">ВРЕМЕННОе решение: нет</span><span class="sxs-lookup"><span data-stu-id="147e7-178">WORKAROUND: None</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="147e7-179">Агент UE-V 1 вызывает ошибки при запуске шаблонов UE-V 2</span><span class="sxs-lookup"><span data-stu-id="147e7-179">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="147e7-180">Если шаблон расположений параметров UE-V 2 распространяется на компьютер, установленный с агентом UE-V 1, некоторые параметры не синхронизируются между компьютерами, и агент сообщает об ошибках в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="147e7-180">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="147e7-181">РЕШЕНИЕ: при переходе с UE-V 1 на UE-V 2 и, возможно, у вас есть компьютеры, на которых работает Предыдущая версия агента, создайте отдельный каталог UE-V 2. x для поддержки агента и шаблонов UE-v 2. x.</span><span class="sxs-lookup"><span data-stu-id="147e7-181">WORKAROUND: When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.x catalog to support the UE-V 2.x Agent and templates.</span></span>

### <span data-ttu-id="147e7-182">Задержка выхода UE-V</span><span class="sxs-lookup"><span data-stu-id="147e7-182">UE-V logoff delay</span></span>

<span data-ttu-id="147e7-183">Иногда при выходе из системы UE-V занимает много времени для синхронизации параметров.</span><span class="sxs-lookup"><span data-stu-id="147e7-183">Occasionally on logoff, UE-V takes a long time to sync settings.</span></span> <span data-ttu-id="147e7-184">Обычно это происходит из-за того, что в сети используется большое количество задержек или неправильное использование файловой системы distrubuted (DFS).</span><span class="sxs-lookup"><span data-stu-id="147e7-184">Typically, this is due to a high latency network or incorrect use of Distrubuted File System (DFS).</span></span>
<span data-ttu-id="147e7-185">Для получения дополнительных сведений о службе поддержки распределенной файловой системы (DFS) обратитесь в [службу поддержки Майкрософт вокруг реплицируемых данных профиля пользователя](https://support.microsoft.com/kb/2533009) .</span><span class="sxs-lookup"><span data-stu-id="147e7-185">For DFS support, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://support.microsoft.com/kb/2533009) for further details.</span></span>

<span data-ttu-id="147e7-186">ВРЕМЕННОе решение: начиная с HF03, в следующем разделе реестра представлен следующий раздел, в котором представлен механизм, с помощью которого можно задать максимальную задержку выхода \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span><span class="sxs-lookup"><span data-stu-id="147e7-186">WORKAROUND: Starting with HF03, a new registry key has been introduced The following registry key provides a mechanism by which the maximum logoff delay can be specified \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span></span>

<span data-ttu-id="147e7-187">Дополнительные сведения приведены в разделе [параметры реестра для UE-V](https://support.microsoft.com/kb/2770042) .</span><span class="sxs-lookup"><span data-stu-id="147e7-187">See [UE-V registry settings](https://support.microsoft.com/kb/2770042) for further details</span></span>

## <span data-ttu-id="147e7-188">Исправления и статьи базы знаний для UE-V 2,1 SP1</span><span class="sxs-lookup"><span data-stu-id="147e7-188">Hotfixes and Knowledge Base articles for UE-V 2.1 SP1</span></span>


<span data-ttu-id="147e7-189">В этом разделе содержатся исправления и статьи базы знаний для UE-V 2,1 SP1.</span><span class="sxs-lookup"><span data-stu-id="147e7-189">This section contains hotfixes and KB articles for UE-V 2.1 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="147e7-190">Статья базы знаний</span><span class="sxs-lookup"><span data-stu-id="147e7-190">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="147e7-191">Title</span><span class="sxs-lookup"><span data-stu-id="147e7-191">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="147e7-192">Ссылка</span><span class="sxs-lookup"><span data-stu-id="147e7-192">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-193">3018608</span><span class="sxs-lookup"><span data-stu-id="147e7-193">3018608</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-194">UE-V 2,1-TemplateConsole.exe завершает работу со сбоем, если отсутствуют классы WMI UE-V.</span><span class="sxs-lookup"><span data-stu-id="147e7-194">UE-V 2.1 - TemplateConsole.exe crashes when UE-V WMI classes are missing</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)"><span data-ttu-id="147e7-195">support.microsoft.com/kb/3018608/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-195">support.microsoft.com/kb/3018608/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-196">2903501</span><span class="sxs-lookup"><span data-stu-id="147e7-196">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-197">UE-V: совместимость с интерфейсом пользователя (UE-V) Compatibility с профилями пользователей</span><span class="sxs-lookup"><span data-stu-id="147e7-197">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="147e7-198">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-198">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-199">2770042</span><span class="sxs-lookup"><span data-stu-id="147e7-199">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-200">Параметры реестра UE-V</span><span class="sxs-lookup"><span data-stu-id="147e7-200">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="147e7-201">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-201">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-202">2847017</span><span class="sxs-lookup"><span data-stu-id="147e7-202">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-203">Параметры UE-V реплицированы с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="147e7-203">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="147e7-204">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-204">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-205">2769631</span><span class="sxs-lookup"><span data-stu-id="147e7-205">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-206">Восстановление поврежденной установки UE-V</span><span class="sxs-lookup"><span data-stu-id="147e7-206">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="147e7-207">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-207">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-208">2850989</span><span class="sxs-lookup"><span data-stu-id="147e7-208">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-209">Миграция профилей MAPI с помощью Microsoft UE-V не поддерживается</span><span class="sxs-lookup"><span data-stu-id="147e7-209">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="147e7-210">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-210">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-211">2769586</span><span class="sxs-lookup"><span data-stu-id="147e7-211">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-212">UE-V перемещение пустых папок и разделов реестра</span><span class="sxs-lookup"><span data-stu-id="147e7-212">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="147e7-213">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-213">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-214">2782997</span><span class="sxs-lookup"><span data-stu-id="147e7-214">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-215">Как включить ведение журнала отладки в Microsoft User Experience Virtualization (UE-V)</span><span class="sxs-lookup"><span data-stu-id="147e7-215">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="147e7-216">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-216">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-217">2769570</span><span class="sxs-lookup"><span data-stu-id="147e7-217">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-218">UE-V не обновляет тему в сеансах RDS и VDI</span><span class="sxs-lookup"><span data-stu-id="147e7-218">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="147e7-219">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-219">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-220">2850582</span><span class="sxs-lookup"><span data-stu-id="147e7-220">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-221">Использование виртуализации взаимодействия с пользователем Microsoft в приложениях App-V</span><span class="sxs-lookup"><span data-stu-id="147e7-221">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="147e7-222">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-222">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="147e7-223">3041879</span><span class="sxs-lookup"><span data-stu-id="147e7-223">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-224">Текущие версии файлов для Microsoft User Experience Virtualization</span><span class="sxs-lookup"><span data-stu-id="147e7-224">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="147e7-225">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-225">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="147e7-226">2843592</span><span class="sxs-lookup"><span data-stu-id="147e7-226">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="147e7-227">Сведения о виртуализации взаимодействия с пользователем и о высокой доступности</span><span class="sxs-lookup"><span data-stu-id="147e7-227">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="147e7-228">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="147e7-228">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 






 

 




