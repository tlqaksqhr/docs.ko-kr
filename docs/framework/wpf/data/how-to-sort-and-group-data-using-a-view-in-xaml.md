---
title: "방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bfa1941e6352372712debb5a5243bdd24810aac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="d01a7-102">방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="d01a7-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="d01a7-103">데이터 컬렉션의 보기를 만드는 방법을 보여 주는이 예제 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="d01a7-104">그룹화, 정렬, 필터링의 기능 및 현재 항목의 개념에 대 한 뷰를 통해.</span><span class="sxs-lookup"><span data-stu-id="d01a7-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d01a7-105">예</span><span class="sxs-lookup"><span data-stu-id="d01a7-105">Example</span></span>  
 <span data-ttu-id="d01a7-106">다음 예제에서는 정적 리소스 이름이 *배치* 의 컬렉션으로 정의 *위치* 각 개체 *위치* 도시 이름으로 구성 된 개체 및 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="d01a7-107">접두사 *src* 네임 스페이스에 매핑되어 있는 데이터 원본 *위치* 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="d01a7-108">접두사 *scm* 매핑됩니다 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` 및 *dat* 매핑됩니다 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`합니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="d01a7-109">다음 예에서는 도시 이름을 기준으로 정렬 되며 상태에 따라 그룹화 된 데이터 컬렉션의 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="d01a7-110">다음 예제와 같이 바인딩 소스 뷰 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="d01a7-111">에 정의 된 XML 데이터에 대 한 바인딩의 <xref:System.Windows.Data.XmlDataProvider> 리소스를 XML 이름 앞에 @ 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="d01a7-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="d01a7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d01a7-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="d01a7-113">데이터 수집의 기본 뷰 가져오기</span><span class="sxs-lookup"><span data-stu-id="d01a7-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="d01a7-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="d01a7-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="d01a7-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d01a7-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
