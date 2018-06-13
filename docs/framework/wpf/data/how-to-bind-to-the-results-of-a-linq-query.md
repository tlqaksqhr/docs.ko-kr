---
title: '방법: LINQ 쿼리 결과에 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d374bb69b6b7e022497403b9591b27e9ad7e2395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554995"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>방법: LINQ 쿼리 결과에 바인딩
이 예제에서는 LINQ 쿼리를 실행 한 다음 결과에 바인딩할 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 두 개의 목록 상자를 만듭니다. 첫 번째 목록 상자에는 세 가지 목록 항목이 포함 됩니다.  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 첫 번째 목록 상자에서 항목을 선택한 다음 이벤트 처리기를 호출 합니다. 이 예제에서는 `Tasks` 의 컬렉션인 `Task` 개체입니다. `Task` 클래스 라는 속성이 `Priority`합니다. 이 이벤트 처리기의 컬렉션을 반환 하는 LINQ 쿼리 실행 `Task` 선택한 우선 순위 값이 있어야 하 고 다음으로 설정 하는 개체는 <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 두 번째 목록 상자 이므로 해당 컬렉션에 바인딩되는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 값으로 설정 되어 `{Binding}`합니다. 결과적으로 반환된 된 컬렉션을 표시 합니다 (기반는 `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>참고 항목  
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [WPF 버전 4.5의 새로운 기능](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
