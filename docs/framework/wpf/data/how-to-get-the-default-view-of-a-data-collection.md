---
title: "방법: 데이터 수집의 기본 뷰 가져오기"
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
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>방법: 데이터 수집의 기본 뷰 가져오기
뷰는 동일한 데이터 수집을 정렬, 필터링 또는 그룹화 기준에 따라 다양 한 방법으로 볼 수 있도록 합니다. 모든 컬렉션에 바인딩 원본으로 컬렉션을 지정 하는 경우 실제 바인딩 원본으로 사용 되는 하나의 공유 기본 보기. 이 예제에는 컬렉션의 기본 보기를 가져오는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 보기를 만들려면 컬렉션에 대 한 개체 참조가 필요 합니다. 데이터 원본의 속성을 가져오거나 또는 바인딩 속성을 가져오거나 데이터 컨텍스트를 가져와 사용자 고유의 코드 숨김 개체를 참조 하 여이 데이터 개체를 가져올 수 있습니다. 가져오는 방법을 보여 주는이 예제는 <xref:System.Windows.FrameworkElement.DataContext%2A> 이 컬렉션에 대 한 보기를 직접 기본 컬렉션을 얻기 위해 데이터 개체 및 사용 합니다.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 이 예제에서는 루트 요소는 한 <xref:System.Windows.Controls.StackPanel>합니다. <xref:System.Windows.FrameworkElement.DataContext%2A> 로 설정 된 *myDataSource*, 데이터 공급자를 참조 하는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 *순서* 개체입니다.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 또는 인스턴스화할 수를 사용 하 여 사용자 고유의 컬렉션 뷰를 바인딩하는 <xref:System.Windows.Data.CollectionViewSource> 클래스입니다. 이 컬렉션 뷰에 직접 바인딩된 컨트롤에서만 공유 됩니다. 예를 들어 뷰 섹션 만들기 하는 방법을 참조 하십시오.는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
 컬렉션 보기에서 제공 하는 기능의 예 참조 [보기의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [보기에서 필터 데이터](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), 및 [데이터 수집 뷰의the의개체를통해이동](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>참고 항목  
 [XAML 데이터 정렬 및 그룹화](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
