---
title: "방법: 템플릿을 사용하여 GridView 사용 ListView의 스타일 지정 | Microsoft Docs"
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
  - "ListView 컨트롤, 스타일 지정"
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 템플릿을 사용하여 GridView 사용 ListView의 스타일 지정
이 예제에서는 <xref:System.Windows.DataTemplate> 및 <xref:System.Windows.Style> 개체를 사용하여 <xref:System.Windows.Controls.GridView> 뷰 모드를 사용하는 <xref:System.Windows.Controls.ListView> 컨트롤의 모양을 지정하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.GridViewColumn>의 열 머리글 모양을 사용자 지정하는 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 개체를 보여 줍니다.  
  
 [!code-xml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 다음 예제에서는 이 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 개체를 사용하여 <xref:System.Windows.Controls.GridViewColumn>의 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 속성을 설정하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성은 열 셀의 콘텐츠를 정의합니다.  
  
 [!code-xml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>은 <xref:System.Windows.Controls.GridView> 컨트롤의 열 머리글 모양을 사용자 지정할 때 사용할 수 있는 몇몇 속성 중 일부일 뿐입니다.  자세한 내용은 [GridView 열 머리글 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)를 참조하십시오.  
  
 다음 예제에서는 <xref:System.Windows.Controls.GridViewColumn>의 셀 모양을 사용자 지정하는 <xref:System.Windows.DataTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 다음 예제에서는 이 <xref:System.Windows.DataTemplate>을 사용하여 <xref:System.Windows.Controls.GridViewColumn> 셀의 콘텐츠를 정의하는 방법을 보여 줍니다.  이 템플릿은 이전 <xref:System.Windows.Controls.GridViewColumn> 예제에 사용된 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성 대신 사용됩니다.  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)