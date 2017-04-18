---
title: "방법: 그린 텍스트에 탭 정지 설정 | Microsoft Docs"
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
  - "탭, 그린 텍스트"
  - "텍스트, 탭 정지를 사용하여 그리기"
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 그린 텍스트에 탭 정지 설정
<xref:System.Drawing.StringFormat> 개체의 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드를 호출한 다음 해당 <xref:System.Drawing.StringFormat> 개체를 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달하여 텍스트에 대한 탭 정지를 설정할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>에서 그린 텍스트에 대한 탭 정지를 추가하지 않지만 <xref:System.Windows.Forms.TextFormatFlags?displayProperty=fullName> 플래그를 사용하여 기존 탭 정지를 확장할 수 있습니다.  
  
## 예제  
 아래 예제에서는 150, 250 및 350에 탭 정지를 설정합니다.  그런 다음 코드에서는 이름과 테스트 점수로 이루어진 탭 목록을 표시합니다.  
  
 아래 그림에서는 탭 정지가 설정된 텍스트를 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 다음 코드에서는 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드에 두 개의 인수를 전달합니다.  두 번째 인수는 탭 오프셋이 들어 있는 배열입니다.  <xref:System.Drawing.StringFormat.SetTabStops%2A>에 전달된 첫 번째 인수는 0입니다. 이는 배열에서 첫 번째 오프셋이 경계 사각형의 왼쪽 가장자리인 위치 0에서 시작된다는 것을 나타냅니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## 코드 컴파일  
  
-   앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)