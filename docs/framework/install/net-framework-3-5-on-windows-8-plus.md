---
title: "Windows 8, Windows 8.1 및 Windows 10에 .NET Framework 3.5 설치"
ms.date: 05/26/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework 3.5, installing on Windows 8
- Windows 8, installing .NET Framework 3.5
ms.assetid: 3eab3eb4-4573-42ac-98f8-36fb2c22c7d5
caps.latest.revision: 69
author: mairaw
ms.author: mairaw
ms.translationtype: HT
ms.sourcegitcommit: 20b0c1b36f705deb2f46ef4ab23653f829faf7ca
ms.openlocfilehash: 8a0395e28c01363eed27f327ea623feb4832c844
ms.contentlocale: ko-kr
ms.lasthandoff: 08/08/2017

---

# <a name="install-the-net-framework-35-on-windows-8-windows-81-and-windows-10"></a><span data-ttu-id="e6cf4-102">Windows 8, Windows 8.1 및 Windows 10에 .NET Framework 3.5 설치</span><span class="sxs-lookup"><span data-stu-id="e6cf4-102">Install the .NET Framework 3.5 on Windows 8, Windows 8.1, and Windows 10</span></span>

<span data-ttu-id="e6cf4-103">.NET Framework는 Windows에서 실행되는 대부분의 앱에서 필수적인 요소이며, 해당 앱이 실행되는 데 필요한 공통적인 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-103">The .NET Framework is an integral part of many apps running on Windows and provides common functionality for those apps to run.</span></span> <span data-ttu-id="e6cf4-104">개발자의 경우 .NET Framework는 앱 빌드를 위한 일관된 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-104">For developers, the .NET Framework provides a consistent programming model for building apps.</span></span> <span data-ttu-id="e6cf4-105">Windows 운영 체제를 사용하는 경우 .NET Framework가 이미 컴퓨터에 설치되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-105">If you're using the Windows operating system, the .NET Framework may already be installed on your computer.</span></span> <span data-ttu-id="e6cf4-106">구체적으로 [!INCLUDE[win8](../../../includes/win8-md.md)]에는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 포함되어 있고, [!INCLUDE[win81](../../../includes/win81-md.md)]에는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]이 포함되어 있으며, Windows 10에는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-106">Specifically, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is included with [!INCLUDE[win8](../../../includes/win8-md.md)], the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] is included with [!INCLUDE[win81](../../../includes/win81-md.md)], and the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] is included with Windows 10.</span></span>  
  
<span data-ttu-id="e6cf4-107">그러나 .NET Framework 3.5는 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] 또는 Windows 10과 함께 자동으로 설치되지 않으므로 이 버전에 종속된 앱을 실행하려면 별도로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-107">The .NET Framework 3.5, however, is not automatically installed with [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], or Windows 10, and must be separately enabled to run apps that depend on it.</span></span> <span data-ttu-id="e6cf4-108">이 작업은 세 가지 중 하나의 방법으로 호출되는 Windows 업데이트를 통해 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-108">This must happen through Windows Update, which is invoked in one of three ways.</span></span> <span data-ttu-id="e6cf4-109">이러한 모든 방법을 사용하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-109">All of these require an Internet connection:</span></span>  
  
