---
title: "GDI+의 브러시 및 채워진 도형 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "브러시, GDI+"
  - "브러시, 그라데이션"
  - "채워진 도형, GDI+"
  - "GDI+, 브러시"
  - "GDI+, 채워진 도형"
  - "그라데이션 브러시"
  - "도형, GDI+"
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# GDI+의 브러시 및 채워진 도형
사각형 또는 타원과 같은 폐도형은 윤곽선과 내부로 이루어져 있습니다.  펜을 사용하여 윤곽선을 그리고 브러시를 사용하여 내부를 채웁니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 폐도형의 내부를 채울 수 있도록 <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> 및 <xref:System.Drawing.Drawing2D.PathGradientBrush>와 같은 여러 가지 브러시 클래스를 제공합니다.  이러한 클래스는 모두 <xref:System.Drawing.Brush> 클래스에서 상속됩니다.  다음 그림은 단색 브러시로 채운 사각형과 빗살 무늬 브러시로 채운 타원을 보여 줍니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.png "Aboutgdip02\_art17")  
  
## 단색 브러시  
 폐도형을 채우려면 <xref:System.Drawing.Graphics> 클래스 인스턴스와 <xref:System.Drawing.Brush>가 필요합니다.  <xref:System.Drawing.Graphics> 클래스 인스턴스는 <xref:System.Drawing.Graphics.FillRectangle%2A>과 <xref:System.Drawing.Graphics.FillEllipse%2A> 같은 메서드를 제공하고 <xref:System.Drawing.Brush>에는 색과 패턴 같은 채우기 특성이 저장됩니다.  <xref:System.Drawing.Brush>는 채우기 메서드에 대한 인수 중 하나로 전달됩니다.  다음 코드 예제에서는 빨간색으로 타원을 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  위의 예제에서 브러시 유형은 <xref:System.Drawing.Brush>에서 상속된 <xref:System.Drawing.SolidBrush>입니다.  
  
## 빗살 무늬 브러시  
 도형을 빗살 무늬 브러시로 채울 때 전경색, 배경색 및 사선 스타일을 지정합니다.  전경색은 사선 색입니다.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에는 50개가 넘는 빗살 무늬 스타일이 있으며 이 중에서 다음 그림에 표시된 스타일은 <xref:System.Drawing.Drawing2D.HatchStyle>, <xref:System.Drawing.Drawing2D.HatchStyle> 및 <xref:System.Drawing.Drawing2D.HatchStyle>입니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.png "Aboutgdip02\_art18")  
  
## 질감 브러시  
 질감 브러시를 사용하여 도형을 비트맵에 저장된 패턴으로 채울 수 있습니다.  예를 들어 `MyTexture.bmp`라는 디스크 파일에 다음 그림을 저장한다고 가정합니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.png "Aboutgdip02\_Art19")  
  
 다음 코드 예제에서는 `MyTexture.bmp`에 저장된 그림을 반복하여 타원을 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 아래 그림에 채워진 타원이 나와 있습니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.png "AboutGdip02\_Art20")  
  
## 그라데이션 브러시  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 선형과 경로라는 두 가지 유형의 그라데이션 브러시를 제공합니다.  선형 그라데이션 브러시를 사용하면 가로, 세로 또는 사선 방향에 따라 점차 변하는 색으로 도형을 채울 수 있습니다.  다음 코드 예제에서는 타원의 왼쪽 가장자리에서 오른쪽 가장자리로 이동함에 따라 파란색에서 녹색으로 변하는 가로 그라데이션 브러시로 타원을 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 아래 그림에 채워진 타원이 나와 있습니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.png "AboutGdip02\_Art21")  
  
 경로 그라데이션 브러시를 도형의 중앙에서 가장자리로 움직임에 따라 색이 변하도록 구성할 수 있습니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.png "AboutGdip02\_Art22")  
  
 경로 그라데이션 브러시는 매우 유연합니다.  다음 그림에서 삼각형을 채우는 데 사용된 그라데이션 브러시는 중앙의 빨강에서 서로 다른 색의 세 꼭짓점으로 갈수록 서서히 색이 변합니다.  
  
 ![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.png "AboutGdip02\_Art23")  
  
## 참고 항목  
 <xref:System.Drawing.SolidBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=fullName>   
 <xref:System.Drawing.TextureBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: Windows Form에 채워진 사각형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)   
 [방법: Windows Form에 채워진 타원 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)