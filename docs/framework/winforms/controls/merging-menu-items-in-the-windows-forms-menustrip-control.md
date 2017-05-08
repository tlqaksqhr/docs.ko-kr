---
title: "Windows Forms MenuStrip 컨트롤의 메뉴 항목 병합 | Microsoft Docs"
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
  - "MenuStrip, 병합"
  - "병합, 일반 개념"
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Windows Forms MenuStrip 컨트롤의 메뉴 항목 병합
MDI\(다중 문서 인터페이스\) 응용 프로그램의 경우 자식 폼의 메뉴 항목이나 전체 메뉴를 부모 폼의 메뉴에 병합할 수 있습니다.  
  
 이 항목에서는 MDI 응용 프로그램의 메뉴 항목을 병합하는 데 관련된 기본 개념을 설명합니다.  
  
## 일반 개념  
 병합 과정에는 대상 컨트롤과 소스 컨트롤이 모두 포함됩니다.  
  
-   대상은 메뉴 항목을 병합할 기본 또는 MDI 부모 폼에 있는 <xref:System.Windows.Forms.MenuStrip> 컨트롤입니다.  
  
-   소스는 대상 메뉴에 병합할 메뉴 항목이 들어 있는 MDI 자식 폼의 <xref:System.Windows.Forms.MenuStrip> 컨트롤입니다.  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성은 현재 MDI 부모 폼의 MDI 자식에 대한 제목으로 채울 드롭다운 목록이 있는 메뉴 항목을 식별합니다.  예를 들어, 현재 열려 있는 MDI 자식 목록을 일반적으로 **창** 메뉴에 표시합니다.  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> 속성은 MDI 자식 폼의 <xref:System.Windows.Forms.MenuStrip>에서 가져온 메뉴 항목을 식별합니다.  
  
 수동으로 또는 자동으로 메뉴 항목을 병합할 수 있습니다.  어느 방법을 사용하든 메뉴 항목이 병합되는 방식은 동일하지만 병합이 활성화되는 방식은 각기 다릅니다. 자세한 내용은 이 항목의 "수동 병합" 및 "자동 병합" 설명을 참조하십시오.  수동 병합이나 자동 병합 모두, 각 병합 작업은 다음 병합 작업에 영향을 줍니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 병합은 <xref:System.Windows.Forms.MainMenu>에서와 같이 메뉴 항목을 복제하는 것이 아니라 다른 <xref:System.Windows.Forms.ToolStrip>으로 이동합니다.  
  
## MergeAction 값  
 <xref:System.Windows.Forms.MergeAction> 속성을 사용하여 소스 <xref:System.Windows.Forms.MenuStrip>의 메뉴 항목에 대한 병합 작업을 설정할 수 있습니다.  
  
 다음 표에서는 사용할 수 있는 병합 작업의 의미와 일반적인 용도를 설명합니다.  
  
|MergeAction 값|설명|일반적인 용도|  
|-------------------|--------|-------------|  
|<xref:System.Windows.Forms.MergeAction>|기본값. 소스 항목을 대상 항목 컬렉션의 끝에 추가합니다.|프로그램의 일부분이 활성화될 때 메뉴 끝에 메뉴 항목을 추가하는 데 사용합니다.|  
|<xref:System.Windows.Forms.MergeAction>|대상 항목 컬렉션에서 소스 항목에 설정된 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성에 의해 지정된 위치에 소스 항목을 추가합니다.|프로그램의 일부분이 활성화될 때 메뉴의 중간이나 처음에 메뉴 항목을 추가하는 데 사용합니다.<br /><br /> 두 메뉴 항목의 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값이 같으면 역순으로 메뉴 항목이 추가됩니다.  원래 순서를 유지하려면 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>를 적절하게 설정합니다.|  
|<xref:System.Windows.Forms.MergeAction>|일치하는 텍스트를 찾거나 일치하는 텍스트가 없을 경우 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용한 다음 일치하는 대상 메뉴 항목을 소스 메뉴 항목으로 바꿉니다.|대상 메뉴 항목을 이름은 같지만 기능이 다른 소스 메뉴 항목으로 바꾸는 데 사용합니다.|  
|<xref:System.Windows.Forms.MergeAction>|일치하는 텍스트를 찾거나 일치하는 텍스트가 없을 경우 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용한 다음 소스의 모든 드롭다운 항목을 대상에 추가합니다.|메뉴 항목을 하위 메뉴에 삽입 또는 추가하거나 하위 메뉴에서 메뉴 항목을 제거하는 메뉴 구조를 만드는 데 사용합니다.  예를 들어, MDI 자식의 메뉴 항목을 기본 <xref:System.Windows.Forms.MenuStrip>의 **다른 이름으로 저장** 메뉴에 추가할 수 있습니다.<br /><br /> <xref:System.Windows.Forms.MergeAction>를 사용하면 별도의 작업 없이 메뉴 구조를 탐색할 수 있으므로  다음에 나오는 항목을 쉽게 확인할 수 있습니다.|  
|<xref:System.Windows.Forms.MergeAction>|일치하는 텍스트를 찾거나 일치하는 텍스트가 없을 경우 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용한 다음 해당 항목을 대상에서 제거합니다.|대상 <xref:System.Windows.Forms.MenuStrip>에서 메뉴 항목을 제거하는 데 사용합니다.|  
  
## 수동 병합  
 자동 병합은 <xref:System.Windows.Forms.MenuStrip> 컨트롤에만 사용할 수 있습니다.  <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip> 등의 다른 컨트롤에 있는 항목을 병합하려면 필요에 따라 코드에서 <xref:System.Windows.Forms.ToolStripManager.Merge%2A> 및 <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> 메서드를 호출하여 수동으로 병합해야 합니다.  
  
## 자동 병합  
 소스 폼을 활성화하여 MDI 응용 프로그램에 대한 자동 병합 기능을 사용할 수 있습니다.  MDI 응용 프로그램에서 <xref:System.Windows.Forms.MenuStrip>을 사용하려면 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성을 대상 <xref:System.Windows.Forms.MenuStrip>으로 설정하여 소스 <xref:System.Windows.Forms.MenuStrip>에 대해 수행되는 병합 작업이 대상 <xref:System.Windows.Forms.MenuStrip>에 반영되도록 합니다.  
  
 MDI 소스에서 <xref:System.Windows.Forms.MenuStrip>을 활성화하여 자동 병합을 트리거할 수 있습니다.  활성화되면 소스 <xref:System.Windows.Forms.MenuStrip>이 MDI 대상에 병합됩니다.  새 폼이 활성화되면 마지막 폼에 대해 수행된 병합이 되돌려지고 새 폼에 대해 병합이 수행됩니다.  각 <xref:System.Windows.Forms.ToolStripItem>에서 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 속성을 필요한 대로 설정하고 각 <xref:System.Windows.Forms.MenuStrip>에서 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 설정하여 이 동작을 제어할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [방법: MenuStrip이 포함된 MDI 창 목록 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)   
 [방법: MDI 응용 프로그램의 자동 메뉴 병합 설정](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)