---
title: "방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화 | Microsoft Docs"
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
  - "AllowItemReorder 속성"
  - "예제[Windows Forms], 도구 모음"
  - "도구 모음[Windows Forms], 컨트롤 다시 정렬"
  - "ToolStrip 컨트롤[Windows Forms], 예제"
  - "ToolStrip 컨트롤[Windows Forms], 항목 다시 정렬"
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화
사용자가 <xref:System.Windows.Forms.ToolStrip>에서 <xref:System.Windows.Forms.ToolStripItem> 컨트롤을 다시 정렬하도록 할 수 있습니다.  
  
### 런타임에 ToolStripItem 다시 정렬 기능을 활성화하려면  
  
-   <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`으로 설정합니다.  <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>의 기본값은 `false`입니다.  
  
     런타임에 Alt 키를 누른 채 마우스 왼쪽 단추를 클릭하면 <xref:System.Windows.Forms.ToolStripItem>을 <xref:System.Windows.Forms.ToolStrip>의 다른 위치로 끌 수 있습니다.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)