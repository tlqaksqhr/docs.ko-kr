---
title: '방법: Grid의 자식 요소 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 62508deee1b10b4a1287360f971b3699e57d4243
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552151"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>방법: Grid의 자식 요소 위치 지정
Get를 사용 하 고에 정의 된 메서드를 설정 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Grid> 자식 요소의 위치입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 부모 <xref:System.Windows.Controls.Grid> 요소 (`grid1`)는에 세 개의 열 3 개와 행. 자식 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)에 추가 되 고 <xref:System.Windows.Controls.Grid> 0 열에서 위치 0 행을 합니다. <xref:System.Windows.Controls.Button> 요소 위치를 변경 하기 위해 호출할 수 있는 메서드를 나타냅니다는 <xref:System.Windows.Shapes.Rectangle> 내의 요소는 <xref:System.Windows.Controls.Grid>합니다. 사용자가 단추를 클릭 하면 관련된 메서드가 활성화 됩니다.  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 다음 코드 예제에서는 메서드를 처리 하는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시킵니다. 이 예제에서는 기록에 이러한 메서드 호출 <xref:System.Windows.Controls.TextBlock> 사용 관련 요소를 get 메서드를 문자열로 새 속성 값을 출력 합니다.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Grid>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
