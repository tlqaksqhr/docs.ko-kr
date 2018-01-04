---
title: "잉크 수집"
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
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbf55b5d84420a6aa7af06e94497a85a2b54a0c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-ink"></a><span data-ttu-id="2d38f-102">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="2d38f-102">Collecting Ink</span></span>
<span data-ttu-id="2d38f-103">[Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) 플랫폼은 기능의 핵심 요소로서 디지털 잉크를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="2d38f-104">이 항목에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서 잉크를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-104">This topic discusses methods for collection of ink in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d38f-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2d38f-105">Prerequisites</span></span>  
 <span data-ttu-id="2d38f-106">다음에 나오는 예제를 사용하려면 먼저 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]와 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-106">To use the following examples, you must first install [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="2d38f-107">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-107">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="2d38f-108">시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-108">For more information about getting started with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="using-the-inkcanvas-element"></a><span data-ttu-id="2d38f-109">InkCanvas 요소 사용</span><span class="sxs-lookup"><span data-stu-id="2d38f-109">Using the InkCanvas Element</span></span>  
 <span data-ttu-id="2d38f-110"><xref:System.Windows.Controls.InkCanvas> 요소에 잉크를 수집 하는 가장 쉬운 방법은 제공 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-110">The <xref:System.Windows.Controls.InkCanvas> element provides the easiest way to collect ink in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="2d38f-111"><xref:System.Windows.Controls.InkCanvas> 요소는 비슷합니다는 [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) 에서 개체는 [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] 및 이전 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-111">The <xref:System.Windows.Controls.InkCanvas> element is similar to the [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) object from the [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] and earlier versions.</span></span>  
  
 <span data-ttu-id="2d38f-112">사용 하 여 프로그램 <xref:System.Windows.Controls.InkCanvas> 요소를 수신 및 잉크 입력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-112">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="2d38f-113">일반적으로 스타일러스를 사용하여 잉크를 입력합니다.이 스타일러스는 디지타이저와 상호 작용하여 잉크 스트로크를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-113">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="2d38f-114">또한 스타일러스 대신 마우스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-114">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="2d38f-115">생성된 된 스트로크도 표현 됩니다 <xref:System.Windows.Ink.Stroke> , 이러한 개체를 프로그래밍 방식으로 및 사용자가 입력 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-115">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="2d38f-116"><xref:System.Windows.Controls.InkCanvas> 선택, 수정 또는 삭제는 기존 수 있도록 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-116">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>  
  
 <span data-ttu-id="2d38f-117">XAML을 사용하면 트리에 `InkCanvas` 요소를 추가하는 것처럼 쉽게 잉크 컬렉션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-117">By using XAML, you can set up ink collection as easily as adding an `InkCanvas` element to your tree.</span></span> <span data-ttu-id="2d38f-118">다음 예제에서는 추가 <xref:System.Windows.Controls.InkCanvas> 을 기본값 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 만든 프로젝트 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-118">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project created in [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].</span></span>  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 <span data-ttu-id="2d38f-119">`InkCanvas` 요소는 자식 요소를 포함할 수도 있으므로 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-119">The `InkCanvas` element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="2d38f-120">예를 들어 잉크 기능에 텍스트 요소를 추가 하려면 단순히 자식으로 만듭니다의 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-120">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 <span data-ttu-id="2d38f-121">잉크로 이미지를 표시하기 위한 지원 기능을 추가하는 것도 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-121">Adding support for marking up an image with ink is just as easy.</span></span>  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a><span data-ttu-id="2d38f-122">InkCollection 모드</span><span class="sxs-lookup"><span data-stu-id="2d38f-122">InkCollection Modes</span></span>  
 <span data-ttu-id="2d38f-123"><xref:System.Windows.Controls.InkCanvas> 다양 한 입력을 통해 모드 지원을 제공 해당 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-123">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>  
  
