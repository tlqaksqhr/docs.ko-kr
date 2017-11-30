---
title: "방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53c40e9e3b02bdf33a073a93d28b619e399e375f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리
에 있는 항목에 대 한 이벤트를 처리 하는 <xref:System.Windows.Controls.ListView>, 각 이벤트 처리기를 추가 해야 <xref:System.Windows.Controls.ListViewItem>합니다. 때는 <xref:System.Windows.Controls.ListView> 바인딩된 데이터 원본에 명시적으로 만들면 안 한 <xref:System.Windows.Controls.ListViewItem>, 추가 하 여 각 항목에 대 한 이벤트를 처리할 수 있지만 <xref:System.Windows.EventSetter> 의 스타일으로는 <xref:System.Windows.Controls.ListViewItem>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터 바인딩된 <xref:System.Windows.Controls.ListView> 만듭니다는 <xref:System.Windows.Style> 각 이벤트 처리기를 추가 하려면 <xref:System.Windows.Controls.ListViewItem>합니다.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 핸들의 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트입니다.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  바인딩할 가장 일반적으로 하지만 <xref:System.Windows.Controls.ListView> 데이터 원본에 각 이벤트 처리기를 추가 하는 형식을 사용할 수 있습니다 <xref:System.Windows.Controls.ListViewItem> 비 데이터 바인딩된는 <xref:System.Windows.Controls.ListView> 명시적으로 만드는 지 여부에 관계 없이 <xref:System.Windows.Controls.ListViewItem>합니다.  에 대 한 자세한 정보에 대 한 명시적 및 암시적으로 만든 <xref:System.Windows.Controls.ListViewItem> 컨트롤 참조 <xref:System.Windows.Controls.ItemsControl>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.XmlElement>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)
