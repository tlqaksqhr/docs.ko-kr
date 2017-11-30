---
title: ".NET Framework 및 번외 릴리스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1785c222238a58893edf71352839b40ea8db29f7
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="the-net-framework-and-out-of-band-releases"></a><span data-ttu-id="a9d5e-102">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="a9d5e-102">The .NET Framework and Out-of-Band Releases</span></span>
<span data-ttu-id="a9d5e-103">.NET Framework는 기존의 데스크톱 및 웹 응용 프로그램뿐만 아니라 Windows Phone 및 Windows 스토어 앱과 같은 서로 다른 플랫폼을 수용하고 코드 재사용을 최대화하는 방향으로 발전하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-103">The .NET Framework is evolving to accommodate different platforms such as Windows Phone and Windows Store apps as well as traditional desktop and web apps, and to maximize code reuse.</span></span> <span data-ttu-id="a9d5e-104">정기적인 .NET Framework 릴리스 이외에 새로운 기능인 OOB(Out Of Band)도 릴리스하여 플랫폼 간 개발을 향상시키거나 새 기능을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-104">In addition to our regular .NET Framework releases, we release new features out of band (OOB) to improve cross-platform development or to introduce new functionality.</span></span> <span data-ttu-id="a9d5e-105">이 항목에서는 .NET Framework 및 해당 OOB 릴리스의 향후 방향에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-105">This topic discusses the future direction of the .NET Framework and its OOB releases.</span></span>  
  
## <a name="advantages-of-oob-releases"></a><span data-ttu-id="a9d5e-106">OOB 릴리스의 장점</span><span class="sxs-lookup"><span data-stu-id="a9d5e-106">Advantages of OOB releases</span></span>  
 <span data-ttu-id="a9d5e-107">Microsoft는 새 구성 요소 또는 구성 요소 Out of Band에 대한 업데이트를 제공함으로써 .NET Framework를 보다 자주 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-107">Shipping new components or updates to components out of band enables Microsoft to provide more frequent updates to the .NET Framework.</span></span> <span data-ttu-id="a9d5e-108">또한 보다 신속하게 고객 의견을 수집하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-108">In addition, we can gather and respond to customer feedback more quickly.</span></span>  
  
 <span data-ttu-id="a9d5e-109">응용 프로그램에서 OOB 기능을 사용하면 OOB 어셈블리가 응용 프로그램 패키지와 함께 배포되므로 사용자는 응용 프로그램을 실행하기 위해 최신 버전의 .NET Framework를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-109">When you use an OOB feature in your app, your users do not have to install the latest version of the .NET Framework to run your app, because the OOB assemblies deploy with your app package.</span></span>  
  