### <a name="manipulating-ink"></a><span data-ttu-id="2d38f-124">잉크 조작</span><span class="sxs-lookup"><span data-stu-id="2d38f-124">Manipulating Ink</span></span>  
 <span data-ttu-id="2d38f-125"><xref:System.Windows.Controls.InkCanvas> 많은 잉크 편집 작업에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-125">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="2d38f-126">예를 들어 <xref:System.Windows.Controls.InkCanvas> 요소에 기능을 추가 하는 데 필요한 추가 코드 없이 지원 펜 백 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-126">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase with no additional code needed to add the functionality to the element.</span></span>  
  
#### <a name="selection"></a><span data-ttu-id="2d38f-127">선택</span><span class="sxs-lookup"><span data-stu-id="2d38f-127">Selection</span></span>  
 <span data-ttu-id="2d38f-128">선택 모드를 설정 하는 작업은 설정으로는 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-128">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span> <span data-ttu-id="2d38f-129">값에 따라 편집 모드를 설정 하는 다음 코드는 <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="2d38f-129">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a><span data-ttu-id="2d38f-130">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="2d38f-130">DrawingAttributes</span></span>  
 <span data-ttu-id="2d38f-131">사용 된 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 잉크 스트로크의 모양을 변경할 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-131">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="2d38f-132">예를 들어,는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 소속 <xref:System.Windows.Ink.DrawingAttributes> 는 렌더링 된 색을 설정 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-132">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="2d38f-133">다음 예제에서는 선택한 스트로크의 색을 빨강으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-133">The following example changes the color of the selected strokes to red.</span></span>  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a><span data-ttu-id="2d38f-134">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="2d38f-134">DefaultDrawingAttributes</span></span>  
 <span data-ttu-id="2d38f-135"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성은 높이, 너비 및에 만들어질 선의 색 같은 속성에 대 한 액세스를 제공는 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-135">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="2d38f-136">변경 하면는 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>에 입력 한 모든 이후 스트로크는 <xref:System.Windows.Controls.InkCanvas> 새로운 속성 값으로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-136">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>  
  
 <span data-ttu-id="2d38f-137">수정할 뿐 아니라는 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 코드 숨김 파일에 XAML 구문을 지정 하는 데 사용할 수 있습니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-137">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span> <span data-ttu-id="2d38f-138">다음 XAML 코드에 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-138">The following XAML code demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="2d38f-139">이 코드를 사용하려면 Visual Studio 2005에서 "HelloInkCanvas"라는 새 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-139">To use this code, create a new [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project called "HelloInkCanvas" in Visual Studio 2005.</span></span> <span data-ttu-id="2d38f-140">Window1.xaml 파일의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-140">Replace the code in the Window1.xaml file with the following code.</span></span>  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="2d38f-141">그런 다음 코드 숨김 파일의 Window1 클래스 내에 다음 단추 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-141">Next, add the following button event handlers to the code behind file, inside the Window1 class.</span></span>  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 <span data-ttu-id="2d38f-142">이 코드를 복사한 후 Microsoft Visual Studio 2005에서 **F5** 키를 눌러 디버거에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-142">After copying this code, press **F5** in Microsoft Visual Studio 2005 to run the program in the debugger.</span></span>  
  
 <span data-ttu-id="2d38f-143">알림 방법을 <xref:System.Windows.Controls.StackPanel> 단추 위쪽에 배치 합니다.는 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-143">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="2d38f-144">단추의 위에 잉크 하려고 하면는 <xref:System.Windows.Controls.InkCanvas> 수집 하 고 단추 뒤 잉크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-144">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="2d38f-145">형제는 단추가 때문에 이것이 <xref:System.Windows.Controls.InkCanvas> 자식이 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-145">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="2d38f-146">또한 단추가 z 순서에서 더 앞서기 때문에 잉크가 단추 뒤에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d38f-146">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d38f-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d38f-147">See Also</span></span>  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
