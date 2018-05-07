---
title: '방법: 색 매핑 변경 테이블 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: ba763cc7960e71c6fc705d40eefdbde163d06181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-remap-table"></a>방법: 색 매핑 변경 테이블 사용
다시 매핑하는 색 다시 매핑 테이블에 따라 이미지의 색을 변환의 프로세스입니다. 색 매핑 변경 테이블은 배열을 <xref:System.Drawing.Imaging.ColorMap> 개체입니다. 각 <xref:System.Drawing.Imaging.ColorMap> 배열의 개체에는 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 속성 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성입니다.  
  
 때 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 에서는 각 픽셀 이미지의 이미지를 그릴 이전 색 배열 비교 됩니다. 픽셀의 색이 이전 색과 일치 하면 해당 새 색으로 변경 됩니다. 렌더링에만 변경 되는 색-이미지 자체의 색상 값 (에 저장 된는 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 개체)은 변경 되지 않습니다.  
  
 배열을 초기화할 매핑이 변경된 된 이미지를 그리려면 <xref:System.Drawing.Imaging.ColorMap> 개체입니다. 해당 배열을 전달는 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달 합니다는 <xref:System.Drawing.Imaging.ImageAttributes> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Drawing.Image> RemapInput.bmp 파일에서 개체입니다. 단일 구성 되는 색 다시 매핑 테이블을 만들고 <xref:System.Drawing.Imaging.ColorMap> 개체입니다. <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 의 속성은 `ColorRemap` 개체는 빨간색, 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성은 파란색입니다. 이미지가 그려지는 한 번 다시 매핑 없이 및 한 번 다시 매핑입니다. 매핑 모든 빨간색 픽셀 파란색을 변경 합니다.  
  
 다음 그림에서는 오른쪽의 왼쪽에 원본 이미지와 매핑이 변경된 된 이미지를 보여 줍니다.  
  
 ![색 다시 매핑](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
