---
title: "방법: LINQ 쿼리 결과에 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e77a0c698dae0330877c54422c15e14c82376891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="fd29b-102">방법: LINQ 쿼리 결과에 바인딩</span><span class="sxs-lookup"><span data-stu-id="fd29b-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="fd29b-103">이 예제에서는 LINQ 쿼리를 실행 한 다음 결과에 바인딩할 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd29b-104">예제</span><span class="sxs-lookup"><span data-stu-id="fd29b-104">Example</span></span>  
 <span data-ttu-id="fd29b-105">다음 예에서는 두 개의 목록 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-105">The following example creates two list boxes.</span></span> <span data-ttu-id="fd29b-106">첫 번째 목록 상자에는 세 가지 목록 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="fd29b-107">첫 번째 목록 상자에서 항목을 선택한 다음 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="fd29b-108">이 예제에서는 `Tasks` 의 컬렉션인 `Task` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="fd29b-109">`Task` 클래스 라는 속성이 `Priority`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="fd29b-110">이 이벤트 처리기의 컬렉션을 반환 하는 LINQ 쿼리 실행 `Task` 선택한 우선 순위 값이 있어야 하 고 다음으로 설정 하는 개체는 <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="fd29b-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="fd29b-111">두 번째 목록 상자 이므로 해당 컬렉션에 바인딩되는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 값으로 설정 되어 `{Binding}`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="fd29b-112">결과적으로 반환된 된 컬렉션을 표시 합니다 (기반는 `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="fd29b-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd29b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd29b-113">See Also</span></span>  
 [<span data-ttu-id="fd29b-114">XAML의 바인딩에 사용할 수 있는 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="fd29b-114">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [<span data-ttu-id="fd29b-115">선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="fd29b-115">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="fd29b-116">WPF 버전 4.5의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="fd29b-116">What's New in WPF Version 4.5</span></span>](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [<span data-ttu-id="fd29b-117">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="fd29b-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fd29b-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="fd29b-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
