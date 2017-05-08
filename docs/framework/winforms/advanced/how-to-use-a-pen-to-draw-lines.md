---
title: "방법: 펜을 사용하여 선 그리기 | Microsoft Docs"
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
  - "선, 그리기"
  - "펜, 선 그리기"
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 펜을 사용하여 선 그리기
선을 그리려면 <xref:System.Drawing.Graphics> 개체와 <xref:System.Drawing.Pen> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 선의 색과 두께 같은 특징이 저장됩니다.  
  
## 예제  
 아래 예제에서는 \(20, 10\)에서 \(300, 100\)까지 선을 그립니다.  첫 번째 문에서는 <xref:System.Drawing.Pen.%23ctor%2A> 클래스 생성자를 사용하여 검은색 펜을 만듭니다.  <xref:System.Drawing.Pen.%23ctor%2A> 생성자에 전달되는 인수는 <xref:System.Drawing.Color.FromArgb%2A> 메서드를 사용하여 만든 <xref:System.Drawing.Color> 개체입니다.  <xref:System.Drawing.Color> 개체를 만드는 데 사용되는 값 \(255, 0, 0, 0\)은 색의 알파, 빨강, 녹색 및 파랑 구성 요소를 나타냅니다.  이 값은 불투명한 검정 펜을 정의합니다.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Pen>   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [GDI\+의 펜, 선 및 사각형](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)