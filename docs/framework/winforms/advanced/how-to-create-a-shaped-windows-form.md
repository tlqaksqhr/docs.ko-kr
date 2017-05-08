---
title: "방법: 모양을 가진 Windows Form 만들기 | Microsoft Docs"
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
  - "폼, 도형 변경"
  - "폼, 원형"
  - "폼, 사용자 지정 도형"
  - "폼, 사각형이 아닌 폼"
  - "폼, 원형 폼"
  - "도형 폼"
  - "Windows Forms, 원형"
  - "Windows Forms, 사용자 지정 도형"
  - "Windows Forms, 사각형이 아닌 도형"
  - "Windows Forms, 원형 폼"
  - "Windows Forms, 도형"
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 모양을 가진 Windows Form 만들기
이 예제에서는 폼을 기초로 크기가 조정되는 타원 모양의 폼을 만듭니다.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms> 및 <xref:System.Drawing> 네임스페이스에 대한 참조  
  
 이 예제에서는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 폼의 모양을 변경합니다.  이 코드를 사용하려면 메서드 선언과 그리기 코드를 메서드 안에 복사해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Region>   
 <xref:System.Drawing>   
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>   
 <xref:System.Windows.Forms.Control.Region%2A>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)