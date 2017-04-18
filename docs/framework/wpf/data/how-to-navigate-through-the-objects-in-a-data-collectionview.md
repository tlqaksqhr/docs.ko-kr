---
title: "방법: 데이터 수집 뷰의 개체 탐색 | Microsoft Docs"
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
  - "CollectionView, 개체 탐색"
  - "데이터 바인딩(data binding), 데이터 CollectionView의 개체 탐색"
  - "데이터 CollectionView의 개체 탐색"
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 데이터 수집 뷰의 개체 탐색
뷰를 사용하면 정렬, 필터링 또는 그룹화에 따라 다양한 방식으로 같은 데이터 수집을 볼 수 있습니다.  또한 뷰는 현재 레코드 포인터 개념을 제공하고 포인터를 이동할 수 있게 해줍니다.  이 예제에서는 <xref:System.Windows.Data.CollectionView> 클래스에서 제공하는 기능을 사용하여 현재 개체를 가져오는 방법 및 데이터 수집의 개체를 탐색하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 `myCollectionView`는 바인딩된 컬렉션을 보여 주는 <xref:System.Windows.Data.CollectionView> 개체입니다.  
  
 다음 예제에서 `OnButton`은 `Previous`의 이벤트 처리기 및 응용 프로그램의 `Next` 단추이며 이러한 단추를 사용하면 사용자가 데이터 수집을 탐색할 수 있습니다.  <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 및 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 속성은 현재 레코드 포인터가 목록의 시작에 있는지 아니면 끝에 있는지 여부를 보고하여 경우에 따라 적절하게 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 및 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>를 호출할 수 있도록 합니다.  
  
 뷰의 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 속성은 수집에서 현재 순서 항목을 반환하기 위해 `Order`로 캐스팅됩니다.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [뷰의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)