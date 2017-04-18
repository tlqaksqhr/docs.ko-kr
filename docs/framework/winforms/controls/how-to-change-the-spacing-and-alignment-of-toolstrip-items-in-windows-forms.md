---
title: "방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 모음"
  - "도구 모음[Windows Forms], 항목 맞춤"
  - "ToolStrip 컨트롤[Windows Forms], 항목 맞춤"
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경
<xref:System.Windows.Forms.ToolStrip> 컨트롤은 크기 조정, 다른 컨트롤을 기준으로 하는 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 간격 조정, <xref:System.Windows.Forms.ToolStrip>의 컨트롤 배열 및 <xref:System.Windows.Forms.ToolStrip>을 기준으로 하는 컨트롤의 간격 조정과 같은 모든 레이아웃 기능을 지원합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성의 기본값이 `true`이므로 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`로 설정하지 않으면 컨트롤의 크기가 자동으로 조정됩니다.  
  
### ToolStripItem의 크기를 수동으로 조정하려면  
  
1.  연결된 컨트롤의 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`로 설정합니다.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
  
    ```  
  
2.  연결된 <xref:System.Windows.Forms.ToolStripItem>에 대해 원하는 방식으로 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 속성을 설정합니다.  
  
### ToolStripItem의 간격을 설정하려면  
  
1.  연결된 컨트롤의 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성에 원하는 값을 픽셀 단위로 삽입합니다.  
  
     <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성의 값은 항목과 인접 항목 간의 간격을 왼쪽, 위쪽, 오른쪽, 아래쪽의 순서로 지정합니다.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
  
    ```  
  
### ToolStripItem을 ToolStrip의 오른쪽에 맞추려면  
  
1.  연결된 컨트롤의 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemAlignment>로 설정합니다.  <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>의 기본 설정은 <xref:System.Windows.Forms.ToolStripItemAlignment>이므로, 컨트롤이 <xref:System.Windows.Forms.ToolStrip>의 왼쪽에 맞춰집니다.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
  
    ```  
  
### ToolStrip에서 ToolStrip 항목을 정렬하려면  
  
-   <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성을 원하는 <xref:System.Windows.Forms.ToolStripLayoutStyle> 값으로 설정합니다.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.Control.Layout>   
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>   
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>   
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)