## <a name="how-oob-packages-are-distributed"></a><span data-ttu-id="a9d5e-110">OOB 패키지 분산 방식</span><span class="sxs-lookup"><span data-stu-id="a9d5e-110">How OOB packages are distributed</span></span>  
<span data-ttu-id="a9d5e-111">핵심 공용 언어 런타임 (CLR) 구성 요소에 대 한 OOB 릴리스를 통해 제공 되는 [NuGet](https://www.nuget.org/)은.NET에 대 한 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-111">OOB releases for core common language runtime (CLR) components are delivered through the [NuGet](https://www.nuget.org/), which is a package manager for .NET.</span></span> <span data-ttu-id="a9d5e-112">NuGet을 사용하면 Visual Studio의 솔루션 탐색기에서 간단하게 라이브러리를 찾아보고 해당 라이브러리를 .NET Framework 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-112">NuGet enables you to browse and add libraries to your .NET Framework projects easily from the Solution Explorer in Visual Studio.</span></span> <span data-ttu-id="a9d5e-113">NuGet은 Visual Studio 2012부터 Visual Studio의 모든 버전에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-113">NuGet is included with all editions of Visual Studio starting with Visual Studio 2012.</span></span> <span data-ttu-id="a9d5e-114">NuGet이 설치되어 있는지 확인하려면 Visual Studio **도구** 메뉴에서 **라이브러리 패키지 관리자**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-114">To see if NuGet is installed, look for **Library Package Manager** on the Visual Studio **Tools** menu.</span></span> <span data-ttu-id="a9d5e-115">NuGet이 설치되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="a9d5e-115">If it’s not installed:</span></span>  
  
1.  <span data-ttu-id="a9d5e-116">Visual Studio 메뉴 모음에서 **도구**, **확장명 및 업데이트**를 선택합니다(Visual Studio 2010에서는 **확장명 관리자** 선택.)</span><span class="sxs-lookup"><span data-stu-id="a9d5e-116">On the Visual Studio menu bar, choose **Tools**, **Extensions and Updates** (in Visual Studio 2010, choose **Extension Manager**).</span></span>  
  
     <span data-ttu-id="a9d5e-117">**확장명 및 업데이트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-117">The **Extensions and Updates** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="a9d5e-118">**온라인**, **NuGet 패키지 관리자**를 선택한 다음 **다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-118">Choose **Online**, **NuGet Package Manager**, and then choose **Download**.</span></span>  
  
3.  <span data-ttu-id="a9d5e-119">다운로드가 완료된 후 Visual Studio를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-119">After the download completes, restart Visual Studio.</span></span>  
  
 <span data-ttu-id="a9d5e-120">자세한 설치 지침은 NuGet 문서 웹 사이트에서 [NuGet 설치](http://docs.nuget.org/docs/start-here/installing-nuget)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-120">For detailed installation instructions, see [Installing NuGet](http://docs.nuget.org/docs/start-here/installing-nuget) on the NuGet Docs website.</span></span> <span data-ttu-id="a9d5e-121">NuGet에 대한 자세한 내용은 [NuGet 설명서](http://docs.nuget.org/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-121">For more information about NuGet, see the [NuGet documentation](http://docs.nuget.org/).</span></span>  
  
## <a name="using-a-nuget-oob-package"></a><span data-ttu-id="a9d5e-122">NuGet OOB 패키지 사용</span><span class="sxs-lookup"><span data-stu-id="a9d5e-122">Using a NuGet OOB package</span></span>  
 <span data-ttu-id="a9d5e-123">NuGet을 설치한 후 Visual Studio의 솔루션 탐색기를 사용하여 NuGet 패키지에 대한 참조를 찾아보고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-123">After you install NuGet, you can browse and add references to NuGet packages by using Solution Explorer in Visual Studio:</span></span>  
  
1.  <span data-ttu-id="a9d5e-124">Visual Studio에서 프로젝트의 바로 가기 메뉴를 열고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-124">Open the shortcut menu for your project in Visual Studio, and then choose **Manage NuGet Packages**.</span></span> <span data-ttu-id="a9d5e-125">(이 옵션은 **프로젝트** 메뉴에서도 사용 가능합니다.)</span><span class="sxs-lookup"><span data-stu-id="a9d5e-125">(This option is also available from the **Project** menu.)</span></span>  
  
2.  <span data-ttu-id="a9d5e-126">왼쪽 창에서 **온라인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-126">In the left pane, choose **Online**.</span></span>  
  
3.  <span data-ttu-id="a9d5e-127">시험판 패키지를 사용할 경우 중간 창의 드롭다운 목록 상자에서 **안정된 상태만** 대신 **시험판 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-127">If you want to use prerelease packages, in the drop-down list box in the middle pane, choose **Include Prerelease** instead of **Stable Only**.</span></span>  
  
4.  <span data-ttu-id="a9d5e-128">오른쪽 창에서 **검색** 상자를 사용하여 사용하려는 패키지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-128">In the right pane, use the **Search** box to locate the package you would like to use.</span></span> <span data-ttu-id="a9d5e-129">일부 Microsoft 패키지는 Microsoft .NET Framework 로고로 식별되며 모두 Microsoft를 게시자로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-129">Some Microsoft packages are identified by the Microsoft .NET Framework logo, and all identify Microsoft as the publisher.</span></span>  
  
 <span data-ttu-id="a9d5e-130">![NuGet 패키지 관리자](../../../docs/framework/get-started/media/clrnugetdialog.png "clrNugetDialog")</span><span class="sxs-lookup"><span data-stu-id="a9d5e-130">![NuGet Package Manager](../../../docs/framework/get-started/media/clrnugetdialog.png "clrNugetDialog")</span></span>  
  
 <span data-ttu-id="a9d5e-131">앞에서 언급했듯이 OOB 패키지를 사용하는 응용 프로그램을 배포하면 응용 프로그램 패키지와 함께 OOB 어셈블리가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-131">As mentioned previously, when you deploy an app that uses an OOB package, the OOB assemblies will ship with your app package.</span></span>  
  
## <a name="types-of-oob-releases"></a><span data-ttu-id="a9d5e-132">OOB 릴리스 형식</span><span class="sxs-lookup"><span data-stu-id="a9d5e-132">Types of OOB releases</span></span>  
 <span data-ttu-id="a9d5e-133">일반적으로 OOB 패키지에는 하나 이상의 시험판 버전 및 안정적인 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-133">Typically, an OOB package has one or more prerelease versions and a stable version.</span></span> <span data-ttu-id="a9d5e-134">시험판과 함께 제공되는 라이선스는 일반적으로 재배포할 수 없지만 패키지를 사용해 보고 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-134">The license that accompanies a prerelease doesn't typically allow redistribution, but enables you to try out a package and provide feedback.</span></span> <span data-ttu-id="a9d5e-135">피드백이 패키지의 모든 업데이트에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-135">Feedback is incorporated in any updates made to the package.</span></span> <span data-ttu-id="a9d5e-136">최종 릴리스는 NuGet과 함께 안정적인 패키지로 분산되며 응용 프로그램과 함께 NuGet 패키지를 재배포할 수 있는 라이선스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-136">A final release is distributed as a stable package with NuGet and includes a license that lets you redistribute the NuGet package with your app.</span></span> <span data-ttu-id="a9d5e-137">안정적인 패키지가 Microsoft에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-137">Stable packages are supported by Microsoft.</span></span> <span data-ttu-id="a9d5e-138">Microsoft는 모든 패키지에 대한 블로그 게시물 및 포럼 답변과 같은 다른 유형의 문서는 물론 IntelliSense 지원도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-138">Microsoft provides IntelliSense support as well as other types of documentation such as blog posts and forum answers for all packages.</span></span> <span data-ttu-id="a9d5e-139">또한 소스 코드는 전부는 아니지만 일부 패키지에서 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-139">In addition, source code may be available with some, but not all, packages.</span></span> <span data-ttu-id="a9d5e-140">[.NET Framework 블로그](http://blogs.msdn.com/b/dotnet/)를 구독하면 새 패키지 및 업데이트된 패키지에 대한 알림을 받아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-140">For announcements regarding new and updated packages, you can subscribe to [the .NET Framework Blog](http://blogs.msdn.com/b/dotnet/).</span></span>  
  
 <span data-ttu-id="a9d5e-141">시험판과 안정적인 패키지를 둘 다 찾아보려면 NuGet 패키지 관리자에서 **시험판 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-141">To find both prerelease and stable packages, choose **Include Prerelease** in the NuGet Package Manager.</span></span>  
  
 <span data-ttu-id="a9d5e-142">안정적인 패키지 릴리스에 대한 알림을 받아보려면 [.NET Framework 피드](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/)를 구독하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d5e-142">If you want to be notified of stable package releases, subscribe to the [the .NET Framework feed](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d5e-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9d5e-143">See Also</span></span>  
 [<span data-ttu-id="a9d5e-144">시작</span><span class="sxs-lookup"><span data-stu-id="a9d5e-144">Getting Started</span></span>](../../../docs/framework/get-started/index.md)
