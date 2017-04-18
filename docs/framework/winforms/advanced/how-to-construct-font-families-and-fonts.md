---
title: "방법: 글꼴 패밀리 및 글꼴 만들기 | Microsoft Docs"
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
  - "글꼴 패밀리, 만들기"
  - "글꼴, 만들기"
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 글꼴 패밀리 및 글꼴 만들기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 서체는 같고 스타일이 다른 글꼴로 글꼴 패밀리를 구성합니다.  예를 들어, Arial 글꼴 패밀리는 다음과 같은 글꼴로 구성됩니다.  
  
-   Arial Regular  
  
-   Arial Bold  
  
-   Arial Italic  
  
-   Arial Bold Italic  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 보통, 굵게, 기울임꼴 및 굵은 기울임꼴 등 네 가지 스타일을 사용하여 패밀리를 구성합니다.  *narrow* 및 *rounded*와 같은 형용사는 스타일이 아니라 패밀리 이름의 일부입니다.  예를 들어, Arial Narrow는 다음과 같은 멤버를 포함하는 글꼴 패밀리입니다.  
  
-   Arial Narrow Regular  
  
-   Arial Narrow Bold  
  
-   Arial Narrow Italic  
  
-   Arial Narrow Bold Italic  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 텍스트를 그리려면 먼저 <xref:System.Drawing.FontFamily> 개체와 <xref:System.Drawing.Font> 개체를 만들어야 합니다.  <xref:System.Drawing.FontFamily> 개체는 서체\(예: Arial\)를 지정하고 <xref:System.Drawing.Font> 개체는 크기, 스타일 및 단위를 지정합니다.  
  
## 예제  
 다음 예제에서는 16픽셀 크기로 보통 스타일의 Arial 글꼴을 만듭니다.  다음 코드에서 <xref:System.Drawing.Font.%23ctor%2A> 생성자에 전달되는 첫 번째 인수는  <xref:System.Drawing.FontFamily> 개체입니다.  두 번째 인수에는 글꼴의 크기를 네 번째 인수에서 지정하는 단위로 지정합니다.  세 번째 인수에는 스타일을 지정합니다.  
  
 <xref:System.Drawing.GraphicsUnit>은 <xref:System.Drawing.GraphicsUnit> 열거형의 멤버이고 <xref:System.Drawing.FontStyle>는 <xref:System.Drawing.FontStyle> 열거형의 멤버입니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)