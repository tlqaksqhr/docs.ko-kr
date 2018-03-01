---
title: "방법: ListView의 사용자 지정 뷰 모드 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e67777b5568214dff889088708db166efc6ae4dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="018c8-102">방법: ListView의 사용자 지정 뷰 모드 만들기</span><span class="sxs-lookup"><span data-stu-id="018c8-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="018c8-103">이 예제에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.ListView.View%2A> 에 대 한 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="018c8-104">예</span><span class="sxs-lookup"><span data-stu-id="018c8-104">Example</span></span>  
 <span data-ttu-id="018c8-105">사용 해야 합니다는 <xref:System.Windows.Controls.ViewBase> 클래스에 대 한 사용자 지정 보기를 만들 때의 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="018c8-106">다음 예제에서는 라고 하는 뷰 모드 `PlainView`에서 파생 되는 <xref:System.Windows.Controls.ViewBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="018c8-107">사용자 지정 보기에는 스타일을 적용 하려면 사용 하 여는 <xref:System.Windows.Style> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="018c8-108">다음 예제에서는 정의 <xref:System.Windows.Style> 에 대 한는 `PlainView` 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="018c8-109">이전 예제에서는이 스타일의 값으로 설정 된 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 속성에 대해 정의 된 `PlainView`합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="018c8-110">사용자 지정 보기 모드에서 데이터의 레이아웃을 정의 하려면 정의 <xref:System.Windows.DataTemplate> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="018c8-111">다음 예제에서는 정의 <xref:System.Windows.DataTemplate> 에 데이터를 표시를 사용할 수 있는 `PlainView` 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="018c8-112">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.ResourceKey> 에 대 한는 `PlainView` 보기 모드를 사용 하는 <xref:System.Windows.DataTemplate> 앞의 예제에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="018c8-113">A <xref:System.Windows.Controls.ListView> 컨트롤 설정 하면 사용자 지정 보기를 사용할 수는 <xref:System.Windows.Controls.ListView.View%2A> 속성을 리소스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="018c8-114">다음 예제에서는 지정 하는 방법을 보여 줍니다. `PlainView` 에 대 한 보기 모드와는 <xref:System.Windows.Controls.ListView>합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="018c8-115">전체 샘플을 참조 하십시오. [여러 보기 샘플에는 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)합니다.</span><span class="sxs-lookup"><span data-stu-id="018c8-115">For the complete sample, see [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018c8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="018c8-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="018c8-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="018c8-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="018c8-118">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="018c8-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="018c8-119">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="018c8-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
