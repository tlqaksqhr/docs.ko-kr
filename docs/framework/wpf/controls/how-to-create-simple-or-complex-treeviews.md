---
title: '방법: 간단하거나 복잡한 TreeView 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 54e9218ea1460a0c29d8b9d7b9c740c18ac7ab24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553000"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="bb609-102">방법: 간단하거나 복잡한 TreeView 만들기</span><span class="sxs-lookup"><span data-stu-id="bb609-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="bb609-103">이 예제에는 간단 하거나 복잡 한를 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.TreeView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="bb609-104">A <xref:System.Windows.Controls.TreeView> 계층 구조로 구성 됩니다 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 포함할 수 있는 간단한 텍스트 문자열와 더 복잡 한 콘텐츠를 같은 <xref:System.Windows.Controls.Button> 컨트롤 또는 <xref:System.Windows.Controls.StackPanel> 포함 된 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="bb609-105">명시적으로 정의할 수는 <xref:System.Windows.Controls.TreeView> 콘텐츠 또는 데이터 원본에서 콘텐츠를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="bb609-106">이 항목에서는 이러한 개념의 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb609-107">예제</span><span class="sxs-lookup"><span data-stu-id="bb609-107">Example</span></span>  
 <span data-ttu-id="bb609-108"><xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성은 <xref:System.Windows.Controls.TreeViewItem> 콘텐츠를 포함 하는 <xref:System.Windows.Controls.TreeView> 해당 항목에 대해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="bb609-109">A <xref:System.Windows.Controls.TreeViewItem> 수도 <xref:System.Windows.Controls.TreeViewItem> 자식 요소와 컨트롤 사용 하 여 이러한 하위 요소를 정의할 수는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="bb609-110">다음 예제에서는 명시적으로 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.TreeViewItem> 설정 하 여 콘텐츠는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성을 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="bb609-111">다음 예제에서는의 자식 요소를 정의 하는 방법을 보여는 <xref:System.Windows.Controls.TreeViewItem> 정의 하 여 <xref:System.Windows.Controls.ItemsControl.Items%2A> 있는 <xref:System.Windows.Controls.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="bb609-112">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TreeView> 위치는 <xref:System.Windows.Data.XmlDataProvider> 제공 <xref:System.Windows.Controls.TreeViewItem> 콘텐츠 및 <xref:System.Windows.HierarchicalDataTemplate> 콘텐츠의 모양을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="bb609-113">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TreeView> 여기서는 <xref:System.Windows.Controls.TreeViewItem> 넣는 <xref:System.Windows.Controls.DockPanel> 내용을 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="bb609-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="bb609-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb609-114">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="bb609-115">TreeView 개요</span><span class="sxs-lookup"><span data-stu-id="bb609-115">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [<span data-ttu-id="bb609-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="bb609-116">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
