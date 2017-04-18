---
title: "방법: 펜 색 설정 | Microsoft Docs"
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
  - "색이 있는 펜"
  - "펜, 색 설정"
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 펜 색 설정
이 예제에서는 기존 <xref:System.Drawing.Pen> 개체의 색을 변경합니다.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이  `myPen`인 <xref:System.Drawing.Pen> 개체  
  
## 강력한 프로그래밍  
 <xref:System.Drawing.Pen> 개체와 같이 시스템 리소스를 소모하는 개체의 사용이 끝나면 해당 개체에 대해 <xref:System.Drawing.Pen.Dispose%2A>를 호출해야 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Pen>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [GDI\+의 펜, 선 및 사각형](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)