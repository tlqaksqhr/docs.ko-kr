---
title: "방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7bbae29cea265fbc4cd92213066198b3f721c01d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화
다음 절차에서는 <xref:System.Windows.Forms.ToolStripLabel> 와 <xref:System.Windows.Forms.ToolStripComboBox> 를 삭제할 수 있습니다 방문한 웹 사이트와 같은 최근에 항목 목록이 표시 합니다. 목록의 항목 중 하나의 첫 번째 문자를 일치 하는 문자를 입력 하는 경우의 항목이 즉시 표시 됩니다.  
  
> [!NOTE]
>  자동 완성 연동 `ToolStrip` 와 같은 기존 컨트롤 사용 방식과 동일한 방식으로 컨트롤 <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.TextBox>합니다.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>ToolStrip 컨트롤에 자동 완성을 사용 하도록 설정 하려면  
  
1.  만들기는 <xref:System.Windows.Forms.ToolStrip> 제어 하 고 항목을 추가 합니다.  
  
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
  
2.  설정의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 레이블과 콤보 상자를 속성 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 목록은 항상 폼의 크기에 관계 없이 사용할 수 있도록 합니다.  
  
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
  
3.  단어의 항목 컬렉션에 추가 <xref:System.Windows.Forms.ToolStripComboBox> 제어 합니다.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4.  설정의 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 속성 콤보 상자의 <xref:System.Windows.Forms.AutoCompleteMode.Append>합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5.  설정의 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 속성 콤보 상자의 <xref:System.Windows.Forms.AutoCompleteSource.ListItems>합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripLabel>  
 <xref:System.Windows.Forms.ToolStripComboBox>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
