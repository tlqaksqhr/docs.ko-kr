---
title: "방법: MenuStrip에 옵션 단추 표시(Windows Forms) | Microsoft Docs"
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
  - "옵션 단추 표시, MenuStrip[Windows Forms]"
  - "MenuStrip[Windows Forms], 옵션 단추 표시"
  - "옵션 단추[Windows Forms], MenuStrip에 표시"
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: MenuStrip에 옵션 단추 표시(Windows Forms)
라디오 단추라고도 하는 옵션 단추는 한 번에 하나만 선택할 수 있다는 점만 제외하면 확인란과 비슷합니다.  기본적으로 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스에서는 옵션 단추 동작을 제공하지 않지만 확인란 동작을 제공하므로 이를 사용자 지정하여 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 메뉴 항목에 대한 옵션 단추 동작을 구현할 수 있습니다.  
  
 메뉴 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성이 `true`이면 사용자가 해당 항목을 클릭하여 확인 표시를 표시하거나 숨길 수 있습니다.  <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성은 항목의 현재 상태를 나타냅니다.  기본 옵션 단추 동작을 구현하려면 항목이 선택될 때 이전에 선택된 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성이 `false`로 설정되도록 해야 합니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스를 상속하는 클래스에서 이 기능과 추가 기능을 구현하는 방법을 설명합니다.  `ToolStripRadioButtonMenuItem` 클래스는 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>와 같은 멤버를 재정의하여 옵션 단추의 선택 동작 및 모양을 제공합니다.  또한 이 클래스는 부모 항목이 선택되지 않은 경우 하위 메뉴의 옵션을 사용할 수 없도록 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 재정의합니다.  
  
### 옵션 단추 선택 동작을 구현하려면  
  
1.  <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`로 초기화하여 항목 선택 기능을 설정합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  새 항목이 선택될 때 이전에 선택된 항목의 선택 상태를 해제하도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  이미 선택한 항목을 클릭해도 선택 상태가 해제되지 않도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### 옵션 단추 항목의 모양을 수정하려면  
  
1.  <xref:System.Windows.Forms.RadioButtonRenderer> 클래스를 사용하여 기본 확인 표시를 옵션 단추로 바꾸도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  마우스의 상태를 추적하고 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드로 올바른 옵션 단추 상태를 그릴 수 있도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### 부모 항목이 선택되지 않았을 때 하위 메뉴의 옵션을 사용할 수 없도록 하려면  
  
1.  부모 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 값이 `true`이고 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 값이 `false`일 때 해당 하위 메뉴 항목을 사용할 수 없도록 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  부모 항목의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트를 구독하도록 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  부모 항목 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트의 처리기에서 항목을 무효화하여 표시 상태를 새로 설정된 상태로 업데이트합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## 예제  
 다음 코드 예제에서는 `ToolStripRadioButtonMenuItem` 클래스 전체와 옵션 단추 동작을 보여 주기 위한 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스를 제공합니다.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RadioButtonRenderer>   
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [방법: 사용자 지정 ToolStripRenderer 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)