---
title: '방법: 선택에 따라 수집 및 표시 정보에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 154f4b9b6024d064e73d64c44e2398a5da47052c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557411"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="542dc-102">방법: 선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="542dc-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="542dc-103">데이터 바인딩된 있는 간단한 마스터-세부 시나리오에서 <xref:System.Windows.Controls.ItemsControl> 와 같은 <xref:System.Windows.Controls.ListBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="542dc-104">선택한 항목에 대 한 자세한 정보를 표시할 사용자 선택에 따라 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="542dc-105">이 예제에서는이 시나리오를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="542dc-106">예제</span><span class="sxs-lookup"><span data-stu-id="542dc-106">Example</span></span>  
 <span data-ttu-id="542dc-107">이 예제에서는 `People` 는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `Person` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="542dc-108">이 `Person` 세 가지 속성을 포함 하는 클래스: `FirstName`, `LastName`, 및 `HomeTown`, 유형의 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="542dc-109"><xref:System.Windows.Controls.ContentControl> 에서는 다음과 같은 <xref:System.Windows.DataTemplate> 정의 하는 방법을의 정보는 `Person` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="542dc-110">다음은 예제에서 생성의 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="542dc-111"><xref:System.Windows.Controls.ContentControl> 선택 하는 사용자의 다른 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="542dc-112">![컬렉션에 바인딩](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="542dc-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="542dc-113">이 예에서 유념 해야 할 두 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="542dc-114"><xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl> 동일한 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="542dc-115"><xref:System.Windows.Data.Binding.Path%2A> 전체 컬렉션 개체를 두 컨트롤이 모두 바인딩하는 때문에 두 바인딩은 모두의 속성을 지정 하지 않으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="542dc-116">설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true` 이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="542dc-117">이 속성을 설정 하면 선택한 항목은 항상으로 설정 된다는 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="542dc-118">또는 경우는 <xref:System.Windows.Controls.ListBox> 에서 데이터를 가져오는 <xref:System.Windows.Data.CollectionViewSource>, 선택 및 통화 자동으로 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="542dc-119">`Person` 재정의 `ToString` 메서드는 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="542dc-120">기본적으로는 <xref:System.Windows.Controls.ListBox> 호출 `ToString` 바인딩된 컬렉션에 있는 각 개체의 문자열 표현을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="542dc-121">바로 이러한 이유로 각 `Person` 에 이름으로 표시는 <xref:System.Windows.Controls.ListBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="542dc-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="542dc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="542dc-122">See Also</span></span>  
 [<span data-ttu-id="542dc-123">계층적 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="542dc-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [<span data-ttu-id="542dc-124">계층적 XML 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="542dc-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [<span data-ttu-id="542dc-125">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="542dc-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="542dc-126">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="542dc-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="542dc-127">방법 항목</span><span class="sxs-lookup"><span data-stu-id="542dc-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
