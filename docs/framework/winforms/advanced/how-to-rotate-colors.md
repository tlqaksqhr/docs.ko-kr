---
title: "방법: 색 회전"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c82a77ff3d643afc0ddd542868a96c17d31ef336
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-colors"></a>방법: 색 회전
4 차원 색 공간에서 회전 시각화 하기 어렵습니다. 동의 고정 색상 구성 요소 중 하나를 유지 하는 것으로 회전 시각화할 쉽게 만들 수 있습니다. 1 자리 알파 구성 요소 (완전히 불투명 함)을 유지 한다고 가정 합니다. 다음 다음 그림에 나와 있는 것 처럼 빨간색, 녹색 및 파란색 축이 있는 3 차원 색 공간을 시각화할 수 했습니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 색 3 차원 공간에서 지점으로 생각할 수 있습니다. 예를 들어 공간에서 지점 (1, 0, 0) 빨강을 나타내고 녹색 공간에서 지점 (0, 1, 0)을 나타냅니다.  
  
 다음 그림은 빨강-녹색 평면에서 60도의 각도 통해 (1, 0, 0) 색 회전 하는 의미를 보여 줍니다. 빨간색-녹색 평면과 평면 병렬로 회전 파란색 축을 중심으로 회전으로 생각할 수 있습니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 다음 그림에는 각각 세 개의 좌표 축 (빨강, 녹색, 파랑)을 중심으로 회전에 색 매트릭스를 초기화 하는 방법을 보여 줍니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>예제  
 다음 예제에서는 (1, 0, 0.6) 모두 같은 색 이므로 파란색 축에 대 한 60도 회전을 적용 하는 이미지입니다. 회전 각도 빨간색-녹색 평면과 평행 하는 평면에 이루어집니다.  
  
 다음 그림에서는 왼쪽 및 오른쪽에 있는 색 회전 이미지에 원본 이미지를 보여 줍니다.  
  
 ![색 회전](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 다음 그림에서는 다음 코드에서 수행 되는 색 회전의 시각화를 보여 줍니다.  
  
 ![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다. 대체 `RotationInput.bmp` 있는 이미지 파일 이름 및 경로 시스템에서 사용할 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)
