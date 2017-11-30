---
title: "잉크 시작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc8ffe9ad68060d9dfbcafe99133a736237a2bb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="22ff8-102">잉크 시작</span><span class="sxs-lookup"><span data-stu-id="22ff8-102">Getting Started with Ink</span></span>
<span data-ttu-id="22ff8-103">디지털 잉크 응용 프로그램에 통합 하는 것이 이전 보다 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="22ff8-104">잉크가 발전 하 고 완벽 한 통합을 위한 프로그래밍의 COM 및 Windows Forms 메서드를 자연스럽 게 구축 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="22ff8-105">별도 Sdk 또는 런타임 라이브러리를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="22ff8-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="22ff8-106">Prerequisites</span></span>  
 <span data-ttu-id="22ff8-107">다음 예제를 사용 하려면 먼저 설치 해야 Microsoft Visual Studio 2005 및 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="22ff8-108">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="22ff8-109">시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="22ff8-110">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="22ff8-110">Quick Start</span></span>  
 <span data-ttu-id="22ff8-111">이 섹션에서는 간단한을 작성 하는 데 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 잉크를 수집 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="22ff8-112">그렇게 이미 하지 않은 경우 Microsoft Visual Studio 2005를 설치 및 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="22ff8-113">응용 프로그램 일반적으로 전에 컴파일되어야 볼 수 공백으로만 구성 된 경우에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="22ff8-114">그러나는 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] 응용 프로그램이 포함 된, XamlPad 구현 과정을 가속화 하도록 디자인 된는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-UI를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="22ff8-115">보고 하 여 마다 개별적으로 처음 몇 가지 샘플이이 문서에서는 해당 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="22ff8-116">만드는 과정에서 컴파일된 응용 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 문서의 뒷부분에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="22ff8-117">XAMLPad를 실행 하려면 클릭는 **시작** 메뉴에서 **모든 프로그램**, 가리킨 **Microsoft Winndows SDK**, 가리킨 **도구**를 클릭 하 고 **XAMLPad**합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="22ff8-118">XAMLPad는 렌더링 창에서 코드 창에서 작성 된 XAML 코드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="22ff8-119">XAML 코드를 편집할 수 있으며 변경 내용이 즉시 렌더링 창에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="22ff8-120">잉크 사용</span><span class="sxs-lookup"><span data-stu-id="22ff8-120">Got Ink?</span></span>  
 <span data-ttu-id="22ff8-121">첫 번째를 시작 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 잉크를 지 원하는 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="22ff8-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="22ff8-122">Microsoft Visual Studio를 2005를 열으십시오</span><span class="sxs-lookup"><span data-stu-id="22ff8-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="22ff8-123">새 **Windows 응용 프로그램 (WPF)**</span><span class="sxs-lookup"><span data-stu-id="22ff8-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="22ff8-124">형식 `<InkCanvas/>` 사이 `<Grid>` 태그</span><span class="sxs-lookup"><span data-stu-id="22ff8-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="22ff8-125">키를 눌러 **F5** 디버거에서 응용 프로그램을 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="22ff8-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="22ff8-126">스타일러스 또는 마우스를 사용 하 여, 작성 **hello world** 창에서</span><span class="sxs-lookup"><span data-stu-id="22ff8-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="22ff8-127">잉크 해당 하는 12 키 입력으로는 "hello world" 응용 프로그램을 작성 했습니다!</span><span class="sxs-lookup"><span data-stu-id="22ff8-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="22ff8-128">응용 프로그램 꾸미기</span><span class="sxs-lookup"><span data-stu-id="22ff8-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="22ff8-129">일부 기능을 사용 하겠습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="22ff8-130">열기 사이 있는 모든 대체 \<창 > 태그와 닫는 \</Window > 태그를 다음 태그로 그라데이션 브러시 백그라운드 프로그램 잉크 표면에 얻으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="22ff8-131">애니메이션을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="22ff8-131">Using Animation</span></span>  
 <span data-ttu-id="22ff8-132">쉽도록 애니메이션 그라데이션 브러시의 색을 적용 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="22ff8-133">다음 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 닫은 후 `</InkCanvas>` 태그 닫히기 전까지 `</Page>` 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="22ff8-134">XAML 뒤에 있는 일부 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="22ff8-135">XAML을 사용 하면 매우 쉽게 사용자 인터페이스를 디자인 하려면, 실제 응용 프로그램 이벤트를 처리 하는 코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="22ff8-136">잉크 마우스에서 마우스 단추 클릭에 대 한 응답에서을 확대 하는 간단한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="22ff8-137">설정의 `MouseRightButtonUp` 처리기에 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="22ff8-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="22ff8-138">Visual Studio의 솔루션 탐색기에서 Windows1.xaml를 확장 하 고 코드 숨김 파일 Window1.xaml.cs 또는 Visual Basic을 사용 하는 경우 Window1.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="22ff8-139">다음 이벤트 처리기 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="22ff8-140">이제 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-140">Now, run your application.</span></span> <span data-ttu-id="22ff8-141">잉크를 추가한 다음 마우스 오른쪽 단추로 클릭 하거나 스타일러스로 키를 눌러 보류 동작을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="22ff8-142">프로시저 코드를 사용 하 여 XAML 대신</span><span class="sxs-lookup"><span data-stu-id="22ff8-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="22ff8-143">모든 액세스할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로시저 코드의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="22ff8-144">여기서는 "Hello 잉크 World" 응용 프로그램에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하나를 사용 하지 않는 하 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 전혀 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="22ff8-145">Visual Studio에서 빈 콘솔 응용 프로그램에 아래 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="22ff8-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="22ff8-146">PresentationCore, PresentationFramework, 및 WindowsBase 어셈블리에 대 한 참조를 추가 하 고 키를 눌러 응용 프로그램을 빌드합니다 **F5**:</span><span class="sxs-lookup"><span data-stu-id="22ff8-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="22ff8-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22ff8-147">See Also</span></span>  
 [<span data-ttu-id="22ff8-148">디지털 잉크</span><span class="sxs-lookup"><span data-stu-id="22ff8-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="22ff8-149">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="22ff8-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="22ff8-150">필기 인식</span><span class="sxs-lookup"><span data-stu-id="22ff8-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="22ff8-151">잉크 저장</span><span class="sxs-lookup"><span data-stu-id="22ff8-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
