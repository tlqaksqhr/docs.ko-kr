---
title: "방법: 선 조인 | Microsoft Docs"
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
  - "빗면 선 조인 스타일"
  - "그리기, 선 조인"
  - "그래픽, 선 조인"
  - "GraphicsPath 개체"
  - "선 조인"
  - "선, 조인"
  - "마이터 선 조인 스타일"
  - "Pen 클래스"
  - "원형 선 조인 스타일"
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 선 조인
선 조인은 끝 부분이 만나거나 겹치는 두 개의 선에 의해 만들어지는 공통 영역입니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 마이터, 빗면, 원형 등 세 가지 선 조인 스타일을 지정할 수 있습니다.  선 조인 스타일은 <xref:System.Drawing.Pen> 클래스의 속성입니다.  <xref:System.Drawing.Pen> 개체에 선 조인 스타일을 지정하면 이 펜을 사용하여 그리는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체의 모든 연결선에 같은 조인 스타일이 적용됩니다.  
  
 다음 그림에서는 빗면 스타일을 적용한 선 조인 예제의 결과를 보여 줍니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens5.png "pens5")  
  
## 예제  
 <xref:System.Drawing.Pen> 클래스의 <xref:System.Drawing.Pen.LineJoin%2A> 속성을 사용하여 선 조인 스타일을 지정할 수 있습니다.  이 예제에서는 가로 선과 세로 선 사이의 빗면 선 조인을 보여 줍니다.  다음 코드에서 <xref:System.Drawing.Pen.LineJoin%2A> 속성에 할당된 값 <xref:System.Drawing.Drawing2D.LineJoin>은 <xref:System.Drawing.Drawing2D.LineJoin> 열거형의 멤버이고  <xref:System.Drawing.Drawing2D.LineJoin> 열거형의 다른 멤버는 <xref:System.Drawing.Drawing2D.LineJoin>와 <xref:System.Drawing.Drawing2D.LineJoin>입니다.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)