---
title: "방법: 질감으로 채워진 선 그리기 | Microsoft Docs"
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
  - "선 그리기, 질감"
  - "그리기, 선"
  - "선, 질감"
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 질감으로 채워진 선 그리기
단색 선 대신 질감을 가진 선을 그릴 수도 있습니다.  질감이 있는 선과 곡선을 그리려면 <xref:System.Drawing.TextureBrush> 개체를 만든 다음 이 <xref:System.Drawing.TextureBrush> 개체를 <xref:System.Drawing.Pen.%23ctor%2A> 생성자에 전달합니다.  질감 브러시와 연결된 비트맵으로 평면을 바둑판식으로 채워 보이지 않게 하고, 펜을 사용하여 선이나 곡선을 그릴 때는 펜의 이동 경로에 따라 해당 픽셀에서 질감이 제거됩니다.  
  
## 예제  
 다음 예제에서는  `Texture1.jpg` 파일에서 <xref:System.Drawing.Bitmap> 개체를 만듭니다.  이 비트맵은 <xref:System.Drawing.TextureBrush> 개체를 만드는 데 사용되고 <xref:System.Drawing.TextureBrush> 개체는 <xref:System.Drawing.Pen> 개체를 만드는 데 다시 사용됩니다.  <xref:System.Drawing.Graphics.DrawImage%2A>를 호출하면 왼쪽 위 모퉁이가 \(0, 0\) 좌표인 비트맵이 그려지고  <xref:System.Drawing.Graphics.DrawEllipse%2A>를 호출하면 <xref:System.Drawing.Pen> 개체를 사용하여 질감이 있는 타원을 그릴 수 있습니다.  
  
 아래 그림에 비트맵 및 질감이 있는 타원이 나와 있습니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## 코드 컴파일  
 Windows Form을 만들고 이 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리한 다음  위의 코드를 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에 붙여넣고   `Texture.jpg`를 시스템에서 사용할 수 있는 이미지로 바꿉니다.  
  
## 참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)