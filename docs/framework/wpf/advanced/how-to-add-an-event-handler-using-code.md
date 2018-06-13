---
title: '방법: 코드를 사용하여 이벤트 처리기 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 782f668557c3cb081d30e7835006af63c9ca4df5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542625"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="de95c-102">방법: 코드를 사용하여 이벤트 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="de95c-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="de95c-103">이 예제 코드를 사용 하 여 요소에 이벤트 처리기를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="de95c-104">이벤트 처리기를 추가 하려는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소와 요소를 포함 하는 태그 페이지 이미 로드 된 코드를 사용 하 여 처리기를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="de95c-105">또는 응용 프로그램 코드를 사용 하 여 전체 하지를 사용 하 여 요소를 선언 하 고 요소 트리를 작성 하는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 생성 된 요소 트리를 이벤트 처리기를 추가 하는 특정 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de95c-106">예제</span><span class="sxs-lookup"><span data-stu-id="de95c-106">Example</span></span>  
 <span data-ttu-id="de95c-107">다음 예제에서는 새 <xref:System.Windows.Controls.Button> 처음에 정의 된 기존 페이지 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="de95c-108">코드 숨김 파일 이벤트 처리기 메서드를 구현 하 고 다음에 새 이벤트 처리기로 해당 메서드를 추가 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="de95c-109">사용 하 여 C# 예제는 `+=` 이벤트에 대 한 처리기를 할당 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="de95c-110">이것이에서 처리기를 할당 하는 데 사용 되는 동일한 연산자는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 처리 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="de95c-111">Microsoft Visual Basic의 이벤트 처리기를 추가 하는 방법으로이 연산자를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="de95c-112">대신 두 가지 방법 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="de95c-113">사용 하 여는 <xref:System.Windows.UIElement.AddHandler%2A> 메서드를 함께 `AddressOf` 연산자 참조할 이벤트 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="de95c-114">사용 된 `Handles` 이벤트 처리기 정의의 일부로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="de95c-115">이 기술은; 여기 표시 되지 않습니다. 참조 [Visual Basic 및 WPF 이벤트 처리](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="de95c-116">에 처음 구문 분석 된 이벤트 처리기를 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 훨씬 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="de95c-117">이벤트 처리기를 추가 하려는 개체 요소 내에서 처리 하려면 이벤트의 이름과 일치 하는 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="de95c-118">다음의 코드 숨김 파일에 정의 된 이벤트 처리기 메서드의 이름으로 해당 특성의 값을 지정 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지.</span><span class="sxs-lookup"><span data-stu-id="de95c-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="de95c-119">자세한 내용은 참조 [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 또는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de95c-119">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de95c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de95c-120">See Also</span></span>  
 [<span data-ttu-id="de95c-121">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="de95c-121">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="de95c-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="de95c-122">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
