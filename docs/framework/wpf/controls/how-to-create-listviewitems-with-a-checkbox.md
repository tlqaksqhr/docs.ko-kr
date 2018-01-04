---
title: "방법: CheckBox를 사용하여 ListViewItems 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be87183efd8101233bd5cbda49d556d09802b630
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>방법: CheckBox를 사용하여 ListViewItems 만들기
열을 표시 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.CheckBox> 컨트롤에 <xref:System.Windows.Controls.ListView> 컨트롤을 사용 하는 <xref:System.Windows.Controls.GridView>합니다.  
  
## <a name="example"></a>예  
 포함 된 열을 만들려면 <xref:System.Windows.Controls.CheckBox> 컨트롤에 <xref:System.Windows.Controls.ListView>, 만들는 <xref:System.Windows.DataTemplate> 를 포함 하는 <xref:System.Windows.Controls.CheckBox>합니다. 다음 설정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 의 <xref:System.Windows.Controls.GridViewColumn> 에 <xref:System.Windows.DataTemplate>합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.DataTemplate> 를 포함 하는 <xref:System.Windows.Controls.CheckBox>합니다. 예제는 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 속성의는 <xref:System.Windows.Controls.CheckBox> 에 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 속성 값이는 <xref:System.Windows.Controls.ListViewItem> 해당 항목을 포함 합니다. 따라서,는 <xref:System.Windows.Controls.ListViewItem> 를 포함 하는 <xref:System.Windows.Controls.CheckBox> 을 선택 하면는 <xref:System.Windows.Controls.CheckBox> 을 선택 합니다.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 열을 만드는 방법을 보여 주는 다음 예제 <xref:System.Windows.Controls.CheckBox> 컨트롤입니다. 예제에서는 열으로 만들려면는 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 의 속성은 <xref:System.Windows.Controls.GridViewColumn> 에 <xref:System.Windows.DataTemplate>합니다.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)
