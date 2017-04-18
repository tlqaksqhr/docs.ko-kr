---
title: "방법: Windows Forms의 ToolStrip 오버플로 관리 | Microsoft Docs"
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
  - "CanOverflow 속성"
  - "예제[Windows Forms], 도구 모음"
  - "Overflow 속성"
  - "도구 모음[Windows Forms], 오버플로 관리"
  - "ToolStrip 컨트롤[Windows Forms], 오버플로 관리"
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms의 ToolStrip 오버플로 관리
<xref:System.Windows.Forms.ToolStrip> 컨트롤의 항목 중 할당된 공간에 맞지 않는 항목이 있을 경우, <xref:System.Windows.Forms.ToolStrip>에 대해 오버플로 기능을 활성화하고 특정 <xref:System.Windows.Forms.ToolStripItem>의 오버플로 동작을 결정할 수 있습니다.  
  
 지정된 폼의 현재 크기인 <xref:System.Windows.Forms.ToolStrip>에 할당된 크기보다 더 많은 공간이 필요한 <xref:System.Windows.Forms.ToolStripItem>을 추가하면 <xref:System.Windows.Forms.ToolStrip>에 <xref:System.Windows.Forms.ToolStripOverflowButton>이 자동으로 표시됩니다.  <xref:System.Windows.Forms.ToolStripOverflowButton>이 표시되고 오버플로가 활성화된 항목이 드롭다운 오버플로 메뉴로 이동합니다.  따라서 <xref:System.Windows.Forms.ToolStrip> 항목이 서로 다른 폼 크기에 맞게 조정되는 방법을 사용자 지정하고 우선 순위를 결정할 수 있습니다.  또한 항목이 오버플로에 포함될 경우 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 및 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=fullName> 속성과 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 사용하여 해당 항목의 모양을 변경할 수도 있습니다.  디자인 타임이나 런타임에 폼을 확대하면 기본 <xref:System.Windows.Forms.ToolStrip>에 더 많은 <xref:System.Windows.Forms.ToolStripItem>이 표시될 수 있고 폼의 크기를 축소할 때까지는 <xref:System.Windows.Forms.ToolStripOverflowButton>이 표시되지 않을 수도 있습니다.  
  
### ToolStrip 컨트롤에서 오버플로를 활성화하려면  
  
-   <xref:System.Windows.Forms.ToolStrip>에 대해 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 속성이 `false`로 설정되어 있지 않은지 확인합니다.  기본값은 `True`입니다.  
  
     <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>가 `True`\(기본값\)일 경우, <xref:System.Windows.Forms.ToolStripItem>의 내용이 가로 <xref:System.Windows.Forms.ToolStrip>의 너비나 세로 <xref:System.Windows.Forms.ToolStrip>의 높이를 초과하면 <xref:System.Windows.Forms.ToolStripItem>이 드롭다운 오버플로 메뉴로 보내집니다.  
  
### 특정 ToolStripItem의 오버플로 동작을 지정하려면  
  
-   <xref:System.Windows.Forms.ToolStripItem>의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 원하는 값으로 설정합니다.  가능한 값으로는 `Always`, `Never` 및 `AsNeeded`가 있습니다.  The defaultis `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripOverflowButton>   
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)