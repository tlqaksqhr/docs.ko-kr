---
title: '방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 6ff5ad4825bd9f683d895341dd084c00f68aa27b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작
메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ColumnDefinitionCollection> 및 <xref:System.Windows.Controls.RowDefinitionCollection> 추가, 지우기 또는 행 또는 열의 내용을 계산과 같은 동작을 수행 하는 클래스가 있습니다. 예를 들어, <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, 또는 <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> 에 포함 된 항목을 <xref:System.Windows.Controls.ColumnDefinition> 또는 <xref:System.Windows.Controls.RowDefinition>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Controls.Grid> 인 요소는 <xref:System.Windows.FrameworkElement.Name%2A> 의 `grid1`합니다. <xref:System.Windows.Controls.Grid> 포함 한 <xref:System.Windows.Controls.StackPanel> 를 보유 하는 <xref:System.Windows.Controls.Button> 다른 수집 방법으로 제어 각 요소입니다. 클릭는 <xref:System.Windows.Controls.Button>, 코드 숨김 파일에서 메서드 호출을 활성화 합니다.  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 일련의 각에 해당 하는 사용자 지정 메서드를 정의 하는이 예제는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일입니다. 열과 행의 수를 변경할 수는 <xref:System.Windows.Controls.Grid> 에서 여러 가지 방법으로, 포함 또는 추가 하 고, 행 및 열을 제거 하 고, 행과 열의 총 수를 계산 합니다. 방지 하기 위해 <xref:System.ArgumentOutOfRangeException> 및 <xref:System.ArgumentException> 예외를 오류 검사 기능을 사용할 수 있는 <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> 메서드를 제공 합니다.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>
