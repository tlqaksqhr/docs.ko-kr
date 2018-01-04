---
title: "방법: ListView에 있는 열의 가로 맞춤 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="6db16-102">방법: ListView에 있는 열의 가로 맞춤 변경</span><span class="sxs-lookup"><span data-stu-id="6db16-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="6db16-103">기본적으로에서 각 열의 내용은 <xref:System.Windows.Controls.ListViewItem> 는 왼쪽 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="6db16-104">제공 하 여 각 열의 맞춤을 변경할 수는 <xref:System.Windows.DataTemplate> 설정는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 내에서 요소의 속성에는 <xref:System.Windows.DataTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="6db16-105">이 항목에서는 방법을 <xref:System.Windows.Controls.ListView> 맞춤에서 한 열을 변경 하는 방법 및 기본적으로 해당 내용을 맞춥니다.는 <xref:System.Windows.Controls.ListView>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db16-106">예</span><span class="sxs-lookup"><span data-stu-id="6db16-106">Example</span></span>  
 <span data-ttu-id="6db16-107">다음 예제에서는 데이터에는 `Title` 및 `ISBN` 열은 왼쪽 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="6db16-108">맞춤을 변경 하려면는 `ISBN` 열을 지정 해야 하는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 각 속성 <xref:System.Windows.Controls.ListViewItem> 은 <xref:System.Windows.HorizontalAlignment.Stretch>되도록 각 요소 <xref:System.Windows.Controls.ListViewItem> 에 걸쳐 있을 수 또는 각 열의 전체 너비를 따라 위치할 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="6db16-109">때문에 <xref:System.Windows.Controls.ListView> 바인딩된 데이터 소스를 설정 하는 스타일을 만들어야 할는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="6db16-110">사용 해야 하는 다음으로 <xref:System.Windows.DataTemplate> 사용 하는 대신 내용을 표시 하는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="6db16-111">표시 하는 `ISBN` 각 서식 파일의는 <xref:System.Windows.DataTemplate> 만 포함 될 수 있습니다는 <xref:System.Windows.Controls.TextBlock> 있는 해당 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성이로 설정 <xref:System.Windows.HorizontalAlignment.Right>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="6db16-112">스타일을 정의 하는 다음 예제에서는 및 <xref:System.Windows.DataTemplate> 확인 하는 데 필요한는 `ISBN` 열을 오른쪽 맞춤 하 고 변경 내용을 <xref:System.Windows.Controls.GridViewColumn> 참조에는 <xref:System.Windows.DataTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db16-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6db16-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6db16-113">See Also</span></span>  
 [<span data-ttu-id="6db16-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="6db16-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6db16-115">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="6db16-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="6db16-116">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="6db16-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="6db16-117">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="6db16-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
