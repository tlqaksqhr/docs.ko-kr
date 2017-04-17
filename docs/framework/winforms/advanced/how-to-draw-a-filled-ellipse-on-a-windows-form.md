---
title: "방법: Windows Form에 채워진 타원 그리기 | Microsoft Docs"
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
  - "Graphics.FillEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "원, 그리기"
  - "원형"
  - "그리기, 타원"
  - "타원, 그리기"
  - "폼, 타원 그리기"
  - "도형, 그리기"
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Form에 채워진 타원 그리기
이 예제에서는 폼에 채워진 타원을 그립니다.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## 코드 컴파일  
 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 이 메서드를 호출할 수 없습니다.  그려진 내용은 폼 크기가 조정되거나 다른 폼에 의해 가려지더라도 새로 그려지지 않습니다.  내용이 자동으로 다시 그려지려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의해야 합니다.  
  
## 강력한 프로그래밍  
 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Graphics> 개체와 같이 시스템 리소스를 소모하는 개체에 대해서는 항상 <xref:System.IDisposable.Dispose%2A>를 호출해야 합니다.  
  
## 참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [선 및 채우기 알파 혼합](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)