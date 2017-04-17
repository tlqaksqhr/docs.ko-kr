---
title: "방법: GridView를 구현하는 ListView의 항목 그룹화 | Microsoft Docs"
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
  - "GridView 컨트롤, 항목 그룹화"
  - "GridView를 구현하는 ListView의 항목 그룹화"
  - "ListView 컨트롤, GridView로 항목 그룹화"
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: GridView를 구현하는 ListView의 항목 그룹화
이 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 <xref:System.Windows.Controls.GridView> 뷰 모드에 항목의 그룹을 표시하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.ListView>에 항목 그룹을 표시하려면 <xref:System.Windows.Data.CollectionViewSource>를 정의해야 합니다.  다음 예제에서는 `Catalog` 데이터 필드의 값에 따라 데이터 항목을 그룹화하는 <xref:System.Windows.Data.CollectionViewSource>를 보여 줍니다.  
  
 [!code-xml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ListView>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 이전 예제에서 정의한 <xref:System.Windows.Data.CollectionViewSource>로 설정합니다.  예제에서는 또한 <xref:System.Windows.Controls.Expander> 컨트롤을 구현하는 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>을 정의합니다.  
  
 [!code-xml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)