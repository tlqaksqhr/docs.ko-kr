---
title: '방법: 뷰에서 데이터 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 55ec68e8918c9f7fbc9d3ac0062926cc03cb5e10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-filter-data-in-a-view"></a>방법: 뷰에서 데이터 필터링
이 예에서는 뷰에서 데이터를 필터링 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 필터를 만들려면 필터링 논리를 제공 하는 메서드를 정의 합니다. 메서드는 콜백으로 사용 되 고 형식의 매개 변수를 허용 `object`합니다. 모든을 반환 하는 다음 메서드는 `Order` 개체와 `filled` 속성을 필터링 하는 개체의 나머지 부분 "아니요"로 설정 합니다.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 다음 예제에 나와 있는 것 처럼 필터를 적용할 수 있습니다. 이 예제에서는 `myCollectionView` 는 <xref:System.Windows.Data.ListCollectionView> 개체입니다.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 필터링을 실행 취소 하려면 설정할 수 있습니다는 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 만들거나 보기가 하는 방법에 대 한 정보를 참조 하십시오. [데이터 컬렉션의 기본 보기 가져올](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)합니다. 전체 예제를 참조 하십시오. [정렬 및 항목 보기 샘플의 필터링](http://go.microsoft.com/fwlink/?LinkID=160040)합니다.  
  
 보기 개체에서 제공 하는 경우는 <xref:System.Windows.Data.CollectionViewSource> 개체에 대 한 이벤트 처리기를 설정 하 여 필터링 논리를 적용할는 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트입니다. 다음 예에서 `listingDataView` 의 인스턴스가 <xref:System.Windows.Data.CollectionViewSource>합니다.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 다음 예의 구현을 보여 줍니다. `ShowOnlyBargainsFilter` 필터 이벤트 처리기입니다. 이 이벤트 처리기를 사용 하 여는 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 속성을 필터링 할 `AuctionItem` 있는 개체는 `CurrentPrice` $25 이상.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [뷰의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
