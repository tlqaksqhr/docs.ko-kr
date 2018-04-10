---
title: 응용 프로그램 개발
ms.custom: ''
ms.date: 01/26/2018
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d2a79a05f18fecf4e008aa6a95d359c719e854b
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="application-development"></a><span data-ttu-id="2c0fe-102">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="2c0fe-102">Application Development</span></span>
<a name="introduction"></a>
<span data-ttu-id="2c0fe-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]다음과 같은 종류의 응용 프로그램을 개발 하는 데 사용할 수 있는 프레젠테이션 프레임 워크:</span><span class="sxs-lookup"><span data-stu-id="2c0fe-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
-   <span data-ttu-id="2c0fe-104">독립 실행형 응용 프로그램(클라이언트 컴퓨터에 설치되어 실행되는 실행 가능한 어셈블리로 빌드된 전형적인 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 응용 프로그램)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-104">Standalone Applications (traditional style [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="2c0fe-105">(실행 가능한 어셈블리로 빌드되고 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 또는 Mozilla Firefox와 같은 웹 브라우저에서 호스트하는 탐색 페이지로 구성된 응용 프로그램)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-105"> (applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] or Mozilla Firefox).</span></span>  
  
-   <span data-ttu-id="2c0fe-106">사용자 지정 컨트롤 라이브러리(재사용 가능한 컨트롤을 포함하는 실행 불가능한 어셈블리)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-106">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
-   <span data-ttu-id="2c0fe-107">클래스 라이브러리(재사용 가능한 클래스를 포함하는 실행 불가능한 어셈블리)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-107">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c0fe-108">Windows 서비스에서 WPF 유형을 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="2c0fe-109">Windows 서비스에서 이러한 기능을 사용하려고 하면 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-109">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="2c0fe-110">이 응용 프로그램 집합을 빌드하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 서비스 호스트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-110">To build this set of applications, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implements a host of services.</span></span> <span data-ttu-id="2c0fe-111">이 항목에서 이러한 서비스의 개요를 제공하며 자세한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-111">This topic provides an overview of these services and where to find more information.</span></span>  
  

  
<a name="Application_Management"></a>   
## <a name="application-management"></a><span data-ttu-id="2c0fe-112">응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="2c0fe-112">Application Management</span></span>  
 <span data-ttu-id="2c0fe-113">실행 가능한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에는 일반적으로 다음을 포함하는 핵심 기능 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-113">Executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications commonly require a core set of functionality that includes the following:</span></span>  
  
-   <span data-ttu-id="2c0fe-114">일반적인 응용 프로그램 인프라 만들기 및 관리(시스템 및 입력 메시지를 수신하는 Windows 메시지 루프 및 진입점 메서드 만들기 포함)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-114">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
-   <span data-ttu-id="2c0fe-115">응용 프로그램의 수명 추적 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="2c0fe-115">Tracking and interacting with the lifetime of an application.</span></span>  
  
-   <span data-ttu-id="2c0fe-116">명령줄 매개 변수 검색 및 처리</span><span class="sxs-lookup"><span data-stu-id="2c0fe-116">Retrieving and processing command-line parameters.</span></span>  
  
-   <span data-ttu-id="2c0fe-117">응용 프로그램 범위 속성 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 리소스 공유</span><span class="sxs-lookup"><span data-stu-id="2c0fe-117">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
-   <span data-ttu-id="2c0fe-118">처리되지 않은 예외 검색 및 처리</span><span class="sxs-lookup"><span data-stu-id="2c0fe-118">Detecting and processing unhandled exceptions.</span></span>  
  
-   <span data-ttu-id="2c0fe-119">종료 코드 반환</span><span class="sxs-lookup"><span data-stu-id="2c0fe-119">Returning exit codes.</span></span>  
  
-   <span data-ttu-id="2c0fe-120">독립 실행형 응용 프로그램에서 창 관리</span><span class="sxs-lookup"><span data-stu-id="2c0fe-120">Managing windows in standalone applications.</span></span>  
  
