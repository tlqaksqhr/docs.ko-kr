---
title: "방법: Windows Form에 선 그리기 | Microsoft Docs"
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
  - "Graphics.DrawLine"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "선 그리기"
  - "그리기, 선"
  - "예제[Windows Forms], 폼에 선 그리기"
  - "선, 그리기"
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Form에 선 그리기
이 예제에서는 폼에 선을 그립니다.  일반적으로 폼에 그릴 때는 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리하고, 이 예제에서와 같이 <xref:System.Windows.Forms.PaintEventArgs>의 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 속성을 사용하여 그리기를 수행합니다.  
  
## 예제  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 강력한 프로그래밍  
 <xref:System.Drawing.Pen> 개체와 같이 시스템 리소스를 소모하는 개체에 대해서는 항상 <xref:System.IDisposable.Dispose%2A>를 호출해야 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Graphics.DrawLine%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)