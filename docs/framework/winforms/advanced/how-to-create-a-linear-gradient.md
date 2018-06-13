---
title: '방법: 선형 그라데이션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 9eeedf1ef92bdf6e5e2724eeca5060765b0778f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522462"
---
# <a name="how-to-create-a-linear-gradient"></a>방법: 선형 그라데이션 만들기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 가로, 세로, 및 대각선 선형 그라데이션을 제공합니다. 기본적으로 선형 그라데이션 색 균일 하 게 변경합니다. 그러나 균일 하지 않은 방식으로 색이 변경 되도록 선형 그라데이션을 사용자 지정할 수 있습니다.  
  
 다음 예제에서는 줄, 타원 및 사각형 가로 선형 그라데이션 브러시로 채웁니다.  
  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 네 개의 인수를 받는 생성자: 두 점과 두 가지 색입니다. 첫 번째 지점 (0, 10) 첫 번째 색 (빨강)으로 연결 되며 두 번째 색 (파랑)와 연결 된 두 번째 점 (200, 10). 와 마찬가지로, 그린 선 (0, 10)에 (200, 10) 빨강에서 파랑 점진적으로 변경 합니다.  
  
 점 (50, 10) 및 (200, 10)에서 10 개 기준 중요 하지 않습니다. 중요 한 것은 두 지점 동일한 두 번째 좌표 있는지-으로 연결 되도록에 그려집니다. 타원 및 사각형에서에서 변경할 수도 점진적으로 빨강을 200으로 0에서 가로 좌표 면 파란색입니다.  
  
 다음은 줄, 타원 및 사각형입니다. 색 그라데이션이 반복 됨 자체 200 이외의 증가 하면 가로 좌표 참고 합니다.  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>가로 선형 그라데이션을 사용 하려면  
  
-   불투명 빨강 및 불투명 파란색에서 세 번째와 네 번째 인수로 각각 전달 합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 앞의 예제에서 200에서 가로 좌표 0 가로 좌표에서 이동 색상 구성 선형으로 변경 합니다. 예를 들어 첫 번째 좌표가 0과 200 사이의 중간 지점 0에서 255 사이의 중간에 있는 파란색 구성 요소를 갖습니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 다른 색이 변하는 그라데이션의 한쪽 가장자리에서 방식을 조정할 수 있습니다. 검정에서 다음 표에 따라 빨강으로 변경 하는 그라데이션 브러시를 만들려고 한다고 가정 합니다.  
  
|가로 좌표|RGB 구성 요소|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 가로 좌표는 0에서 200 하는 방법의 20%만 때 빨강 구성 농도가 절반은 note 합니다.  
  
 다음 예에서는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> 속성은 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 세 가지 상대 농도 세 가지 상대 위치를 연결할 개체입니다. 앞의 표에서 같이 0.5 상대 강도 0.2의 상대 위치와 연결 됩니다. 코드는 타원 및 사각형 그라데이션 브러시를 채웁니다.  
  
 다음은 결과 타원 및 사각형입니다.  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>선형 그라데이션 사용자 지정 하려면  
  
-   불투명 한 검정색 및 불투명 빨간색 세 번째와 네 번째 인수로 각각 전달 합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 이전 예제에서 그라데이션 가로; 되었습니다. 즉, 색 가로 줄 이동 하면 점진적으로 변경 합니다. 세로 그라데이션 및 대각선 그라데이션을 정의할 수 있습니다.  
  
 에 점 (0, 0) 및 (200, 100)를 전달 하는 다음 예제는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자입니다. 파란색 연관 (0, 0)와 연결 되는 녹색 (200, 100). 선형 그라데이션 브러시로 (펜 굵기 10)이 있는 선 및 타원 채워집니다.  
  
 다음 그림에는 줄과 타원 보여 줍니다. 참고는 타원 변경 내용에서 색 점진적으로 하나를 따라 이동 하면 줄 하는 통과 한 줄에 병렬 (0, 0) 및 (200, 100).  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>대각선 선형 그라데이션을 만들려면  
  
-   불투명 파란색 아이콘과 불투명 녹색 세 번째와 네 번째 인수로 각각 전달 합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>참고 항목  
 [그라데이션 브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
