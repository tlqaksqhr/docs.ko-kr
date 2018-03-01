---
title: "방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f8965ee524d6a5cb03a54ac07d8889ff9801440
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정
정의 하는 방법을 보여 주는이 예제 <xref:System.Windows.Style.Triggers%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 제어 되도록 때의 속성 값을는 <xref:System.Windows.Controls.ListViewItem> 변경은 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 변경 내용에 대 한 응답에서입니다.  
  
## <a name="example"></a>예  
 원하는 경우는 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 속성 변경에 대 한 응답을 변경 하려면 정의 <xref:System.Windows.Style.Triggers%2A> 에 대 한는 <xref:System.Windows.Style> 변경 합니다.  
  
 다음 예제에서는 정의 <xref:System.Windows.Trigger> 로 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 <xref:System.Windows.Media.Brushes.Blue%2A> , 코드 변경 내용에서 <xref:System.Windows.FrameworkElement.Cursor%2A> 표시 하는 <xref:System.Windows.Input.CursorType.Hand> 때는 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성 변경 `true`합니다.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 다음 예제에서는 정의 <xref:System.Windows.MultiTrigger> 로 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성은 <xref:System.Windows.Controls.ListViewItem> 를 <xref:System.Windows.Media.Brushes.Yellow%2A> 때는 <xref:System.Windows.Controls.ListViewItem> 선택한 항목은 키보드 포커스를 가진 합니다.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)