-   <span data-ttu-id="2c0fe-121">탐색 창 및 프레임이 있는 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]에서 탐색 추적</span><span class="sxs-lookup"><span data-stu-id="2c0fe-121">Tracking navigation in [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="2c0fe-122">이러한 기능은 *응용 프로그램 정의*를 사용하여 응용 프로그램에 추가되는 <xref:System.Windows.Application> 클래스에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-122">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="2c0fe-123">자세한 내용은 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-123">For more information, see [Application Management Overview](../../../../docs/framework/wpf/app-development/application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="2c0fe-124">WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="2c0fe-124">WPF Application Resource, Content, and Data Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="2c0fe-125">는 세 종류의 실행 불가능한 데이터 파일(리소스, 콘텐츠 및 데이터)에 대한 지원으로 포함된 리소스에 대한 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 핵심 지원을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-125"> extends the core support in the [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="2c0fe-126">자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-126">For more information, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="2c0fe-127">WPF 실행 불가능 데이터 파일에 대한 지원의 핵심 구성 요소는 고유한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 사용하여 이를 식별하고 로드하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-127">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="2c0fe-128">자세한 내용은 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-128">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="2c0fe-129">창 및 대화 상자</span><span class="sxs-lookup"><span data-stu-id="2c0fe-129">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="2c0fe-130">사용자는 창을 통해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-130">Users interact with [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone applications through windows.</span></span> <span data-ttu-id="2c0fe-131">창의 목적은 응용 프로그램 콘텐츠를 호스트하고 일반적으로 사용자가 콘텐츠와 상호 작용할 수 있도록 응용 프로그램 기능을 노출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-131">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="2c0fe-132">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창은 다음을 지원하는 <xref:System.Windows.Window> 클래스에 의해 캡슐화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-132">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
-   <span data-ttu-id="2c0fe-133">창 만들기 및 표시</span><span class="sxs-lookup"><span data-stu-id="2c0fe-133">Creating and showing windows.</span></span>  
  
-   <span data-ttu-id="2c0fe-134">소유자/피소유자 창 관계 설정</span><span class="sxs-lookup"><span data-stu-id="2c0fe-134">Establishing owner/owned window relationships.</span></span>  
  
-   <span data-ttu-id="2c0fe-135">창 모양 구성(예: 크기, 위치, 아이콘, 제목 표시줄 텍스트, 테두리)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-135">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
-   <span data-ttu-id="2c0fe-136">창의 수명 추적 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="2c0fe-136">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="2c0fe-137">자세한 내용은 [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-137">For more information, see [WPF Windows Overview](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="2c0fe-138"><xref:System.Windows.Window>는 대화 상자로 알려진 특별한 유형의 창을 만드는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-138"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="2c0fe-139">모달 및 모덜리스 유형의 대화 상자를 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-139">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="2c0fe-140">여러 응용 프로그램에서 일관된 사용자 환경과 재사용 가능성 이점을 제공하기 위해 편의상 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 공통 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 대화 상자 3개(<xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, <xref:System.Windows.Controls.PrintDialog>)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-140">For convenience, and the benefits of reusability and a consistent user experience across applications, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes three of the common [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="2c0fe-141">메시지 상자는 중요한 텍스트 정보를 보여 주고 간단한 예/아니요/확인/취소 질문을 묻는 특별한 유형의 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-141">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="2c0fe-142"><xref:System.Windows.MessageBox> 클래스를 사용하여 메시지 상자를 만들고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-142">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="2c0fe-143">자세한 내용은 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-143">For more information, see [Dialog Boxes Overview](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>   
## <a name="navigation"></a><span data-ttu-id="2c0fe-144">탐색</span><span class="sxs-lookup"><span data-stu-id="2c0fe-144">Navigation</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="2c0fe-145">에서는 페이지(<xref:System.Windows.Controls.Page>) 및 하이퍼링크(<xref:System.Windows.Documents.Hyperlink>)를 통한 웹 스타일 탐색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-145"> supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="2c0fe-146">다음을 포함한 다양한 방법으로 탐색을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-146">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
-   <span data-ttu-id="2c0fe-147">웹 브라우저에 호스트되는 독립 실행형 페이지</span><span class="sxs-lookup"><span data-stu-id="2c0fe-147">Standalone pages that are hosted in a Web browser.</span></span>  
  
-   <span data-ttu-id="2c0fe-148">웹 브라우저에 호스트되는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]로 컴파일된 페이지</span><span class="sxs-lookup"><span data-stu-id="2c0fe-148">Pages compiled into an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that is hosted in a Web browser.</span></span>  
  
-   <span data-ttu-id="2c0fe-149">독립 실행형 응용 프로그램으로 컴파일되고 탐색 창(<xref:System.Windows.Navigation.NavigationWindow>)에서 호스트하는 페이지</span><span class="sxs-lookup"><span data-stu-id="2c0fe-149">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
-   <span data-ttu-id="2c0fe-150">독립 실행형 페이지나 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 또는 독립 실행형 응용 프로그램으로 컴파일된 페이지에서 호스트할 수 있는 프레임(<xref:System.Windows.Controls.Frame>)에서 호스트되는 페이지</span><span class="sxs-lookup"><span data-stu-id="2c0fe-150">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] or a standalone application.</span></span>  
  
 <span data-ttu-id="2c0fe-151">탐색을 쉽게 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 다음을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-151">To facilitate navigation, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implements the following:</span></span>  
  
-   <span data-ttu-id="2c0fe-152">응용 프로그램 내 탐색을 지원하기 위해 <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서 사용되는 탐색 요청을 처리하기 위한 공유 탐색 엔진 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="2c0fe-152"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] to support intra-application navigation.</span></span>  
  
-   <span data-ttu-id="2c0fe-153">탐색을 시작하는 탐색 메서드</span><span class="sxs-lookup"><span data-stu-id="2c0fe-153">Navigation methods to initiate navigation.</span></span>  
  
-   <span data-ttu-id="2c0fe-154">탐색 수명을 추적하고 상호 작용하는 탐색 이벤트</span><span class="sxs-lookup"><span data-stu-id="2c0fe-154">Navigation events to track and interact with navigation lifetime.</span></span>  
  
-   <span data-ttu-id="2c0fe-155">저널을 사용하여 뒤로/앞으로 탐색 저장(검사하고 조작할 수도 있음)</span><span class="sxs-lookup"><span data-stu-id="2c0fe-155">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="2c0fe-156">자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-156">For information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="2c0fe-157">는 구조적 탐색이라고 알려진 특별한 유형의 탐색도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-157"> also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="2c0fe-158">구조적 탐색을 사용하여 호출 함수와 일치하는 구조적이고 예측 가능한 방식으로 데이터를 반환하는 하나 이상의 페이지를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-158">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="2c0fe-159">이 기능은 <xref:System.Windows.Navigation.PageFunction%601> 클래스에 따라 달라지며 [구조적 탐색 개요](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-159">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).</span></span> <span data-ttu-id="2c0fe-160"><xref:System.Windows.Navigation.PageFunction%601>은 복잡한 탐색 토폴로지 생성을 간소화하는 역할도 합니다. 이러한 탐색 토폴로지에 대한 설명은 [탐색 토폴로지 개요](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-160"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>   
## <a name="hosting"></a><span data-ttu-id="2c0fe-161">호스팅</span><span class="sxs-lookup"><span data-stu-id="2c0fe-161">Hosting</span></span>  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]<span data-ttu-id="2c0fe-162">는 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 또는 Firefox에 호스트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-162"> can be hosted in [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] or Firefox.</span></span> <span data-ttu-id="2c0fe-163">각 호스팅 모델에는 [호스팅](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)에서 다루는 고유한 고려 사항 및 제약 조건 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-163">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a><span data-ttu-id="2c0fe-164">빌드 및 배포</span><span class="sxs-lookup"><span data-stu-id="2c0fe-164">Build and Deploy</span></span>  
 <span data-ttu-id="2c0fe-165">명령줄 컴파일러를 사용하여 명령 프롬프트에서 간단한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 빌드할 수 있지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]와 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]가 통합되어 개발 및 빌드 프로세스를 단순화한 추가 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-165">Although simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications can be built from a command prompt using command-line compilers, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrates with [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="2c0fe-166">자세한 내용은 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-166">For more information, see [Building a WPF Application](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="2c0fe-167">빌드하는 응용 프로그램의 유형에 따라 선택할 수 있는 하나 이상의 배포 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-167">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="2c0fe-168">자세한 내용은 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-168">For more information, see [Deploying a WPF Application](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="2c0fe-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2c0fe-169">Related Topics</span></span>  
  
|<span data-ttu-id="2c0fe-170">제목</span><span class="sxs-lookup"><span data-stu-id="2c0fe-170">Title</span></span>|<span data-ttu-id="2c0fe-171">설명</span><span class="sxs-lookup"><span data-stu-id="2c0fe-171">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2c0fe-172">응용 프로그램 관리 개요</span><span class="sxs-lookup"><span data-stu-id="2c0fe-172">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)|<span data-ttu-id="2c0fe-173">응용 프로그램 수명, 창, 응용 프로그램 리소스 및 탐색 관리를 비롯하여 <xref:System.Windows.Application> 클래스에 대해 개략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-173">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="2c0fe-174">WPF의 창</span><span class="sxs-lookup"><span data-stu-id="2c0fe-174">Windows in WPF</span></span>](../../../../docs/framework/wpf/app-development/windows-in-wpf-applications.md)|<span data-ttu-id="2c0fe-175"><xref:System.Windows.Window> 클래스 및 대화 상자의 사용 방법을 비롯하여 응용 프로그램의 창 관리에 대해 세부적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-175">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="2c0fe-176">탐색 개요</span><span class="sxs-lookup"><span data-stu-id="2c0fe-176">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)|<span data-ttu-id="2c0fe-177">응용 프로그램 페이지 간의 탐색 관리에 대해 개략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-177">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="2c0fe-178">호스팅</span><span class="sxs-lookup"><span data-stu-id="2c0fe-178">Hosting</span></span>](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)|<span data-ttu-id="2c0fe-179">
          [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]에 대한 개요를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-179">Provides an overview of [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].</span></span>|  
|[<span data-ttu-id="2c0fe-180">빌드 및 배포</span><span class="sxs-lookup"><span data-stu-id="2c0fe-180">Build and Deploy</span></span>](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)|<span data-ttu-id="2c0fe-181">WPF 응용 프로그램을 빌드하고 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-181">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="2c0fe-182">Visual Studio에서의 WPF 소개</span><span class="sxs-lookup"><span data-stu-id="2c0fe-182">Introduction to WPF in Visual Studio</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="2c0fe-183">WPF의 주요 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-183">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="2c0fe-184">연습: 내 첫 WPF 데스크톱 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2c0fe-184">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="2c0fe-185">페이지 탐색, 레이아웃, 컨트롤, 이미지, 스타일 및 바인딩을 사용하여 WPF 응용 프로그램을 만드는 방법을 보여 주는 연습입니다.</span><span class="sxs-lookup"><span data-stu-id="2c0fe-185">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
