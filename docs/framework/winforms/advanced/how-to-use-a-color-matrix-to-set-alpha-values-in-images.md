---
title: "방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정"
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
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dde9417782e4404237a995364d65058f023c3e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정
<xref:System.Drawing.Bitmap> 클래스 (에서 상속 되는 <xref:System.Drawing.Image> 클래스) 및 <xref:System.Drawing.Imaging.ImageAttributes> 클래스 가져오고 픽셀 값을 설정 하기 위한 기능을 제공 합니다. 사용할 수는 <xref:System.Drawing.Imaging.ImageAttributes> 알파를 수정 하는 클래스는 전체 이미지에 대 한 값 하거나 호출할 수 있습니다는 <xref:System.Drawing.Bitmap.SetPixel%2A> 의 메서드는 <xref:System.Drawing.Bitmap> 개별 픽셀 값을 수정 하는 클래스입니다.  
  
## <a name="example"></a>예  
 <xref:System.Drawing.Imaging.ImageAttributes> 클래스에 렌더링 하는 동안 이미지를 수정 하는 데 사용할 수 있는 여러 속성이 있습니다. 다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체 알파 값을 모두 원래 대로의 80%로 설정 하는 데 사용 됩니다. 색 매트릭스를 초기화 하 고 알파 배율 조정 0.8 행렬에는 값을 설정 하면 됩니다. 색 매트릭스의 주소에 전달 되는 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체 및 <xref:System.Drawing.Imaging.ImageAttributes> 를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 렌더링 하는 동안 경우 비트맵의 알파 값은 원래 대로의 80%로 변환 됩니다. 따라서 이미지를 배경색과 혼합 됩니다. 다음 그림에 나와 있는 비트맵 이미지 찾아 선택 합니다. 이 통해 검은색 실선을 볼 수 있습니다.  
  
 ![행렬을 사용 하 여 알파 혼합](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 여기서 이미지는 흰색 부분 배경색, 이미지를 흰색으로 혼합 되 합니다. 이미지는 검은색 줄과 교차 검은색 이미지 혼합 됩니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [선 및 채우기 알파 혼합](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
