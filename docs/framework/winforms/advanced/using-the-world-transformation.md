---
title: 전역 변형 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: 6a029e17096222d7ed80dea16f91b83a813039f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-world-transformation"></a>전역 변형 사용
월드 변형을의 속성인는 <xref:System.Drawing.Graphics> 클래스입니다. 월드 변형과 지정 하는 숫자는 저장 된 <xref:System.Drawing.Drawing2D.Matrix> 3 × 3 행렬을 나타내는 개체입니다. <xref:System.Drawing.Drawing2D.Matrix> 및 <xref:System.Drawing.Graphics> 클래스에는 여러 가지 방법을 월드 변형 매트릭스에 숫자를 설정 합니다.  
  
## <a name="different-types-of-transformations"></a>여러 종류의 변환  
 다음 예제에서 코드는 먼저 50 × 50 사각형을 만들어 원점 (0, 0)에 배치 합니다. 원점은 클라이언트 영역의 왼쪽 위 모퉁이에 있습니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 다음 코드에는 x 방향의 1.75의 비율로 사각형을 확장 하 고 사각형 y 방향의 0.5의 비율로 감소 하는 크기 조정 변환을 적용 합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 결과 사각형 x 방향의 길고 짧은 y 방향으로 원본 보다입니다.  
  
 크기로 조정 하지 않고 사각형을 회전 하려면 다음 코드를 사용 합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 사각형을 이동 하려면 다음 코드를 사용 합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [관리 GDI+에서 변형 사용](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
