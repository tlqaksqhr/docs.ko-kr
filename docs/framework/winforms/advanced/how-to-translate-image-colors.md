---
title: "방법: 이미지 색 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c21d20b631d8e0cf68e370dd43b3f5e92144b09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-translate-image-colors"></a>방법: 이미지 색 변환
번역 네 가지 구성 요소 중 하나 이상에 값을 추가합니다. 다음 표에 번역을 나타내는 색 매트릭스 항목이 제공 됩니다.  
  
|변환할 구성 요소|행렬 항목|  
|--------------------------------|------------------|  
|빨강|[4][0]|  
|녹색|[4][1]|  
|파랑|[4][2]|  
|알파|[4][3]|  
  
## <a name="example"></a>예제  
 다음 구성 예제는 <xref:System.Drawing.Image> ColorBars.bmp 파일에서 개체입니다. 다음 코드는 이미지의 각 픽셀의 빨간색 구성 요소를 0.75를 추가합니다. 변환된 된 이미지와 함께 원본 이미지를 그립니다.  
  
 다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지 및 변형 된 이미지를 보여 줍니다.  
  
 ![색 변환](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 다음 표에서 빨간색 번역 전후 막대 네 개에 대 한 색 벡터를 나열합니다. Note 색상 구성 요소에 대 한 최대 값이 1 이면 때문에 두 번째 행의 빨간색 구성 요소 변경 되지 않습니다. (마찬가지로, 색상 구성 요소에 대 한 최소 값은 0입니다.)  
  
|원래 색|번역 언어|  
|--------------|----------------|  
|검은색 (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|빨강 (1, 0, 0, 1)|(1, 0, 0, 1)|  
|녹색 (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|파랑 (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다. 대체 `ColorBars.bmp` 있는 이미지 파일 이름 및 시스템에서 사용할 수 있는 경로입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)
