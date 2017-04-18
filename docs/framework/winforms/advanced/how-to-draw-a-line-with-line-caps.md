---
title: "방법: 선 끝이 있는 선 그리기 | Microsoft Docs"
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
  - "선 그리기, 선 끝"
  - "그리기, 선"
  - "선, 그리기"
  - "펜, 선 그리기"
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 선 끝이 있는 선 그리기
선의 시작 또는 끝 부분에 여러 개의 선 끝 모양 중 하나를 그릴 수 있습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 둥근 모양, 정사각형, 다이아몬드, 화살표 모양 등 여러 개의 선 끝 모양을 지원합니다.  
  
## 예제  
 선 시작 부분\(StartCap\), 선 끝 부분\(EndCap\) 또는 파선의 대시\(DashCap\)에 선 끝 모양을 지정할 수 있습니다.  
  
 다음 예제에서는 한 쪽 끝은 화살표 모양이고 다른 한 쪽 끝은 둥근 모양인 선을 그립니다.  이 예제를 실행하면 다음 그림과 같은 선이 만들어집니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens4.png "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## 코드 컴파일  
  
-   Windows Form을 만들고 이 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리한 다음  `e`를 <xref:System.Windows.Forms.PaintEventArgs>로 전달하여 예제 코드를 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에 붙여넣습니다.  
  
## 참고 항목  
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=fullName>   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)