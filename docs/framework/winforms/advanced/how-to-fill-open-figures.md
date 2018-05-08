---
title: '방법: 열린 그림 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-fill-open-figures"></a>방법: 열린 그림 채우기
전달 하 여 경로 채울 수는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 <xref:System.Drawing.Graphics.FillPath%2A> 메서드. <xref:System.Drawing.Graphics.FillPath%2A> 메서드는 현재 경로 대해 설정 된 채우기 모드 (대체 또는 굴곡)에 따라 경로 입력 합니다. 경로 열린 그림이, 경로 해당 종료 된 경우에 따라 채워집니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 시작 점으로 끝점에서 직선 그리기 하 여 그림을 닫습니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 하나의 열린 그림 (호) 및 하나의 폐쇄형된 도형 (: 타원)에 포함 된 경로 만듭니다. <xref:System.Drawing.Graphics.FillPath%2A> 채워지는 기본 채우기 모드, 즉에 따라 경로 <xref:System.Drawing.Drawing2D.FillMode.Alternate>합니다.  
  
 다음 그림에서는 예제 코드의 출력을 보여 줍니다. 경로가 입력 됩니다 (에 따라 <xref:System.Drawing.Drawing2D.FillMode.Alternate>) 열린 그림을 시작 점으로 끝점에서 직선으로 종료 된 경우에 따라 합니다.  
  
 ![열린 경로 채우기](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [GDI+의 그래픽 경로](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
