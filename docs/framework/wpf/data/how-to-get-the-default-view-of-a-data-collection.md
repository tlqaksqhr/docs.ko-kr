---
title: "방법: 데이터 수집의 기본 뷰 가져오기"
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
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="182bf-102">방법: 데이터 수집의 기본 뷰 가져오기</span><span class="sxs-lookup"><span data-stu-id="182bf-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="182bf-103">뷰는 동일한 데이터 수집을 정렬, 필터링 또는 그룹화 기준에 따라 다양 한 방법으로 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="182bf-104">모든 컬렉션에 바인딩 원본으로 컬렉션을 지정 하는 경우 실제 바인딩 원본으로 사용 되는 하나의 공유 기본 보기.</span><span class="sxs-lookup"><span data-stu-id="182bf-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="182bf-105">이 예제에는 컬렉션의 기본 보기를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="182bf-106">예제</span><span class="sxs-lookup"><span data-stu-id="182bf-106">Example</span></span>  
 <span data-ttu-id="182bf-107">보기를 만들려면 컬렉션에 대 한 개체 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="182bf-108">데이터 원본의 속성을 가져오거나 또는 바인딩 속성을 가져오거나 데이터 컨텍스트를 가져와 사용자 고유의 코드 숨김 개체를 참조 하 여이 데이터 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="182bf-109">가져오는 방법을 보여 주는이 예제는 <xref:System.Windows.FrameworkElement.DataContext%2A> 이 컬렉션에 대 한 보기를 직접 기본 컬렉션을 얻기 위해 데이터 개체 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="182bf-110">이 예제에서는 루트 요소는 한 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="182bf-111"><xref:System.Windows.FrameworkElement.DataContext%2A> 로 설정 된 *myDataSource*, 데이터 공급자를 참조 하는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 *순서* 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="182bf-112">또는 인스턴스화할 수를 사용 하 여 사용자 고유의 컬렉션 뷰를 바인딩하는 <xref:System.Windows.Data.CollectionViewSource> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="182bf-113">이 컬렉션 뷰에 직접 바인딩된 컨트롤에서만 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="182bf-114">예를 들어 뷰 섹션 만들기 하는 방법을 참조 하십시오.는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="182bf-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="182bf-115">컬렉션 보기에서 제공 하는 기능의 예 참조 [보기의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [보기에서 필터 데이터](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), 및 [데이터 수집 뷰의the의개체를통해이동](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="182bf-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182bf-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="182bf-116">See Also</span></span>  
 [<span data-ttu-id="182bf-117">XAML 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="182bf-117">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="182bf-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="182bf-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
