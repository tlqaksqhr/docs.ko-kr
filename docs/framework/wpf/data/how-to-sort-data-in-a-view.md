---
title: '방법: 뷰의 데이터 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 5c79261983fcf6200120bcfbf180d155aca3c3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556759"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="682c4-102">방법: 뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="682c4-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="682c4-103">이 예에서는 뷰에서 데이터를 정렬 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="682c4-104">예제</span><span class="sxs-lookup"><span data-stu-id="682c4-104">Example</span></span>  
 <span data-ttu-id="682c4-105">다음 예제에서는 간단한 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="682c4-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="682c4-106"><xref:System.Windows.Controls.Primitives.ButtonBase.Click> 단추의 이벤트 처리기에서 항목을 정렬 하기 위한 논리가 포함 된 <xref:System.Windows.Controls.ListBox> 내림차순에서입니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="682c4-107">에 항목을 추가 하기 때문에이 수행할 수 있습니다는 <xref:System.Windows.Controls.ListBox> 이러한 방식으로 추가 <xref:System.Windows.Controls.ItemCollection> 의 <xref:System.Windows.Controls.ListBox>, 및 <xref:System.Windows.Controls.ItemCollection> 에서 파생 되는 <xref:System.Windows.Data.CollectionView> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="682c4-108">바인딩하는 경우 프로그램 <xref:System.Windows.Controls.ListBox> 사용 하 여 컬렉션에는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 정렬 하려면 동일한 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="682c4-109">보기 개체에 대 한 참조를가지고 다른 컬렉션 보기의 콘텐츠를 정렬 하려면 동일한 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="682c4-110">보기가 하는 방법의 예제를 보려면 [데이터 컬렉션의 기본 보기 가져올](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="682c4-111">또 다른 예에 대 한 참조 [는 GridView 열 정도 머리글을 클릭 하면 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="682c4-112">보기에 대 한 자세한 내용은 참조에서 컬렉션에 바인딩을 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="682c4-113">정렬 논리를 적용 하는 방법의 예 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 참조 [정렬 및 그룹 사용 하 여 데이터를 보려면](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="682c4-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682c4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="682c4-114">See Also</span></span>  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [<span data-ttu-id="682c4-115">헤더를 클릭하면 GridView 열 정렬</span><span class="sxs-lookup"><span data-stu-id="682c4-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [<span data-ttu-id="682c4-116">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="682c4-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="682c4-117">뷰에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="682c4-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="682c4-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="682c4-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
