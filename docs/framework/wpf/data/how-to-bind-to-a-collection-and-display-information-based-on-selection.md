---
title: '방법: 선택에 따라 수집 및 표시 정보에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 154f4b9b6024d064e73d64c44e2398a5da47052c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557411"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>방법: 선택에 따라 수집 및 표시 정보에 바인딩
데이터 바인딩된 있는 간단한 마스터-세부 시나리오에서 <xref:System.Windows.Controls.ItemsControl> 와 같은 <xref:System.Windows.Controls.ListBox>합니다. 선택한 항목에 대 한 자세한 정보를 표시할 사용자 선택에 따라 있습니다. 이 예제에서는이 시나리오를 구현 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `People` 는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `Person` 클래스입니다. 이 `Person` 세 가지 속성을 포함 하는 클래스: `FirstName`, `LastName`, 및 `HomeTown`, 유형의 `string`합니다.  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl> 에서는 다음과 같은 <xref:System.Windows.DataTemplate> 정의 하는 방법을의 정보는 `Person` 표시 됩니다.  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 다음은 예제에서 생성의 스크린샷입니다. <xref:System.Windows.Controls.ContentControl> 선택 하는 사용자의 다른 속성을 보여 줍니다.  
  
 ![컬렉션에 바인딩](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 이 예에서 유념 해야 할 두 가지 사항은 다음과 같습니다.  
  
1.  <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl> 동일한 소스에 바인딩합니다. <xref:System.Windows.Data.Binding.Path%2A> 전체 컬렉션 개체를 두 컨트롤이 모두 바인딩하는 때문에 두 바인딩은 모두의 속성을 지정 하지 않으면 합니다.  
  
2.  설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true` 이 수행 합니다. 이 속성을 설정 하면 선택한 항목은 항상으로 설정 된다는 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>합니다. 또는 경우는 <xref:System.Windows.Controls.ListBox> 에서 데이터를 가져오는 <xref:System.Windows.Data.CollectionViewSource>, 선택 및 통화 자동으로 동기화 합니다.  
  
 `Person` 재정의 `ToString` 메서드는 다음과 같이 합니다. 기본적으로는 <xref:System.Windows.Controls.ListBox> 호출 `ToString` 바인딩된 컬렉션에 있는 각 개체의 문자열 표현을 표시 합니다. 바로 이러한 이유로 각 `Person` 에 이름으로 표시는 <xref:System.Windows.Controls.ListBox>합니다.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>참고 항목  
 [계층적 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [계층적 XML 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
