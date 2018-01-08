---
title: "Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치"
description: "Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5를 설치하는 방법을 알아봅니다."
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload: dotnet
ms.openlocfilehash: ca56bfb37cee60ab014dada7b5d72b74b375dd7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="999f8-103">Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치</span><span class="sxs-lookup"><span data-stu-id="999f8-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="999f8-104">Windows 10, Windows 8.1 및 Windows 8에서 앱을 실행하려면 .NET Framework 3.5가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="999f8-105">이러한 지침은 이전 Windows 버전에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="999f8-106">요청 시 .NET Framework 3.5 설치</span><span class="sxs-lookup"><span data-stu-id="999f8-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="999f8-107">.NET Framework 3.5가 필요한 앱을 실행하려고 하면 다음 구성 대화 상자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="999f8-108">**이 기능 설치**를 선택하여 .NET Framework 3.5를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="999f8-109">이 옵션을 사용하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-109">This option requires an Internet connection.</span></span>

![.NET Framework 설치 대화 상자](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="999f8-111">제어판에서 .NET Framework 3.5를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="999f8-111">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="999f8-112">Windows 제어판을 통해 .NET Framework 3.5를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-112">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="999f8-113">이 옵션을 사용하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-113">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="999f8-114">키보드에서 Windows 키 ![Windows 로고](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)를 누르고, “Windows 기능”을 입력한 후 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-114">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="999f8-115">**Windows 기능 사용/사용 안 함** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-115">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="999f8-116">**.NET Framework 3.5(.NET 2.0 및 3.0 포함)** 확인란을 선택하고, **확인**을 선택하고, 메시지가 표시되면 컴퓨터를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-116">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![제어판으로 .NET 설치](./media/dotnet-control-panel.png)

   <span data-ttu-id="999f8-118">이 기능이 필요한 개발자 또는 서버 관리자가 아니라면 **WCF(Windows Communication Foundation) HTTP 활성화** 및 **WCF(Windows Communication Foundation) 비 HTTP 활성화**를 위한 자식 항목을 선택할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-118">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="999f8-119">.NET Framework 3.5 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="999f8-119">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="999f8-120">설치 중 0x800f0906, 0x800f0907, 0x800f081f 또는 0x800F0922 오류가 발생할 수 있습니다. 이 경우 [.NET Framework 3.5 설치 오류: 0x800f0906, 0x800f0907 또는 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)를 참조하여 이러한 문제 해결 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="999f8-120">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="999f8-121">이전 문서에서 설명한 어떤 방법으로도 문제가 해결되지 않거나 인터넷에 연결되지 않은 경우 Windows 설치 미디어를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="999f8-121">If any of the methods discussed in the previous article fail or if you don't have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="999f8-122">자세한 내용은 [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](https://technet.microsoft.com/library/Dn482069.aspx)(DISM(배포 이미지 서비스 및 관리)을 사용하여 .NET Framework 3.5 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="999f8-122">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](https://technet.microsoft.com/library/Dn482069.aspx).</span></span> <span data-ttu-id="999f8-123">설치 미디어가 없는 경우 [Windows용 설치 미디어 만들기](https://support.microsoft.com/help/15088/windows-create-installation-media)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="999f8-123">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>