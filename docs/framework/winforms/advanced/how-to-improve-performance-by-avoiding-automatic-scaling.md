---
title: '방법: 자동 배율 조정 없이 성능 향상'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: e1c46f805b7ba2e2f2a1eb52042cc2ca08e63e03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>방법: 자동 배율 조정 없이 성능 향상
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 그릴 때, 성능 저하가 발생 하는 이미지의 배율을 조정 자동으로 될 수 있습니다. 이미지의 배율에 대상 사각형의 크기를 전달 하 여 제어할 수 또는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.  
  
 다음을 호출 하는 예를 들어는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 왼쪽 위 모퉁이 지정 하는 메서드 (50, 30) 하지만 대상 사각형을 지정 하지 않습니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 이 가장 쉬운 버전의는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 반드시 가장 효율적인 아니므로 필요한 인수 수를 기준으로 합니다. 해결 방법을 사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (일반적으로 96dpi)에 저장 된 해상도와 다른는 <xref:System.Drawing.Image> 개체 면 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 이미지 크기를 조정 합니다. 예를 들어 한 <xref:System.Drawing.Image> 개체에 216 픽셀 너비와 72 인 저장된 수평 해상도 값입니다. 216/72 3, 이므로 <xref:System.Drawing.Graphics.DrawImage%2A> 을 갖도록 3 인치 너비 96dpi의 해상도 이미지 배율을 조정 합니다. 즉, <xref:System.Drawing.Graphics.DrawImage%2A> 96 x 3 = 288의 너비는 이미지가 표시 됩니다 (픽셀)입니다.  
  
 화면 해상도 96dpi와에서 다른 경우에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 할 배율 이미지 하면 화면 해상도 96dpi 인 것 처럼 합니다. 때문는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 개체가 장치 컨텍스트와 연결 된 시기 및 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 화면 해상도 결과 대 한 장치 컨텍스트는 실제 화면 해상도 관계 없이 96 일반적으로 쿼리 합니다. 대상 사각형을 지정 하 여 자동 크기 조정 작업을 방지할 수 있습니다는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 번 동일한 이미지를 그립니다. 첫 번째 경우에서 대상 사각형의 높이 너비 지정 되지 않은 및 이미지가 자동으로 크기가 조정 됩니다. 두 번째 경우에 너비와 대상 사각형의 높이 (픽셀 단위)를 원본 이미지의 높이 너비와 동일 하 게 지정 됩니다. 다음 그림에서는 두 번 렌더링 되는 이미지를 보여 줍니다.  
  
 ![질감 크기가 조정](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 이미지 이름 및 시스템에 유효한 경로 Texture.jpg를 대체 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
