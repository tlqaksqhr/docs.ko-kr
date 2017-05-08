---
title: "ComboBox 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComboBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "콤보 상자, 콤보 상자 정보"
  - "ComboBox 컨트롤[Windows Forms], ComboBox 컨트롤 정보"
  - "드롭다운 목록, ComboBox 컨트롤"
  - "드롭다운 목록, Windows Forms"
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# ComboBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ComboBox> 컨트롤은 드롭다운 콤보 상자에 데이터를 표시하는 데 사용됩니다.  기본적으로 <xref:System.Windows.Forms.ComboBox> 컨트롤은 두 부분으로 표시됩니다. 윗 부분은 사용자가 목록 항목을 입력할 수 있는 텍스트 상자이며  아랫 부분은 사용자가 항목을 선택할 수 있는 항목 목록을 표시하는 목록 상자입니다.  다른 스타일의 콤보 상자에 대한 자세한 내용은 [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 속성은 목록에서 선택한 항목에 해당하는 정수 값을 반환합니다.  코드에서 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값을 변경하여 선택한 항목을 프로그래밍 방식으로 변경할 수 있습니다. 그러면 목록의 해당 항목이 콤보 상자의 텍스트 상자 부분에 나타납니다.  선택된 항목이 없는 경우 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>의 값은 –1입니다.  목록의 첫 번째 항목을 선택한 경우 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>의 값은 0입니다.  <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 속성은 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>와 비슷하지만 일반적으로 문자열 값인 항목 자체를 반환합니다.  <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> 속성은 목록의 항목 개수를 반영하며 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>가 0부터 시작하기 때문에 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> 속성의 값은 최대 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값보다 항상 1이 더 큽니다.  
  
 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 항목을 추가하거나 삭제하려면 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> 또는 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> 메서드를 사용합니다.  또는 디자이너에서 <xref:System.Windows.Forms.ComboBox.Items%2A> 속성을 사용하여 항목을 목록에 추가할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 [ListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)   
 [방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)