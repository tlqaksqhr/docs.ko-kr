---
title: "방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ListView 컨트롤, MouseDoubleClick 이벤트"
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리
<xref:System.Windows.Controls.ListView>의 항목에 대한 이벤트를 처리하려면 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가해야 합니다.  <xref:System.Windows.Controls.ListView>가 데이터 소스에 바인딩되는 경우에는 <xref:System.Windows.Controls.ListViewItem>을 명시적으로 작성할 필요가 없지만 <xref:System.Windows.EventSetter>를 <xref:System.Windows.Controls.ListViewItem>의 스타일에 추가하여 각 항목에 대한 이벤트를 처리할 수 있습니다.  
  
## 예제  
 다음 예제에서는 데이터 바인딩된 <xref:System.Windows.Controls.ListView>를 만들고 <xref:System.Windows.Style>을 만들어 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가합니다.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트를 처리합니다.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ListView>를 데이터 소스에 바인딩하는 방식이 가장 일반적이지만 <xref:System.Windows.Controls.ListViewItem>을 명시적으로 만드는지 여부에 관계없이 스타일을 사용하여 데이터 바인딩되지 않은 <xref:System.Windows.Controls.ListView>의 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가할 수 있습니다.  명시적 및 암시적으로 만든 <xref:System.Windows.Controls.ListViewItem> 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.ItemsControl>을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Xml.XmlElement>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)