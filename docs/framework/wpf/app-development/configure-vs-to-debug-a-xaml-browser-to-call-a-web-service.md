---
title: "방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="ac64a-102">방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅</span><span class="sxs-lookup"><span data-stu-id="ac64a-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="ac64a-103">사용 권한 인터넷 영역 집합으로 제한 되는 부분 신뢰 보안 샌드박스에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="ac64a-104">이 권한 집합에는 웹 서비스 호출에 나와 있는 웹 서비스로을 제한 된 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 원본 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="ac64a-105">경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 에서 디버깅 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]경우 동일한 원본 사이트의 웹 서비스 참조 하도록 간주 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="ac64a-106">이 원인 보안 예외가 발생할 때에 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="ac64a-107">그러나 한 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 디버깅 하는 동안 호출 웹 서비스와 동일한 원본 사이트를 시뮬레이션할 하도록 프로젝트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-107">However, a [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="ac64a-108">이 통해는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 를 안전 하 게 보안 예외가 발생 하지 않고 웹 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>  
  
## <a name="configuring-visual-studio"></a><span data-ttu-id="ac64a-109">Visual Studio 구성</span><span class="sxs-lookup"><span data-stu-id="ac64a-109">Configuring Visual Studio</span></span>  
 <span data-ttu-id="ac64a-110">구성 하려면 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] 디버깅 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하는:</span><span class="sxs-lookup"><span data-stu-id="ac64a-110">To configure [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>  
  
1.  <span data-ttu-id="ac64a-111">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ac64a-112">에 **프로젝트 디자이너**, 클릭는 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-112">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="ac64a-113">에 **시작 작업** 섹션에서 **시작 외부 프로그램** 여 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  <span data-ttu-id="ac64a-114">에 **시작 옵션** 섹션에서 다음을 입력 하는 **명령줄 인수** 텍스트 상자:</span><span class="sxs-lookup"><span data-stu-id="ac64a-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="ac64a-115">`-debug`  *파일 이름*</span><span class="sxs-lookup"><span data-stu-id="ac64a-115">`-debug`  *filename*</span></span>  
  
     <span data-ttu-id="ac64a-116">*filename* 에 대 한 값의 **-디버그** 매개 변수는.xbap 파일 이름 예:</span><span class="sxs-lookup"><span data-stu-id="ac64a-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  <span data-ttu-id="ac64a-117">이 기본 구성이 사용 하 여 만든 솔루션에 대 한는 [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 서식 파일 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="ac64a-117">This is the default configuration for solutions that are created with the [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>  
  
1.  <span data-ttu-id="ac64a-118">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ac64a-119">에 **프로젝트 디자이너**, 클릭는 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-119">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="ac64a-120">에 **시작 옵션** 섹션을 추가 하려면 다음 명령줄 매개 변수는 **명령줄 인수** 텍스트 상자:</span><span class="sxs-lookup"><span data-stu-id="ac64a-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="ac64a-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="ac64a-121">`-debugSecurityZoneURL`  *URL*</span></span>  
  
     <span data-ttu-id="ac64a-122">*URL* 에 대 한 값은 **-debugSecurityZoneURL** 매개 변수는는 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] 시뮬레이션할 응용 프로그램의 원본 사이트를 원하는 위치에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac64a-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>  
  
 <span data-ttu-id="ac64a-123">예를 들어 고려는 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 다음 웹 서비스를 사용 하는 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ac64a-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 <span data-ttu-id="ac64a-124">원본 사이트의 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 이 웹 서비스는:</span><span class="sxs-lookup"><span data-stu-id="ac64a-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>  
  
 `http://services.msdn.microsoft.com`  
  
 <span data-ttu-id="ac64a-125">따라서 전체 **-debugSecurityZoneURL** 명령줄 매개 변수 및 값은:</span><span class="sxs-lookup"><span data-stu-id="ac64a-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a><span data-ttu-id="ac64a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac64a-126">See Also</span></span>  
 [<span data-ttu-id="ac64a-127">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="ac64a-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
