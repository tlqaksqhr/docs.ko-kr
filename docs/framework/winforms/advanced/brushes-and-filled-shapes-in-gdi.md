---
title: GDI+의 브러시 및 채워진 도형
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>GDI+의 브러시 및 채워진 도형
사각형, 타원, 등의 닫힌된 셰이프 개요와 내부 구성 됩니다. 윤곽선 펜으로 그려지고 브러시로 내부 채워집니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 닫힌 도형의 내부를 채우는 브러시는 여러 클래스 제공: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, 및 <xref:System.Drawing.Drawing2D.PathGradientBrush>합니다. 이 클래스는 모두에서 상속 된 <xref:System.Drawing.Brush> 클래스입니다. 다음 그림에서는 단색 브러시 채워진 사각형 및 타원 빗살 무늬 브러시 채워진 보여 줍니다.  
  
 ![채워진 모양](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>단색 브러시  
 닫힌된 셰이프를 채울 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Brush>합니다. 인스턴스는 <xref:System.Drawing.Graphics> 클래스와 같은 메서드를 제공 <xref:System.Drawing.Graphics.FillRectangle%2A> 및 <xref:System.Drawing.Graphics.FillEllipse%2A>, 및 <xref:System.Drawing.Brush> 채우기, 색 및 패턴 등의 특성을 저장 합니다. <xref:System.Drawing.Brush> fill 메서드를 인수 중 하나로 전달 됩니다. 다음 코드 예제에서는 빨간색 단색으로 타원을 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  브러시는 앞의 예제에서 형식의 <xref:System.Drawing.SolidBrush>에서 상속한 <xref:System.Drawing.Brush>합니다.  
  
## <a name="hatch-brushes"></a>빗살 무늬 브러시  
 빗살 무늬 브러시 도형을 채우는 전경색, 배경색 및 해치 스타일을 지정 합니다. 전경색은 해칭의 색입니다.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 50 개 이상의 해치 스타일; 제공 다음 그림에 표시 된 세 가지 스타일은 <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, 및 <xref:System.Drawing.Drawing2D.HatchStyle.Cross>합니다.  
  
 ![채워진 모양](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>질감 브러시  
 질감 브러시와 패턴 비트맵에 저장 된 셰이프를 채울 수 있습니다. 예를 들어, 다음 그림은 라는 디스크 파일에 저장 `MyTexture.bmp`합니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 다음 코드 예제에 저장 된 그림을 반복 하 여 타원을 채우는 방법을 보여 줍니다. `MyTexture.bmp`합니다.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 다음 그림에서는 채워진된 타원을 보여 줍니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>그라데이션 브러시  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 두 종류의 그라데이션 브러시를 제공 합니다: 선형 및 경로입니다. 선형 그라데이션 브러시에 따라 점차 도형에서 가로, 세로 또는 대각선 방향으로 변경 하는 색으로 도형 채우기를 사용할 수 있습니다. 다음 코드 예제는 타원의 왼쪽된 가장자리에서 맨 오른쪽으로 이동 하면 파랑에서 녹색으로 변경 하는 가로 그라데이션 브러시로 타원을 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 다음 그림에서는 채워진된 타원을 보여 줍니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 가장자리를 향해 셰이프의 가운데 간에 이동할 때 색을 변경 하려면 경로 그라데이션 브러시를 구성할 수 있습니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 경로 그라데이션 브러시는 매우 유연 합니다. 다음 그림에서에서 변경 내용 점진적으로 가운데에 빨간색 각 꼭 짓 서로 다른 세 색에에서 있는 삼각형을 채우는 데 사용 되는 그라데이션 브러시입니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [방법: Windows Form에 채워진 사각형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [방법: Windows Form에 채워진 타원 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
