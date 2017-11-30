---
title: "방법: 요소의 너비 속성 설정"
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
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 830289f13ac89601f0d3539e2f4400e56a2476f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="b1d7c-102">방법: 요소의 너비 속성 설정</span><span class="sxs-lookup"><span data-stu-id="b1d7c-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="b1d7c-103">예제</span><span class="sxs-lookup"><span data-stu-id="b1d7c-103">Example</span></span>  
 <span data-ttu-id="b1d7c-104">이 예제에서는 시각적으로 렌더링에 4 개의 너비와 관련 된 속성 중에서 동작의 차이점을 설명 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="b1d7c-105"><xref:System.Windows.FrameworkElement> 클래스는 요소의 너비 특성을 설명 하는 네 가지 속성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="b1d7c-106">우선적으로 적용 하는 값은 다음과 같이 결정이 작업을 수행 하 고 이러한 네 가지 속성 충돌할 수 있습니다:는 <xref:System.Windows.FrameworkElement.MinWidth%2A> 값 우선는 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 에 우선 하는 값은 <xref:System.Windows.FrameworkElement.Width%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="b1d7c-107">네 번째 속성인 <xref:System.Windows.FrameworkElement.ActualWidth%2A>, 읽기 전용 이므로 레이아웃 프로세스와 상호 작용에 의해 결정 된 실제 너비를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="b1d7c-108">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제 그리기는 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)의 자식으로 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="b1d7c-109">두께 속성을 변경할 수는 <xref:System.Windows.Shapes.Rectangle> 일련의를 사용 하 여 <xref:System.Windows.Controls.ListBox> 의 속성 값을 나타내는 요소 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, 및 <xref:System.Windows.FrameworkElement.Width%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="b1d7c-110">이러한 방식으로 각 속성의 우선 순위 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b1d7c-111">다음 코드 숨김 예에서는 이벤트를 처리 하는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="b1d7c-112">입력을 사용 하는 각 사용자 지정 메서드는 <xref:System.Windows.Controls.ListBox>를 값으로 구문 분석 하는 <xref:System.Double>, 하 고 지정된 된 너비와 관련 된 속성에 값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="b1d7c-113">너비 값도 문자열로 변환 되 고에 다양 한 기록 <xref:System.Windows.Controls.TextBlock> 요소 (해당 요소의 정의 선택 된 XAML에는 표시 되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="b1d7c-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="b1d7c-114">전체 샘플을 참조 하십시오. [너비 속성 비교 샘플](http://go.microsoft.com/fwlink/?LinkID=160050)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d7c-114">For the complete sample, see [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d7c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1d7c-115">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [<span data-ttu-id="b1d7c-116">패널 개요</span><span class="sxs-lookup"><span data-stu-id="b1d7c-116">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="b1d7c-117">요소의 높이 속성 설정</span><span class="sxs-lookup"><span data-stu-id="b1d7c-117">Set the Height Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [<span data-ttu-id="b1d7c-118">너비 속성 비교 샘플</span><span class="sxs-lookup"><span data-stu-id="b1d7c-118">Width Properties Comparison Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160050)
