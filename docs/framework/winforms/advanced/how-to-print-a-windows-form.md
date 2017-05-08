---
title: "방법: Windows Form 인쇄 | Microsoft Docs"
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
  - "인쇄[Windows Forms, 폼 인쇄"
  - "인쇄[Windows Forms]"
  - "폼 인쇄"
  - "Windows Forms, 인쇄"
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows Form 인쇄
개발 과정의 일부로 Windows Form의 복사본을 인쇄해야 하는 경우가 많습니다.  다음 코드 예제에서는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용하여 현재 폼의 복사본을 인쇄하는 방법을 보여 줍니다.  
  
## 예제  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## 코드 컴파일  
 이 예제는 `Main`메서드가 들어 있는 완전한 코드 예제입니다.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   프린터에 액세스할 수 있는 권한이 없는 경우  
  
-   설치된 프린터가 없는 경우  
  
## .NET Framework 보안  
 이 코드 예제를 실행하려면 컴퓨터에서 사용할 프린터에 액세스할 수 있는 권한이 있어야 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>   
 [방법: GDI\+를 사용하여 이미지 렌더링](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)   
 [방법: Windows Forms의 그래픽 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)