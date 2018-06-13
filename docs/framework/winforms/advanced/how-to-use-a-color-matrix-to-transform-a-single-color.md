---
title: '방법: 색 매트릭스를 사용하여 단색으로 변형'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 741259fcf853c82dfd13b43edc92e50d8767887b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527406"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>방법: 색 매트릭스를 사용하여 단색으로 변형
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 제공 된 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 저장 및 이미지 조작을 위한 클래스입니다. <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체는 32 비트 숫자 각 픽셀의 색을 저장 합니다: 각각 빨강, 녹색, 파랑 및 알파에 8 비트입니다. 네 개의 구성 요소가 0부터 농도가 없음을 나타내고 255 전체 강도 나타내는 0부터 255 까지의 숫자입니다. 알파 구성 요소는 색상의 투명도 지정 합니다.: 0은 완전히 투명 하며, 255은 완전히 불투명 합니다.  
  
 색 벡터 (빨강, 녹색, 파란색, alpha) 형태의 4-튜플 됩니다. 예를 들어 색 벡터 (0, 255, 0, 255) 빨강 및 파랑 하지만 농도가 녹색 불투명 한 색을 나타냅니다.  
  
 색을 표시 하는 다른 규칙 전체 강도 대 한 숫자 1을 사용 합니다. 이 규칙을 사용 하 여 이전 단락에 설명 된 색을 표시 벡터 (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 색을 변환할 때 전체 강도으로 1의 규칙을 사용 합니다.  
  
 4x4 매트릭스 색 벡터를 곱하여 색 벡터 선형 변환 (예: 회전, 배율 및 like)을 적용할 수 있습니다. 그러나는 비선형 변환을 수행 하는 4x4 매트릭스를 사용할 수 없습니다. 색 벡터의 각 더미 다섯 번째 좌표 (예를 들어 번호 1)를 추가 하는 경우에 선형 변환 및 번역의 조합을 적용할 5 × 5 매트릭스를 사용할 수 있습니다. 번역 나옵니다 선형 변환으로 구성 된 변환에는 3x3 유사 변환을 이라고 합니다.  
  
 예를 들어 색 (0.2, 0.0, 0.4, 1.0)로 시작 하 고 다음과 같은 변환을 적용 하려는 있다고 가정 합니다.  
  
1.  Double 빨강 구성 요소  
  
2.  0.2 빨강, 녹색 및 파랑 구성 요소에 추가  
  
 다음 매트릭스 곱 나열 된 순서로 변환이 수행 합니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 색 매트릭스의 요소는 행과 열으로 (0부터 시작) 인덱싱됩니다. 예를 들어 다섯 번째 행과 M 행렬의 세 번째 열에 있는 항목은 M [2] [4]로 표시 됩니다.  
  
 (다음 그림에 표시) 5 × 5 항등 매트릭스 대각선 1 및 0으로 다른 곳에 있습니다. 색 벡터 항등 매트릭스를 곱하면 색 벡터 변경 되지 않습니다. 색 변환 매트릭스를 형성 하는 편리한 방법은 항등 매트릭스로 시작 하 고 원하는 변환에서 생성 하는 약간만 변경 하는 합니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 행렬 및 변환의 자세한 논의 알려면 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모두 한 가지 색상 (0.2, 0.0, 0.4, 1.0) 및 이전 단락에 설명 된 변환을 적용 하는 이미지입니다.  
  
 다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지 및 변형 된 이미지를 보여 줍니다.  
  
 ![색](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 다음 예제에서 코드는 다음 단계를 사용 하 여 다시 칠하기는 수행:  
  
1.  초기화는 <xref:System.Drawing.Imaging.ColorMatrix> 개체입니다.  
  
2.  만들기는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달는 <xref:System.Drawing.Imaging.ColorMatrix> 개체는 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체입니다.  
  
3.  전달 된 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
