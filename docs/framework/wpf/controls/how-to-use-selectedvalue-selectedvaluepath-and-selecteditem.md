---
title: "방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6355ed45d7422735d1dac1e1419990e1c5bd120
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="73fa7-102">방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용</span><span class="sxs-lookup"><span data-stu-id="73fa7-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="73fa7-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 및 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성에 대 한 값을 지정 하는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73fa7-104">예</span><span class="sxs-lookup"><span data-stu-id="73fa7-104">Example</span></span>  
 <span data-ttu-id="73fa7-105"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 지정 하는 방법을 제공는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 에 대 한는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 에 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="73fa7-106"><xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 개체를 나타내며는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션 및 <xref:System.Windows.Controls.TreeView> 선택한 항목의 단일 속성의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="73fa7-107"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성의 값을 확인 하는 데 사용 되는 속성에 대 한 경로 지정 된 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="73fa7-108">이 항목의 예제에서는이 개념을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="73fa7-109">다음 예제와 <xref:System.Windows.Data.XmlDataProvider> 직원 정보를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="73fa7-110">다음 예제에서는 정의 <xref:System.Windows.HierarchicalDataTemplate> 표시 하는 `EmployeeName` 및 `EmployeeWorkDay` 의 `Employee`합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="73fa7-111"><xref:System.Windows.HierarchicalDataTemplate> 지정 하지 않습니다는 `EmployeeNumber` 서식 파일의 일부로 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="73fa7-112">다음 예제에서는 한 <xref:System.Windows.Controls.TreeView> 사용 하 여 이전에 정의 된 <xref:System.Windows.HierarchicalDataTemplate> 로 설정 하 고는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성을는 `EmployeeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="73fa7-113">선택 하는 경우는 `EmployeeName` 에 <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에서 반환 된 `EmployeeInfo` 선택한에 해당 하는 데이터 항목 `EmployeeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="73fa7-114">그러나 때문에 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 이 <xref:System.Windows.Controls.TreeView> 로 설정 된 `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 로 설정 되는 `EmployeeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="73fa7-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="73fa7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73fa7-115">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="73fa7-116">TreeView 개요</span><span class="sxs-lookup"><span data-stu-id="73fa7-116">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [<span data-ttu-id="73fa7-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="73fa7-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
