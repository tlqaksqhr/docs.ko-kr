---
title: "방법: 색 전단"
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a32e6c1901f84c276c071402dac641d45566717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-shear-colors"></a>방법: 색 전단
기울이기 증가 또는 다른 색상 구성 요소에 비례 하는 양을 색상 구성 요소 감소 합니다. 예를 들어 빨강 구성 요소를 1/2 파랑의 값 만큼 늘리는 변환을 사용 하십시오. 이러한 변환에서 (0.7, 0.5, 1) (0.2, 0.5, 1) 색 될 것입니다. 새 빨강 구성은 0.2 + (1/2)(1) 0.7입니다.  
  
## <a name="example"></a>예  
 다음 구성 예제는 <xref:System.Drawing.Image> ColorBars4.bmp 파일에서 개체입니다. 다음 코드는 각 픽셀 이미지에 이전 단락에 설명 된 기울이기 변환을 적용 합니다.  
  
 다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 기울이기가 적용 된 이미지를 보여 줍니다.  
  
 ![색 전단](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 다음 표에서 기울이기 변형 전과 후 막대 네 개에 대 한 색 벡터를 나열합니다.  
  
|원래 색|전단|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다. 대체 `ColorBars.bmp` 이미지 이름 및 경로 시스템에서 사용할 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)
