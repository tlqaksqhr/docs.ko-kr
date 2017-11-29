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
ms.openlocfilehash: ac74e50eb6558c38d46714dd7bfe0cfd61133ac8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="d0731-102">방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화</span><span class="sxs-lookup"><span data-stu-id="d0731-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="d0731-103">다음 절차에서는 <xref:System.Windows.Forms.ToolStripLabel> 와 <xref:System.Windows.Forms.ToolStripComboBox> 를 삭제할 수 있습니다 방문한 웹 사이트와 같은 최근에 항목 목록이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="d0731-104">목록의 항목 중 하나의 첫 번째 문자를 일치 하는 문자를 입력 하는 경우의 항목이 즉시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0731-105">자동 완성 연동 `ToolStrip` 와 같은 기존 컨트롤 사용 방식과 동일한 방식으로 컨트롤 <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="d0731-106">ToolStrip 컨트롤에 자동 완성을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0731-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="d0731-107">만들기는 <xref:System.Windows.Forms.ToolStrip> 제어 하 고 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
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
  
2.  <span data-ttu-id="d0731-108">설정의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 레이블과 콤보 상자를 속성 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 목록은 항상 폼의 크기에 관계 없이 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
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
  
3.  <span data-ttu-id="d0731-109">단어의 항목 컬렉션에 추가 <xref:System.Windows.Forms.ToolStripComboBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4.  <span data-ttu-id="d0731-110">설정의 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 속성 콤보 상자의 <xref:System.Windows.Forms.AutoCompleteMode.Append>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5.  <span data-ttu-id="d0731-111">설정의 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 속성 콤보 상자의 <xref:System.Windows.Forms.AutoCompleteSource.ListItems>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0731-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d0731-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0731-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripLabel>  
 <xref:System.Windows.Forms.ToolStripComboBox>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>  
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>  
 [<span data-ttu-id="d0731-113">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d0731-113">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="d0731-114">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d0731-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="d0731-115">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="d0731-115">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
