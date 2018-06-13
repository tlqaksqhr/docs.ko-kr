---
title: '방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: f9a1e91051a7f86bf78cb08a3d58e57541ae4987
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553853"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="34c66-102">방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="34c66-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="34c66-103">에 있는 항목에 대 한 이벤트를 처리 하는 <xref:System.Windows.Controls.ListView>, 각 이벤트 처리기를 추가 해야 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="34c66-104">때는 <xref:System.Windows.Controls.ListView> 바인딩된 데이터 원본에 명시적으로 만들면 안 한 <xref:System.Windows.Controls.ListViewItem>, 추가 하 여 각 항목에 대 한 이벤트를 처리할 수 있지만 <xref:System.Windows.EventSetter> 의 스타일으로는 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c66-105">예제</span><span class="sxs-lookup"><span data-stu-id="34c66-105">Example</span></span>  
 <span data-ttu-id="34c66-106">다음 예제에서는 데이터 바인딩된 <xref:System.Windows.Controls.ListView> 만듭니다는 <xref:System.Windows.Style> 각 이벤트 처리기를 추가 하려면 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="34c66-107">다음 예제에서는 핸들의 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="34c66-108">바인딩할 가장 일반적으로 하지만 <xref:System.Windows.Controls.ListView> 데이터 원본에 각 이벤트 처리기를 추가 하는 형식을 사용할 수 있습니다 <xref:System.Windows.Controls.ListViewItem> 비 데이터 바인딩된는 <xref:System.Windows.Controls.ListView> 명시적으로 만드는 지 여부에 관계 없이 <xref:System.Windows.Controls.ListViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="34c66-109">에 대 한 자세한 정보에 대 한 명시적 및 암시적으로 만든 <xref:System.Windows.Controls.ListViewItem> 컨트롤 참조 <xref:System.Windows.Controls.ItemsControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="34c66-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c66-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34c66-110">See Also</span></span>  
 <xref:System.Xml.XmlElement>  
 [<span data-ttu-id="34c66-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="34c66-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="34c66-112">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="34c66-112">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="34c66-113">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="34c66-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="34c66-114">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="34c66-114">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
