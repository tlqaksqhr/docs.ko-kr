---
title: "방법: 뷰에서 데이터 필터링 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 뷰의 데이터 필터링"
  - "뷰의 데이터 필터링"
  - "뷰, 데이터 필터링"
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 뷰에서 데이터 필터링
이 예제에서는 뷰에서 데이터를 필터링하는 방법을 보여 줍니다.  
  
## 예제  
 필터를 만들려면 필터링 논리를 제공하는 메서드를 정의합니다.  메서드는 콜백으로 사용되고 `object` 형식의 매개 변수를 사용합니다.  다음 메서드는 `filled` 속성이 "No"로 설정된 모든 `Order` 개체를 반환하고 나머지 개체는 필터링합니다.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 그리고 나서 다음 예제에 표시된 대로 필터를 적용할 수 있습니다.  이 예제에서 `myCollectionView`는 <xref:System.Windows.Data.ListCollectionView> 개체입니다.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 필터링을 실행 취소하기 위해 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 `null`로 설정할 수 있습니다.  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 뷰를 만들거나 가져오는 방법에 대한 자세한 내용은 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)를 참조하십시오.  전체 예제를 보려면 [Sorting and Filtering Items in a View 샘플](http://go.microsoft.com/fwlink/?LinkID=160040)을 참조하십시오.  
  
 뷰 개체가 <xref:System.Windows.Data.CollectionViewSource> 개체에서 오는 경우 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트에 대해 이벤트 처리기를 설정하여 필터링 논리를 적용합니다.  다음 예제에서 `listingDataView`는 <xref:System.Windows.Data.CollectionViewSource>의 인스턴스입니다.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 다음 예제에서는 `ShowOnlyBargainsFilter` 필터 이벤트 처리기 예제의 구현을 보여 줍니다.  이 이벤트 처리기는 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 속성을 사용하여 `CurrentPrice`가 $25 이상인 `AuctionItem` 개체를 필터링합니다.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## 참고 항목  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>   
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [뷰의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)