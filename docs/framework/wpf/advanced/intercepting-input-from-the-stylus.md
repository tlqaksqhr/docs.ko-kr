---
title: "스타일러스에서 입력 가로채기"
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
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 611a2d2de56025e2f1b5add6106294834586f9af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="d4be1-102">스타일러스에서 입력 가로채기</span><span class="sxs-lookup"><span data-stu-id="d4be1-102">Intercepting Input from the Stylus</span></span>
<span data-ttu-id="d4be1-103"><xref:System.Windows.Input.StylusPlugIns> 통해 수준이 낮은 제어를 구현 하기 위한 메커니즘을 제공 하는 아키텍처 <xref:System.Windows.Input.Stylus> 입력을 디지털 잉크 만들 <xref:System.Windows.Ink.Stroke> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="d4be1-104"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스는 사용자 지정 동작을 구현 하 고 최적의 성능을 위해 스타일러스 장치에서 가져온 데이터의 스트림에 적용 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="d4be1-105">이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-105">This topic contains the following subsections:</span></span>  
  
-   [<span data-ttu-id="d4be1-106">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4be1-106">Architecture</span></span>](#Architecture)  
  
-   [<span data-ttu-id="d4be1-107">스타일러스 플러그 인을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
-   [<span data-ttu-id="d4be1-108">InkCanvas에 플러그 인 추가</span><span class="sxs-lookup"><span data-stu-id="d4be1-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
-   [<span data-ttu-id="d4be1-109">결론</span><span class="sxs-lookup"><span data-stu-id="d4be1-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a><span data-ttu-id="d4be1-110">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4be1-110">Architecture</span></span>  
 <span data-ttu-id="d4be1-111"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에서 향상 된는 [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) 에 설명 된 Api [액세스 및 조작 펜 입력](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)에 [Microsoft Windows XP Tablet PC Edition 소프트웨어 개발 키트 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) APIs, described in [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), in the [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).</span></span>  
  
 <span data-ttu-id="d4be1-112">각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 않는 속성이 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="d4be1-113">추가할 수 있습니다는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 요소를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 조작 하는 속성 <xref:System.Windows.Input.StylusPoint> 그대로 데이터를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="d4be1-114"><xref:System.Windows.Input.StylusPoint>데이터를 포함 하 여 시스템 디지타이저에서 지 원하는 모든 속성의 구성에서 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 포인트 데이터와 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="d4be1-115">프로그램 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체가에서 가져온 데이터의 스트림으로 직접 삽입 되는 <xref:System.Windows.Input.Stylus> 추가할 때 장치는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="d4be1-116">플러그 인에 추가 되는 순서는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션 받게 됩니다 순서가 결정 <xref:System.Windows.Input.StylusPoint> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="d4be1-117">예를 들어 특정 지역에 대 한 입력을 제한 하는 필터 플러그 인을 추가 하 고 작성 된 대로 제스처를 인식 하는 플러그 인을 추가 하는 경우 제스처를 인식 하는 플러그 인 받습니다 필터링 된 <xref:System.Windows.Input.StylusPoint> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="d4be1-118">스타일러스 플러그 인을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-118">Implementing Stylus Plug-ins</span></span>  
 <span data-ttu-id="d4be1-119">플러그 인을 구현 하려면에서 클래스를 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="d4be1-120">제공 하는 대로이 클래스는 스트림에 적용된 데이터는 <xref:System.Windows.Input.Stylus>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="d4be1-121">이 클래스에서의 값을 수정할 수는 <xref:System.Windows.Input.StylusPoint> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d4be1-122">경우는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throw 되거나 응용 프로그램이 종료 되므로 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="d4be1-123">사용 하는 컨트롤을 철저히 테스트 해야는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 없을 경우에 컨트롤을 사용 하 고는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 예외를 throw 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="d4be1-124">다음 예제를 수정 하 여 스타일러스 입력을 제한 하는 플러그 인은 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 값에 <xref:System.Windows.Input.StylusPoint> 에서 나오는 데이터를는 <xref:System.Windows.Input.Stylus> 장치.</span><span class="sxs-lookup"><span data-stu-id="d4be1-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="d4be1-125">InkCanvas에 플러그 인 추가</span><span class="sxs-lookup"><span data-stu-id="d4be1-125">Adding Your Plug-in to an InkCanvas</span></span>  
 <span data-ttu-id="d4be1-126">InkCanvas에서 파생 되는 클래스를 구현에 추가 하는 사용자 지정 플러그 인을 사용 하는 가장 쉬운 방법은 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="d4be1-127">다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 잉크를 필터링 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="d4be1-128">추가 하는 경우는 `FilterInkCanvas` 응용 프로그램을 실행 하려면를 알게 될 사용자가 스트로크를 완료 한 후 잉크 될 때까지 지역으로 제한 없음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="d4be1-129">¿¡´는 <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성, 즉는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 소속 되어는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="d4be1-130">사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 추가 하는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션 받는 <xref:System.Windows.Input.StylusPoint> 후 데이터 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="d4be1-131">결과적으로 <xref:System.Windows.Input.StylusPoint> 데이터는 사용자가 스트로크를 종료 하려면 펜 뗄 후까지 필터링 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="d4be1-132">삽입 해야 사용자가 그리는 처럼 잉크를 필터링 하려면는 `FilterPlugin` 하기 전에 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="d4be1-133">다음 C# 코드에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 를 그릴 때 잉크를 필터링 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="d4be1-134">결론</span><span class="sxs-lookup"><span data-stu-id="d4be1-134">Conclusion</span></span>  
 <span data-ttu-id="d4be1-135">직접 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스와에 삽입 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 컬렉션, 디지털 잉크의 동작을 크게 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="d4be1-136">에 액세스할 수 있는 <xref:System.Windows.Input.StylusPoint> 으로 사용자 지정할 수 있도록 데이터를 생성 되는 <xref:System.Windows.Input.Stylus> 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="d4be1-137">이러한 하위 수준 액세스를 갖고 있으므로 <xref:System.Windows.Input.StylusPoint> 데이터를 응용 프로그램에 대 한 잉크 컬렉션 및 최적의 성능으로 렌더링을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4be1-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4be1-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4be1-138">See Also</span></span>  
 [<span data-ttu-id="d4be1-139">고급 잉크 처리</span><span class="sxs-lookup"><span data-stu-id="d4be1-139">Advanced Ink Handling</span></span>](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [<span data-ttu-id="d4be1-140">액세스 및 조작을 펜 입력</span><span class="sxs-lookup"><span data-stu-id="d4be1-140">Accessing and Manipulating Pen Input</span></span>](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
