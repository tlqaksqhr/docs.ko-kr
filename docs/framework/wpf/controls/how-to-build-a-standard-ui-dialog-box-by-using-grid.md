---
title: '방법: Grid를 사용하여 표준 UI 대화 상자 빌드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551884"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>방법: Grid를 사용하여 표준 UI 대화 상자 빌드
이 예제에서는 한 표준을 만들 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 대화 상자를 사용 하 여는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 같은 대화 상자가 **실행** 대화 상자에는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 운영 체제입니다.  
  
 이 예에서는 만듭니다는 <xref:System.Windows.Controls.Grid> 사용 하 여는 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 5 개의 열과 4 개의 행을 정의 하는 클래스입니다.  
  
 이 예제에서는 다음 추가 하 고 배치는 <xref:System.Windows.Controls.Image>, `RunIcon.png`대화 상자에서 발견 되는 이미지를 나타내기 위해. 이미지가 첫 번째 열과 행에 배치 되는 <xref:System.Windows.Controls.Grid> (왼쪽 위 모퉁이).  
  
 이 예제에서는 추가 하는 다음으로 <xref:System.Windows.Controls.TextBlock> 첫 번째 행의 나머지 열을 포함 하는 첫 번째 열에는 요소입니다. 다른 추가 <xref:System.Windows.Controls.TextBlock> 두 번째 행을 나타내는 첫 번째 열에는 요소는 **열려** 입력란. A <xref:System.Windows.Controls.TextBlock> 다음과 데이터 입력 영역을 나타냅니다.  
  
 이 예에서는 세 개의 추가 마지막으로, <xref:System.Windows.Controls.Button> 은 마지막 행을 나타내는 요소는 **확인**, **취소**, 및 **찾아보기** 이벤트입니다.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
