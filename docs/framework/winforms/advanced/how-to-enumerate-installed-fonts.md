---
title: "방법: 설치된 글꼴 열거 | Microsoft Docs"
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
  - "예제[Windows Forms], 글꼴"
  - "글꼴, 설치된 글꼴 열거"
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 설치된 글꼴 열거
<xref:System.Drawing.Text.InstalledFontCollection> 클래스는 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스에서 상속됩니다.  <xref:System.Drawing.Text.InstalledFontCollection> 개체는 컴퓨터에 설치되어 있는 글꼴을 열거하는 데 사용할 수 있습니다.  <xref:System.Drawing.Text.InstalledFontCollection> 개체의 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.FontFamily> 개체의 배열입니다.  
  
## 예제  
 아래 예제에서는 시스템에 설치되어 있는 모든 글꼴 패밀리의 이름을 나열합니다.  해당 코드에서는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성에서 반환된 배열에 있는 각 <xref:System.Drawing.FontFamily> 개체의 <xref:System.Drawing.FontFamily.Name%2A> 속성을 검색하고  검색된 패밀리 이름을 연결하여 쉼표로 분리된 목록을 만듭니다.  그런 다음 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드가 쉼표로 구분된 목록을 사각형 안에 그립니다.  
  
 예제 코드를 실행하면 다음 그림과 비슷한 결과가 나타납니다.  
  
 ![설치된 글꼴](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  또한 <xref:System.Drawing.Text> 네임스페이스를 가져와야 합니다.  
  
## 참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)