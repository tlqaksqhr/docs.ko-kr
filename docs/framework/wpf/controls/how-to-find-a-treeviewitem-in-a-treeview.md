---
title: '방법: TreeView에서 TreeViewItem 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: cff931312e6bc6db5ae5f26c0db80ad2f43825f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554757"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="df4e8-102">방법: TreeView에서 TreeViewItem 찾기</span><span class="sxs-lookup"><span data-stu-id="df4e8-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="df4e8-103"><xref:System.Windows.Controls.TreeView> 컨트롤은 계층적 데이터를 표시 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="df4e8-104">경우에 <xref:System.Windows.Controls.TreeView> 데이터 소스에 바인딩된는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성 신속 하 게 선택한 데이터 개체를 검색할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="df4e8-105">기본 데이터 개체를 사용 하는 일반적으로 좋습니다 하지만 프로그래밍 방식으로 포함 하는 데이터를 조작 해야 하는 경우에 따라 <xref:System.Windows.Controls.TreeViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="df4e8-106">예를 들어 프로그래밍 방식으로 확장 해야 할 수 있습니다는 <xref:System.Windows.Controls.TreeViewItem>에서 다른 항목을 선택 하거나는 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="df4e8-107">찾을 <xref:System.Windows.Controls.TreeViewItem> 각 수준의 트래버스해야 합니다, 특정 데이터 개체를 포함 하는 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="df4e8-108">항목에는 <xref:System.Windows.Controls.TreeView> 성능 향상을 위해 가상화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="df4e8-109">항목을 가상화 할 경우에도 해야 생각 한 <xref:System.Windows.Controls.TreeViewItem> 데이터 개체를 포함 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df4e8-110">예제</span><span class="sxs-lookup"><span data-stu-id="df4e8-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="df4e8-111">설명</span><span class="sxs-lookup"><span data-stu-id="df4e8-111">Description</span></span>  
 <span data-ttu-id="df4e8-112">다음 예제에서는 검색 한 <xref:System.Windows.Controls.TreeView> 특정 개체 및 개체의 포함 하는 반환에 대 한 <xref:System.Windows.Controls.TreeViewItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="df4e8-113">이 예제에서는 각 보장 <xref:System.Windows.Controls.TreeViewItem> 해당 자식 항목을 검색할 수 있도록 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="df4e8-114">이 예에서는 경우에 사용할는 <xref:System.Windows.Controls.TreeView> 가상화 된 항목을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df4e8-115">다음 예제에서는 작업에 대 한 <xref:System.Windows.Controls.TreeView>, 기본 데이터 모델 및 검색에 관계 없이 모든 <xref:System.Windows.Controls.TreeViewItem> 개체를 찾을 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="df4e8-116">다른 성능을 향상 시키는 방법은 지정된 된 개체에 대 한 데이터 모델을 검색, 추적 데이터 계층 구조 내에서 해당 위치 및 해당 찾을 <xref:System.Windows.Controls.TreeViewItem> 에 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="df4e8-117">그러나 성능이 향상 된 기술 데이터 모델에 대 한 지식이 필요 하 고 지정 된 모든에 대해 일반화 될 수 없습니다 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="df4e8-118">코드</span><span class="sxs-lookup"><span data-stu-id="df4e8-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="df4e8-119">사용자 지정에 영향을 받는 이전 코드 <xref:System.Windows.Controls.VirtualizingStackPanel> 라는 메서드를 노출 하는 `BringIntoView`합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="df4e8-120">다음 코드를 사용자 지정 정의 <xref:System.Windows.Controls.VirtualizingStackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="df4e8-121">다음 XAML 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.TreeView> 사용자 지정을 사용 하 여 <xref:System.Windows.Controls.VirtualizingStackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="df4e8-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="df4e8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df4e8-122">See Also</span></span>  
 [<span data-ttu-id="df4e8-123">TreeView의 성능 개선</span><span class="sxs-lookup"><span data-stu-id="df4e8-123">Improve the Performance of a TreeView</span></span>](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
