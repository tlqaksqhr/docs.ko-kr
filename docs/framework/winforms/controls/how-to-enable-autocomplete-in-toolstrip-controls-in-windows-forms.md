---
title: "방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화 | Microsoft Docs"
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
  - "자동 완성, 도구 모음에서 활성화"
  - "자동 완성, 예제"
  - "예제[Windows Forms], 도구 모음"
  - "도구 모음[Windows Forms], 자동 완성"
  - "ToolStrip 컨트롤[Windows Forms], 자동 완성"
  - "ToolStripComboBox 클래스, 예제"
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화
다음 절차에서는 최근에 방문한 웹 사이트처럼 드롭다운하여 항목의 목록을 표시할 수 있는 <xref:System.Windows.Forms.ToolStripComboBox>와 <xref:System.Windows.Forms.ToolStripLabel>을 함께 사용합니다.  목록에 있는 항목의 첫 문자와 일치하는 문자를 입력하면 해당 항목이 바로 표시됩니다.  
  
> [!NOTE]
>  자동 완성 기능은 <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.TextBox>와 같은 일반적인 컨트롤에서 작동하는 방식과 동일한 방식으로 `ToolStrip`에서 작동합니다.  
  
### ToolStrip 컨트롤에서 자동 완성 기능을 활성화하려면  
  
1.  <xref:System.Windows.Forms.ToolStrip> 컨트롤을 만들고 여기에 항목을 추가합니다.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
  
    ```  
  
2.  폼의 크기에 관계없이 목록이 항상 사용 가능하도록 레이블과 콤보 상자의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemOverflow>로 설정합니다.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
3.  <xref:System.Windows.Forms.ToolStripComboBox> 컨트롤의 Items 컬렉션에 단어를 추가합니다.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
  
    ```  
  
4.  콤보 상자의 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 속성을 <xref:System.Windows.Forms.AutoCompleteMode>로 설정합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
  
    ```  
  
5.  콤보 상자의 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 속성을 <xref:System.Windows.Forms.AutoCompleteSource>로 설정합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripLabel>   
 <xref:System.Windows.Forms.ToolStripComboBox>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)