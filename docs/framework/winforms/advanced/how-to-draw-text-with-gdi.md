---
title: "방법: GDI를 사용하여 텍스트 그리기 | Microsoft Docs"
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
  - "그리기, 텍스트"
  - "GDI, 텍스트 그리기[Windows Forms]"
  - "텍스트, TextRenderer를 사용하여 그리기"
  - "Windows Forms, GDI를 사용하여 텍스트 그리기"
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: GDI를 사용하여 텍스트 그리기
<xref:System.Windows.Forms.TextRenderer> 클래스의 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용하면 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 기능을 통해 폼이나 컨트롤에 텍스트를 그릴 수 있습니다.  [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트 렌더링은 일반적으로 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]보다 좋은 성능과 정확한 텍스트 길이 맞춤을 제공합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer> 클래스의 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드는 인쇄 기능을 지원하지 않습니다.  인쇄할 때는 항상 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용하여 사각형 안의 여러 줄에 텍스트를 그리는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <xref:System.Windows.Forms.TextRenderer> 클래스를 사용하여 텍스트를 렌더링하려면 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Font>와 같은 <xref:System.Drawing.IDeviceContext>, 텍스트를 그릴 위치 및 텍스트를 그릴 색이 필요합니다.  필요에 따라 <xref:System.Windows.Forms.TextFormatFlags> 열거형을 사용하여 텍스트 서식을 지정할 수 있습니다.  
  
 <xref:System.Drawing.Graphics>를 가져오는 방법에 대한 자세한 내용은 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하십시오.  <xref:System.Drawing.Font>를 생성하는 방법에 대한 자세한 내용은 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)를 참조하십시오.  
  
## 코드 컴파일  
 앞의 코드 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextRenderer>   
 <xref:System.Drawing.Font>   
 <xref:System.Drawing.Color>   
 <xref:System.Drawing.Color>   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)