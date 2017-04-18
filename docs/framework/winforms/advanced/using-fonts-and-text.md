---
title: "글꼴 및 텍스트 사용 | Microsoft Docs"
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
  - "예제[Windows Forms], 글꼴 및 텍스트"
  - "글꼴, Windows Forms에서 사용"
  - "GDI, 텍스트 그리기[Windows Forms]"
  - "문자열[Windows Forms], Windows Forms에 그리기"
  - "텍스트[Windows Forms], Windows Forms에 그리기"
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 글꼴 및 텍스트 사용
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]는 Windows Forms에서 텍스트를 그리는 데 사용할 수 있는 여러 클래스를 제공합니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 클래스에는 텍스트의 위치, 경계 사각형, 글꼴 및 서식과 같은 다양한 기능을 지정할 수 있는 몇 가지 <xref:System.Drawing.Graphics.DrawString%2A> 메서드가 있습니다.  또한 `TextRenderer` 클래스에서 제공하는 정적 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 및 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> 메서드를 사용하여 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]로 텍스트를 그리고 길이를 맞출 수 있습니다.  또한 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 메서드를 사용하여 위치, 글꼴 및 서식을 지정할 수 있습니다.  [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]와 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 중 하나를 선택하여 텍스트를 렌더링할 수 있지만 일반적으로 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]가 성능이 더 좋으며 텍스트 맞춤도 정확합니다.  텍스트 렌더링에 사용되는 다른 클래스로는 `FontFamily`, `Font`, <xref:System.Drawing.StringFormat> 및 `TextFormatFlags`가 있습니다.  
  
## 단원 내용  
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 `Font` 및 `FontFamily` 개체를 만드는 방법을 보여 줍니다.  
  
 [방법: 지정된 위치에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]를 사용하여 특정 위치에 텍스트를 그리는 방법을 설명합니다.  
  
 [방법: 사각형 안에 줄 바꿈된 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]를 사용하여 사각형에 텍스트를 그리는 방법을 설명합니다.  
  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]를 사용하여 텍스트를 그리는 방법을 보여 줍니다.  
  
 [방법: 그린 텍스트 맞추기](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트의 서식을 지정하는 방법을 보여 줍니다.  
  
 [방법: 세로 텍스트 만들기](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 세로로 맞춰진 텍스트를 그리는 방법을 설명합니다.  
  
 [방법: 그린 텍스트에 탭 정지 설정](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 탭 정지가 있는 텍스트를 그리는 방법을 보여 줍니다.  
  
 [방법: 설치된 글꼴 열거](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 설치된 글꼴의 이름을 나열하는 방법을 설명합니다.  
  
 [방법: 개인 글꼴 컬렉션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <xref:System.Drawing.Text.PrivateFontCollection> 개체를 만드는 방법을 설명합니다.  
  
 [방법: 글꼴 메트릭 얻기](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 셀 어센더 및 디센더와 같은 글꼴 메트릭을 가져오는 방법을 보여 줍니다.  
  
 [방법: 텍스트에 앤티 앨리어싱 사용](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 텍스트를 그릴 때 앤티 앨리어싱을 사용하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Drawing.Font>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Drawing.FontFamily>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.