---
title: '방법: 요소의 높이 속성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 467cd57c728be015fb9eb9b974ca6e81e4fd7754
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554861"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="8f22b-102">방법: 요소의 높이 속성 설정</span><span class="sxs-lookup"><span data-stu-id="8f22b-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="8f22b-103">예제</span><span class="sxs-lookup"><span data-stu-id="8f22b-103">Example</span></span>  
 <span data-ttu-id="8f22b-104">이 예제에서는 시각적으로 렌더링에 4 개의 높이 관련 속성 중에서 동작의 차이점을 설명 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="8f22b-105"><xref:System.Windows.FrameworkElement> 클래스 요소 높이 특성을 설명 하는 네 가지 속성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="8f22b-106">우선적으로 적용 하는 값은 다음과 같이 결정이 작업을 수행 하 고 이러한 네 가지 속성 충돌할 수 있습니다:는 <xref:System.Windows.FrameworkElement.MinHeight%2A> 값 우선는 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 에 우선 하는 값은 <xref:System.Windows.FrameworkElement.Height%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="8f22b-107">네 번째 속성인 <xref:System.Windows.FrameworkElement.ActualHeight%2A>, 읽기 전용 이므로 레이아웃 프로세스와 상호 작용에 의해 결정 된 실제 높이 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="8f22b-108">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제 그리기는 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)의 자식으로 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="8f22b-109">높이 속성을 변경할 수는 <xref:System.Windows.Shapes.Rectangle> 일련의를 사용 하 여 <xref:System.Windows.Controls.ListBox> 의 속성 값을 나타내는 요소 <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="8f22b-110">이러한 방식으로 각 속성의 우선 순위 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8f22b-111">다음 코드 숨김 예에서는 이벤트를 처리 하는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="8f22b-112">각 처리기에서 입력을 가져와 <xref:System.Windows.Controls.ListBox>를 값으로 구문 분석 하는 <xref:System.Double>, 하 고 지정된 된 높이 관련 속성에 값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="8f22b-113">높이 값도 문자열로 변환 되 고에 다양 한 기록 <xref:System.Windows.Controls.TextBlock> 요소 (해당 요소의 정의 선택 된 XAML에는 표시 되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="8f22b-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="8f22b-114">전체 샘플을 참조 하십시오. [높이 속성 샘플](http://go.microsoft.com/fwlink/?LinkID=159993)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f22b-114">For the complete sample, see [Height Properties Sample](http://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f22b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f22b-115">See Also</span></span>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [<span data-ttu-id="8f22b-116">요소의 너비 속성 설정</span><span class="sxs-lookup"><span data-stu-id="8f22b-116">Set the Width Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [<span data-ttu-id="8f22b-117">패널 개요</span><span class="sxs-lookup"><span data-stu-id="8f22b-117">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="8f22b-118">높이 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="8f22b-118">Height Properties Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159993)
