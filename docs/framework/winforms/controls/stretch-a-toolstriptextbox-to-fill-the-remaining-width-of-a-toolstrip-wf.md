---
title: "방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms) | Microsoft Docs"
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
  - "텍스트 상자, ToolStrip 컨트롤에서 늘이기[Windows Forms]"
  - "ToolStrip 컨트롤[Windows Forms], 텍스트 상자 늘이기"
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)
<xref:System.Windows.Forms.ToolStrip> 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성을 `true`로 설정하면 이 컨트롤이 컨테이너의 한 쪽 끝에서 다른 쪽 끝까지 채워지고 컨테이너 크기가 조정될 때 이 컨트롤의 크기도 조정됩니다.  이 구성에서 컨트롤 크기가 조정되면 <xref:System.Windows.Forms.ToolStripTextBox>와 같은 컨트롤 안의 항목을 늘려 사용할 수 있는 공간을 채우고 크기를 조정하는 것이 유용할 수 있습니다.  예를 들어, Microsoft® Internet Explorer의 주소 표시줄과 비슷한 모양 및 동작을 구현하려는 경우에 이렇게 항목을 늘리면 유용합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripTextBox>에서 파생된 `ToolStripSpringTextBox`라는 클래스를 제공합니다.  이 클래스는 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 메서드를 재정의하여 다른 모든 항목의 총 너비를 뺀 후 부모 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 사용 가능한 너비를 계산합니다.  이 코드 예제에서는 새로운 동작을 보여 주기 위해 <xref:System.Windows.Forms.Form> 클래스와 `Program` 클래스도 제공합니다.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripTextBox>   
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=fullName>   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [방법: StatusStrip에서 대화형으로 Spring 속성 사용](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)