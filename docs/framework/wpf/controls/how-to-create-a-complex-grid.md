---
title: '방법: 복잡한 모눈 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-complex-grid"></a>방법: 복잡한 모눈 만들기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Grid> 월별 달력 처럼 보이는 레이아웃을 만들 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 8 개의 행과 열이 8 개를 사용 하 여 정의 <xref:System.Windows.Controls.RowDefinition> 및 <xref:System.Windows.Controls.ColumnDefinition> 클래스입니다. 사용 하 여는 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 와 함께 연결 된 속성을 <xref:System.Windows.Shapes.Rectangle> 요소에는 다양 한 열과 행의 배경을 채웁니다. 각 셀에 요소가 둘 이상 있을 수 있으므로이 디자인은 가능한 한 <xref:System.Windows.Controls.Grid>, 원칙 차이 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Documents.Table>합니다.  
  
 이 예에서는 사용 하는 세로 그라데이션을 <xref:System.Windows.Shapes.Shape.Fill%2A> 열과 행이 시각적 표현 및 달력의 가독성을 높이기 위해. 스타일의 <xref:System.Windows.Controls.TextBlock> 요소는 날짜와 요일을 나타냅니다. <xref:System.Windows.Controls.TextBlock> 요소를 사용 하 여 배치 셀 내에서 반드시는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 및 응용 프로그램에 대 한 스타일 내에 정의 된 맞춤 속성입니다.  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)
