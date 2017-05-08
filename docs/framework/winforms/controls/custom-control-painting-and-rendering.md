---
title: "사용자 지정 컨트롤 그리기 및 렌더링 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[Windows Forms], 그리기"
  - "사용자 지정 컨트롤[Windows Forms], 렌더링"
  - "OnPaint 메서드"
  - "사용자 정의 컨트롤[Windows Forms], 그리기"
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 사용자 지정 컨트롤 그리기 및 렌더링
컨트롤의 사용자 지정 그리기는 .NET Framework로 쉽게 수행할 수 있는 여러 가지 복잡한 작업 중 하나입니다.  사용자 지정 컨트롤을 제작하면 컨트롤의 그래픽 모양과 관련된 다양한 옵션을 사용할 수 있습니다.  `Control`에서 상속되는 컨트롤을 제작하는 경우 컨트롤의 그래픽 표현을 렌더링할 수 있는 코드를 제공해야 합니다.  `UserControl`에서 상속하거나 Windows Forms 컨트롤 중 하나에서 상속하여 사용자 정의 컨트롤을 만들 경우 표준 그래픽 표현을 재정의하고 고유한 그래픽 코드를 제공할 수 있습니다.  제작 중인 `UserControl`의 구성 요소 컨트롤에 사용자 지정 렌더링을 제공할 경우 옵션은 더욱 제한되지만 컨트롤과 응용 프로그램에 대한 광범위한 그래픽 기능을 계속 사용할 수 있습니다.  
  
## 단원 내용  
 [Windows Forms 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 컨트롤을 표시하는 논리를 프로그래밍하는 방법을 보여 줍니다.  
  
 [사용자가 그린 컨트롤](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 컨트롤의 렌더링 코드를 작성하고 재정의하는 과정을 설명합니다.  
  
 [구성 요소 컨트롤](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 사용자 정의 컨트롤과 폼의 구성 요소 컨트롤에 대한 사용자 지정 렌더링 코드를 구현하는 방법을 설명합니다.  
  
 [방법: 런타임에 컨트롤 숨기기](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 사용하여 컨트롤을 숨기고 표시하는 방법을 보여 줍니다.  
  
 [방법: 컨트롤에 투명한 배경 적용](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 사용하여 불투명하거나, 투명하거나 부분적으로 투명한 배경 색을 만드는 방법을 보여 줍니다.  
  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 비주얼 스타일을 지원하는 운영 체제에서 비주얼 스타일을 사용하여 컨트롤을 렌더링하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.Windows.Forms.Control>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.UserControl>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 이 메서드에 대해 설명합니다.  
  
## 관련 단원  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Visual Studio의 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 그래픽 기능을 소개하고 상세 정보에 대한 링크를 제공합니다.  
  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 제작할 수 있는 다양한 종류의 사용자 지정 컨트롤을 설명합니다.