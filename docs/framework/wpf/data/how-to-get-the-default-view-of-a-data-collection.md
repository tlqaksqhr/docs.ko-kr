---
title: "방법: 데이터 수집의 기본 뷰 가져오기 | Microsoft Docs"
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
  - "만들기, 데이터 컬렉션의 뷰"
  - "데이터 바인딩(data binding), 데이터 컬렉션의 뷰 만들기"
  - "데이터 컬렉션, 뷰 만들기"
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 데이터 수집의 기본 뷰 가져오기
뷰를 사용하면 정렬, 필터링 또는 그룹화 기준에 따라 동일한 데이터 컬렉션을 다양한 방식으로 볼 수 있습니다.  모든 데이터 컬렉션에는 바인딩에서 컬렉션이 바인딩 소스로 지정된 경우 실제 바인딩 소스로 사용되는 공유 기본 뷰가 하나씩 포함되어 있습니다.  이 예제에서는 컬렉션의 기본 뷰를 가져오는 방법을 보여 줍니다.  
  
## 예제  
 뷰를 만들려면 컬렉션에 대한 개체 참조가 필요합니다.  이 데이터 개체는 사용자 고유의 코드 숨김 개체를 참조하거나, 데이터 컨텍스트를 가져오거나, 데이터 소스의 속성을 가져오거나, 바인딩의 속성을 가져와서 얻을 수 있습니다.  이 예제에서는 데이터 개체의 <xref:System.Windows.FrameworkElement.DataContext%2A>를 가져와서 이를 사용하여 이 컬렉션의 기본 컬렉션 뷰를 직접 얻는 방법을 보여 줍니다.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 이 예제에서 루트 요소는 <xref:System.Windows.Controls.StackPanel>입니다.  <xref:System.Windows.FrameworkElement.DataContext%2A>는 *Order* 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601>인 데이터 공급자를 참조하는 *myDataSource*로 설정됩니다.  
  
 [!code-xml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 또는 <xref:System.Windows.Data.CollectionViewSource> 클래스를 사용하여 고유의 컬렉션 뷰를 인스턴스화한 다음 여기에 바인딩할 수도 있습니다.  이 컬렉션 뷰는 뷰에 직접 바인딩된 컨트롤 간에만 공유됩니다.  예제를 보려면 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)의 뷰를 만드는 방법 단원을 참조하십시오.  
  
 컬렉션 뷰에서 제공하는 기능의 예제를 보려면 [뷰의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md) 및 [데이터 수집 뷰의 개체 탐색](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조하십시오.  
  
## 참고 항목  
 [XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)