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
ms.openlocfilehash: fdc478d62ca97f8f61c26fbbf1ee6c3ea8b4e189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 및 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성에 대 한 값을 지정 하는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 <xref:System.Windows.Controls.TreeView>합니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 지정 하는 방법을 제공는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 에 대 한는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 에 <xref:System.Windows.Controls.TreeView>합니다. <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 개체를 나타내며는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션 및 <xref:System.Windows.Controls.TreeView> 선택한 항목의 단일 속성의 값을 표시 합니다. <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성의 값을 확인 하는 데 사용 되는 속성에 대 한 경로 지정 된 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성입니다. 이 항목의 예제에서는이 개념을 설명 합니다.  
  
 다음 예제와 <xref:System.Windows.Data.XmlDataProvider> 직원 정보를 포함 하는 합니다.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 다음 예제에서는 정의 <xref:System.Windows.HierarchicalDataTemplate> 표시 하는 `EmployeeName` 및 `EmployeeWorkDay` 의 `Employee`합니다. <xref:System.Windows.HierarchicalDataTemplate> 지정 하지 않습니다는 `EmployeeNumber` 서식 파일의 일부로 합니다.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.TreeView> 사용 하 여 이전에 정의 된 <xref:System.Windows.HierarchicalDataTemplate> 로 설정 하 고는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성을는 `EmployeeNumber`합니다. 선택 하는 경우는 `EmployeeName` 에 <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에서 반환 된 `EmployeeInfo` 선택한에 해당 하는 데이터 항목 `EmployeeName`합니다. 그러나 때문에 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 이 <xref:System.Windows.Controls.TreeView> 로 설정 된 `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 로 설정 되는 `EmployeeNumber`합니다.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [TreeView 개요](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
