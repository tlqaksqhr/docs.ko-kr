---
title: "방법: 뷰의 데이터 정렬 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 뷰에서 데이터 그룹화"
  - "데이터 바인딩(data binding), 뷰에서 데이터 정렬"
  - "뷰에서 데이터 그룹화"
  - "뷰에서 데이터 정렬"
  - "뷰, 데이터 그룹화"
  - "뷰, 데이터 정렬"
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 뷰의 데이터 정렬
이 예제에서는 뷰에서 데이터를 정렬하는 방법을 설명합니다.  
  
## 예제  
 다음 예제에서는 간단한 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button>을 만듭니다.  
  
 [!code-xml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기에는 <xref:System.Windows.Controls.ListBox>의 항목을 내림차순으로 정렬하는 논리가 포함되어 있습니다.  이런 식으로 항목을 <xref:System.Windows.Controls.ListBox>에 추가하면 항목이 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemCollection>에 추가되며 <xref:System.Windows.Controls.ItemCollection>이 <xref:System.Windows.Data.CollectionView> 클래스에서 파생되기 때문에 이 작업을 수행할 수 있습니다.  <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 사용하여 <xref:System.Windows.Controls.ListBox>를 컬렉션에 바인딩하는 경우 동일한 기법을 사용하여 정렬할 수 있습니다.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 뷰 개체에 대한 참조가 있는 경우에 한해서 동일한 기법을 사용하여 다른 컬렉션 뷰의 콘텐츠를 정렬할 수 있습니다.  뷰를 가져오는 방법에 대한 예제를 보려면 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)를 참조하십시오.  다른 예제를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조하십시오.  뷰에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)에서 컬렉션에 바인딩을 참조하십시오.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 정렬 논리를 적용하는 방법에 대한 예제를 보려면 [XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>   
 [머리글을 클릭할 때 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)