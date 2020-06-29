---
title: Настройка App-V для обеспечения безопасного администрирования
description: Настройка App-V для обеспечения безопасного администрирования
author: dansimp
ms.assetid: 4543fa81-c8cc-4b10-83b7-060778eb1349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de70c1df734bbf1168fd7dacf9410d3451a8a3c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821902"
---
# <span data-ttu-id="7ecea-103">Настройка App-V для обеспечения безопасного администрирования</span><span class="sxs-lookup"><span data-stu-id="7ecea-103">Configuring App-V for Secure Administration</span></span>


<span data-ttu-id="7ecea-104">В среде, в которой важна безопасность административных операций, App-V обеспечивает безопасную связь между службой управления веб-приложением App/v и консолью управления App-V.</span><span class="sxs-lookup"><span data-stu-id="7ecea-104">In an environment where securing administrative operations is important, App-V allows for secure communication between the App-V Web Management Service and the App-V Management Console.</span></span> <span data-ttu-id="7ecea-105">Поскольку служба управления — это веб-приложение, необходимо обеспечить безопасность серверного приложения управления App-V на веб-сервере, на котором размещается служба управления.</span><span class="sxs-lookup"><span data-stu-id="7ecea-105">Because the Management Service is a Web-based application, it requires securing the App-V Management Server application on the Web server that hosts the Management Service.</span></span> <span data-ttu-id="7ecea-106">Как показано на приведенном ниже рисунке, этот процесс включает использование HTTPS для связи и настройку сервера IIS для разрешения только интегрированной проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7ecea-106">As shown in the following illustration, this process includes using HTTPS for communication and configuring the IIS server to allow only Windows Integrated Authentication.</span></span>

![Настройка сети веб-службы App-v](images/appvmgmtwebservice.gif)

<span data-ttu-id="7ecea-108">Служба веб-управления App-V установлена в службах IIS в виде Интернет-приложения.</span><span class="sxs-lookup"><span data-stu-id="7ecea-108">The App-V Web Management Service is installed as a Web-based application on IIS.</span></span> <span data-ttu-id="7ecea-109">Чтобы служба управления Интернетом поддерживала безопасные соединения (SSL) между консолью управления App-V и службой управления веб-сайтами, вам потребуется настроить сервер IIS, на котором установлена служба веб-управления, и настроить консоль управления App-V.</span><span class="sxs-lookup"><span data-stu-id="7ecea-109">For the Web Management Service to support secure (SSL) connections between the App-V Management Console and the Web Management Service, you will need to configure the IIS server where the Web Management Service is installed and configure the App-V Management Console.</span></span>

## <span data-ttu-id="7ecea-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7ecea-110">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[<span data-ttu-id="7ecea-111">Настройка сертификатов для обеспечения поддержки службы веб-управления App-V</span><span class="sxs-lookup"><span data-stu-id="7ecea-111">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)  
<span data-ttu-id="7ecea-112">Справочные сведения о настройке сертификатов для поддержки подключений на основе SSL для обеспечения безопасной связи с веб-службой управления App-V.</span><span class="sxs-lookup"><span data-stu-id="7ecea-112">Provides helpful information about configuring certificates to support SSL-based connections, to help secure communication for the App-V Web Management Service.</span></span>

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[<span data-ttu-id="7ecea-113">Установка и настройка консоли управления App-V для организации более безопасной среды</span><span class="sxs-lookup"><span data-stu-id="7ecea-113">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
<span data-ttu-id="7ecea-114">В этой статье приведены пошаговые инструкции по подключению к службе веб-управления App-V с помощью безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="7ecea-114">Provides a step-by-step procedure for connecting to an App-V Web Management Service by using a secure connection.</span></span>

 

 