- [<span data-ttu-id="e6cf4-110">요청 시 .NET Framework 3.5 설치</span><span class="sxs-lookup"><span data-stu-id="e6cf4-110">Install the .NET Framework 3.5 on Demand</span></span>](#OnDemand)  
  
- [<span data-ttu-id="e6cf4-111">제어판에서 .NET Framework 3.5를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e6cf4-111">Enable the .NET Framework 3.5 in Control Panel</span></span>](#ControlPanel)  
  
- <span data-ttu-id="e6cf4-112">[.NET Framework 3.5 설치 관리자 다운로드](http://www.microsoft.com/en-us/download/details.aspx?id=21) (참고: Windows 업데이트를 호출하는 설치 관리자로 .NET Framework를 직접 다운로드하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="e6cf4-112">[Download the .NET Framework 3.5 installer](http://www.microsoft.com/en-us/download/details.aspx?id=21) (Note: This does not download the .NET Framework directly; it is an installer that invokes Windows Update.)</span></span>  
  
<span data-ttu-id="e6cf4-113">설치 중 0x800f0906, 0x800f0907 또는 0x800f081f 오류가 발생할 수 있습니다. 이 경우 [.NET Framework 3.5 설치 오류: 0x800f0906, 0x800f0907 또는 0x800f081f](https://support.microsoft.com/en-us/kb/2734782)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-113">During installation, you may encounter error 0x800f0906, 0x800f0907, or 0x800f081f, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/en-us/kb/2734782).</span></span> <span data-ttu-id="e6cf4-114">[보안 업데이트 3005628](https://support.microsoft.com/kb/3005628)을 설치하여 이러한 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-114">Note that these are possibly resolved by installing [security update 3005628](https://support.microsoft.com/kb/3005628).</span></span>  
  
<span data-ttu-id="e6cf4-115">위의 방법이 실패하거나 인터넷에 연결되지 않은 경우 Windows 설치 미디어를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-115">If any of the above methods fail or if you do not have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="e6cf4-116">자세한 내용은 [.NET Framework 3.5 설치 오류 문서](https://support.microsoft.com/en-us/kb/2734782)에서 오류 0x800f0906에 대한 방법 3을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-116">For details, see Method 3 for error 0x800f0906 in the [.NET Framework 3.5 installation error article](https://support.microsoft.com/en-us/kb/2734782).</span></span> <span data-ttu-id="e6cf4-117">설치 미디어가 없는 경우 [Windows 8.1용 설치 미디어 만들기](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-117">If you don't have installation media, see [Create Installation media for Windows 8.1](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0).</span></span>  
  
<span data-ttu-id="e6cf4-118">**유의 사항:**</span><span class="sxs-lookup"><span data-stu-id="e6cf4-118">**Important notes:**</span></span>
  
- <span data-ttu-id="e6cf4-119">일반적으로 컴퓨터에 설치되어 있는 .NET Framework 버전을 제거하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-119">In general, don't uninstall any versions of the .NET Framework from your computer.</span></span> <span data-ttu-id="e6cf4-120">앱마다 다른 버전의 프레임워크를 사용하며, 단일 컴퓨터에서 여러 버전의 .NET Framework를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-120">Different apps depend on different versions of the framework, and multiple versions of the .NET Framework can coexist on a single computer at the same time.</span></span>  
  
- <span data-ttu-id="e6cf4-121">.NET Framework 3.5는 버전 2.0 및 3.0용으로 빌드된 앱에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-121">The .NET Framework 3.5 is also used by apps built for versions 2.0 and 3.0.</span></span>  
  
- <span data-ttu-id="e6cf4-122">.NET Framework 3.5를 설치하기 전에 에 Windows 언어 팩을 설치하면 .NET Framework 3.5 설치에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-122">Installing a Windows language pack before installing the .NET Framework 3.5 may cause the .NET Framework 3.5 installation to fail.</span></span> <span data-ttu-id="e6cf4-123">.NET Framework 3.5를 설치한 후에 Windows 언어 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-123">Install the .NET Framework 3.5 before installing any Windows language packs.</span></span>  
  
- <span data-ttu-id="e6cf4-124">Windows CardSpace는 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 .NET Framework 3.5와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-124">Windows CardSpace is not available with the .NET Framework 3.5 on [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span>  
  
- <span data-ttu-id="e6cf4-125">.NET Framework 3.5를 설치하는 방법이 복잡하므로 Windows 업데이트와 별도로 실행할 수 있는 개별 독립 실행형 설치 관리자를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-125">Because of complications around how the .NET Framework 3.5 must be installed, it's unfortunately not possible to provide a separate, standalone installer that can run independently of Windows Update.</span></span> <span data-ttu-id="e6cf4-126">다른 모든 방법이 실패하는 경우에는 앞에서 설명한 대로 설치 미디어를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-126">If all other methods fail, you must resort to installation media as described earlier.</span></span>  
  
<a name="OnDemand"></a>   
## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="e6cf4-127">요청 시 .NET Framework 3.5 설치</span><span class="sxs-lookup"><span data-stu-id="e6cf4-127">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="e6cf4-128">앱에 .NET Framework 3.5가 필요하지만 컴퓨터에서 사용할 수 있는 해당 버전이 검색되지 않는 경우, 설치하는 동안이나 앱을 처음 실행할 때 다음과 같은 메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-128">If an app requires the .NET Framework 3.5 but doesn't find that version enabled on your computer, it displays the following message box, either during installation or when you run the app for the first time.</span></span> <span data-ttu-id="e6cf4-129">메시지 상자에서 **이 기능 설치** 를 선택하여 .NET Framework 3.5를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-129">In the message box, choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="e6cf4-130">이 옵션을 사용하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-130">This option requires an Internet connection.</span></span>  
  
<span data-ttu-id="e6cf4-131">![Windows 8에 3.5 설치용 대화 상자](../../../docs/framework/deployment/media/installdialog.png "installdialog")</span><span class="sxs-lookup"><span data-stu-id="e6cf4-131">![Dialog box for 3.5 install on Windows 8](../../../docs/framework/deployment/media/installdialog.png "installdialog")</span></span>  
  
<a name="ControlPanel"></a>   
## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="e6cf4-132">제어판에서 .NET Framework 3.5를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e6cf4-132">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="e6cf4-133">제어판을 통해 .NET Framework 3.5를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-133">You can enable the .NET Framework 3.5 through Control Panel.</span></span> <span data-ttu-id="e6cf4-134">이 옵션을 사용하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-134">This option requires an Internet connection.</span></span>  
  
1. <span data-ttu-id="e6cf4-135">키보드에서 Windows 키 ![Windows 로고](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-135">Press the Windows key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard.</span></span> <span data-ttu-id="e6cf4-136">“Windows 기능”을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-136">Type "Windows Features" and press Enter.</span></span> <span data-ttu-id="e6cf4-137">**Windows 기능 사용/사용 안 함 대화 상자** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-137">This brings up the **Turn Windows features on or off** dialog box.</span></span> <span data-ttu-id="e6cf4-138">또는 제어판을 열고 **프로그램** 항목을 클릭한 다음, **프로그램 및 기능**에서 **Windows 기능 사용/사용 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-138">Alternately, open Control Panel, click on the **Programs** items, and then select **Turn Windows features on or off** under **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="e6cf4-139">**.NET Framework 3.5(.NET 2.0 및 3.0 포함)** 확인란을 선택하고, **확인**을 선택하고, 메시지가 표시되면 컴퓨터를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-139">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>  
  
<span data-ttu-id="e6cf4-140">WCF 스크립트 및 처리기 매핑 기능이 필요한 개발자가 아니라면 **WCF(Windows Communication Foundation ) HTTP Activation**을 위한 자식 항목을 선택할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cf4-140">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP activation** unless you're a developer who requires WCF script and handler mapping functionality.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6cf4-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6cf4-141">See also</span></span>

[<span data-ttu-id="e6cf4-142">설치 가이드</span><span class="sxs-lookup"><span data-stu-id="e6cf4-142">Installation Guide</span></span>](../../../docs/framework/get-started/index.md)

