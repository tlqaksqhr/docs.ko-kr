---
title: "개체 트리에 없는 개체 요소 초기화"
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
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5d617176852e72b4b46e48ff9a4528bec373272
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a><span data-ttu-id="3c3fe-102">개체 트리에 없는 개체 요소 초기화</span><span class="sxs-lookup"><span data-stu-id="3c3fe-102">Initialization for Object Elements Not in an Object Tree</span></span>
<span data-ttu-id="3c3fe-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 초기화의 몇 가지 측면은 일반적으로 논리적 트리 또는 시각적 트리에 연결되는 요소에 의존하는 프로세스로 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-103">Some aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] initialization are deferred to processes that typically rely on that element being connected to either the logical tree or visual tree.</span></span> <span data-ttu-id="3c3fe-104">이 항목에서는 두 트리에 연결되지 않는 요소를 초기화하기 위해 필요할 수 있는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-104">This topic describes the steps that may be necessary in order to initialize an element that is not connected to either tree.</span></span>  
  
 
  
## <a name="elements-and-the-logical-tree"></a><span data-ttu-id="3c3fe-105">요소와 논리적 트리</span><span class="sxs-lookup"><span data-stu-id="3c3fe-105">Elements and the Logical Tree</span></span>  
 <span data-ttu-id="3c3fe-106">코드에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 인스턴스를 만들 때 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에 대한 개체 초기화의 몇 가지 측면은 클래스 생성자 호출 시 실행되는 코드의 일부가 아님을 알아 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-106">When you create an instance of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] class in code, you should be aware that several aspects of object initialization for a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] class are deliberately not a part of the code that is executed when calling the class constructor.</span></span> <span data-ttu-id="3c3fe-107">특히 컨트롤 클래스의 경우 해당 컨트롤의 시각적 표현 대부분은 생성자에 정의되지 않고</span><span class="sxs-lookup"><span data-stu-id="3c3fe-107">Particularly for a control class, most of the visual representation of that control is not defined by the constructor.</span></span> <span data-ttu-id="3c3fe-108">컨트롤의 템플릿에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-108">Instead, the visual representation is defined by the control's template.</span></span> <span data-ttu-id="3c3fe-109">템플릿의 소스는 다양할 수 있지만 대부분의 경우 템플릿은 테마 스타일에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-109">The template potentially comes from a variety of sources, but most often the template is obtained from theme styles.</span></span> <span data-ttu-id="3c3fe-110">템플릿은 실제로 런타임에 바인딩됩니다. 즉, 컨트롤 레이아웃 준비가 될 때까지는 필요한 템플릿이 해당 컨트롤에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-110">Templates are effectively late-binding; the necessary template is not attached to the control in question until the control is ready for layout.</span></span> <span data-ttu-id="3c3fe-111">또한 컨트롤은 루트에서 렌더링 화면에 연결되는 논리적 트리에 연결되기 전까지는 레이아웃 준비가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-111">And the control is not ready for layout until it is attached to a logical tree that connects to a rendering surface at the root.</span></span> <span data-ttu-id="3c3fe-112">모든 자식 요소의 렌더링을 논리적 트리에 정의된 대로 시작하는 것은 루트 수준 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-112">It is that root-level element that initiates the rendering of all of its child elements as defined in the logical tree.</span></span>  
  
 <span data-ttu-id="3c3fe-113">시각적 트리도 이 프로세스에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-113">The visual tree also participates in this process.</span></span> <span data-ttu-id="3c3fe-114">템플릿을 통하는 시각적 트리의 일부인 요소도 연결되기 전까지 완전히 인스턴스화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-114">Elements that are part of the visual tree through the templates are also not fully instantiated until connected.</span></span>  
  
 <span data-ttu-id="3c3fe-115">이 동작의 결과로 요소의 완성된 시각적 특성에 의존하는 특정 작업에서 추가적인 단계를 필요로 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-115">The consequences of this behavior are that certain operations that rely on the completed visual characteristics of an element require additional steps.</span></span> <span data-ttu-id="3c3fe-116">이에 대한 예로 생성되었지만 아직 트리에 연결되지 않은 클래스의 시각적 특성을 가져오려고 하는 경우를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-116">An example is if you are attempting to get the visual characteristics of a class that was constructed but not yet attached to a tree.</span></span> <span data-ttu-id="3c3fe-117">예를 들어, 호출 하려는 경우 <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> 에 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 전달 하는 시각적 개체가 트리에 연결 되어 있지는 요소와 추가 초기화 단계를 완료 될 때까지 요소가 시각적으로 완전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-117">For instance, if you want to call <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> on a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and the visual you are passing is an element not connected to a tree, that element is not visually complete until additional initialization steps are completed.</span></span>  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a><span data-ttu-id="3c3fe-118">BeginInit 및 EndInit를 사용하여 요소 초기화</span><span class="sxs-lookup"><span data-stu-id="3c3fe-118">Using BeginInit and EndInit to Initialize the Element</span></span>  
 <span data-ttu-id="3c3fe-119">다양 한 클래스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현에서 <xref:System.ComponentModel.ISupportInitialize> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-119">Various classes in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implement the <xref:System.ComponentModel.ISupportInitialize> interface.</span></span> <span data-ttu-id="3c3fe-120">사용 된 <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> 및 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 포함 초기화 단계 (예: 해당 렌더링에 영향을 값 속성을 설정) 된 코드에서 영역을 표시 하는 인터페이스의 메서드.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-120">You use the <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> and <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> methods of the interface to denote a region in your code that contains initialization steps (such as setting property values that affect rendering).</span></span> <span data-ttu-id="3c3fe-121">후 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 호출 되는 시퀀스에서 레이아웃 시스템 수 요소를 처리 하 고 암시적 스타일을 찾기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-121">After <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> is called in the sequence, the layout system can process the element and start looking for an implicit style.</span></span>  
  
 <span data-ttu-id="3c3fe-122">요소 설정 하는 경우 속성에는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스의 클래스 버전을 호출할 수 있습니다 <xref:System.Windows.FrameworkElement.BeginInit%2A> 및 <xref:System.Windows.FrameworkElement.EndInit%2A> 를 캐스팅 하는 대신 <xref:System.ComponentModel.ISupportInitialize>합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-122">If the element you are setting properties on is a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class, then you can call the class versions of <xref:System.Windows.FrameworkElement.BeginInit%2A> and <xref:System.Windows.FrameworkElement.EndInit%2A> rather than casting to <xref:System.ComponentModel.ISupportInitialize>.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="3c3fe-123">샘플 코드</span><span class="sxs-lookup"><span data-stu-id="3c3fe-123">Sample Code</span></span>  
 <span data-ttu-id="3c3fe-124">다음 예제는 렌더링을 사용 하는 콘솔 응용 프로그램에 대 한 샘플 코드 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 및 <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> 느슨한의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 적절 한 위치를 설명 하기 위해 <xref:System.Windows.FrameworkElement.BeginInit%2A> 및 <xref:System.Windows.FrameworkElement.EndInit%2A> 다른 주위 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 호출 렌더링에 영향을 주는 속성을 조정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-124">The following example is sample code for a console application that uses rendering [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] and <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> of a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file to illustrate the proper placement of <xref:System.Windows.FrameworkElement.BeginInit%2A> and <xref:System.Windows.FrameworkElement.EndInit%2A> around other [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] calls that adjust properties that affect rendering.</span></span>  
  
 <span data-ttu-id="3c3fe-125">이 예제는 main 함수만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-125">The example illustrates the main function only.</span></span> <span data-ttu-id="3c3fe-126">함수 `Rasterize` 및 `Save`(표시되지 않음)는 이미지 처리 및 IO를 처리하는 유틸리티 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3fe-126">The functions `Rasterize` and `Save` (not shown) are utility functions that take care of image processing and IO.</span></span>  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a><span data-ttu-id="3c3fe-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c3fe-127">See Also</span></span>  
 [<span data-ttu-id="3c3fe-128">WPF의 트리</span><span class="sxs-lookup"><span data-stu-id="3c3fe-128">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="3c3fe-129">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="3c3fe-129">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="3c3fe-130">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="3c3fe-130">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
