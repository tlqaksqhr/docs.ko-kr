---
title: 변형을 사용하여 색의 비율 조정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 6cfe90cef42086672990c45c99961db3d29c3ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525969"
---
# <a name="using-transformations-to-scale-colors"></a>변형을 사용하여 색의 비율 조정
크기 조정 변환을 숫자는 네 가지 구성 요소 중 하나 이상을 곱합니다. 다음 테이블에 확장을 나타내는 색 매트릭스 항목이 제공 됩니다.  
  
|구성 요소 크기를 조정할 수|행렬 항목|  
|----------------------------|------------------|  
|빨강|[0][0]|  
|녹색|[1][1]|  
|파랑|[2][2]|  
|알파|[3][3]|  
  
## <a name="scaling-one-color"></a>한 가지 색을 크기 조정  
 다음 구성 예제는 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다. 그런 다음 코드는 2 배 이미지에 각 픽셀의 파란색 구성 요소를 확장 합니다. 변환된 된 이미지와 함께 원본 이미지를 그립니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.  
  
 ![색의 배율을 조정](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 다음 표에서 앞과 뒤 파란색 크기 조정 막대 네 개에 대 한 색 벡터를 나열합니다. 네 번째 색 막대에 있는 파란색 구성 0.8 0.6을 참고 합니다. 때문 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 결과의 소수 부분에만 유지 합니다. 예를 들어 (2)(0.8) = 1.6은 0.6 1.6의 소수 부분 및 합니다. 소수 부분이 그대로 유지 하 고 결과 항상 [0, 1] 간격을 확인 합니다.  
  
|원래 색|배율 조정|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>여러 색 비율 조정  
 다음 구성 예제는 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다. 그런 다음 코드는 이미지에 각 픽셀의 빨간색, 녹색 및 파랑 구성 요소를 확장 합니다. 빨간색 구성 요소는 25% 크기가 조정 되어, 녹색 구성 요소는 35% 크기가 조정 되어 및 파랑 구성 요소는 50%를 축소 합니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.  
  
 ![색의 배율을 조정](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 다음 표에서 빨간색, 녹색 및 파란색 배율을 전후 막대 네 개에 대 한 색 벡터를 나열합니다.  
  
|원래 색|배율 조정|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)
