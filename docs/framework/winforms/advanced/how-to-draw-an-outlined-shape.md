---
title: "방법: 윤곽선이 있는 도형 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Graphics.DrawEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "원"
  - "원, 그리기"
  - "원형"
  - "그리기, 원형"
  - "그리기, 도형"
  - "타원, 그리기"
  - "폼, 원형 그리기"
  - "윤곽선이 있는 도형, 그리기"
  - "윤곽선이 있는 도형, 예제"
  - "도형, 그리기"
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 윤곽선이 있는 도형 그리기
이 예제에서는 폼에서 윤곽선이 있는 타원과 사각형을 그립니다.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## 코드 컴파일  
 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 이 메서드를 호출할 수 없습니다.  그려진 내용은 폼 크기가 조정되거나 다른 폼에 의해 가려지더라도 새로 그려지지 않습니다.  내용이 자동으로 다시 그려지려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의해야 합니다.  
  
## 강력한 프로그래밍  
 <xref:System.Drawing.Pen> 및 <xref:System.Drawing.Graphics> 개체와 같이 시스템 리소스를 소모하는 개체에 대해서는 항상 <xref:System.IDisposable.Dispose%2A>를 호출해야 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Graphics.DrawRectangle%2A>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)