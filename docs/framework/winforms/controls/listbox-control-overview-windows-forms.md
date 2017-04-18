---
title: "ListBox 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "ListBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "목록 상자, 목록 상자 정보"
  - "ListBox 컨트롤[Windows Forms], ListBox 컨트롤 정보"
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ListBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListBox> 컨트롤은 사용자가 하나 이상의 항목을 선택할 수 있는 목록을 표시합니다.  표시할 수 있는 수보다 전체 항목 수가 많으면 <xref:System.Windows.Forms.ListBox> 컨트롤에 자동으로 스크롤 막대가 추가됩니다.  <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `true`로 설정된 경우에는 목록 상자의 항목이 여러 열에 표시되고 가로 스크롤 막대가 나타납니다.  또한 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `false`로 설정된 경우에는 목록 상자의 항목이 단일 열에 표시되고 세로 스크롤 막대가 나타납니다.  <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A>이 `true`로 설정되어 있으면 항목 수에 관계없이 스크롤 막대가 나타납니다.  <xref:System.Windows.Forms.ListBox.SelectionMode%2A> 속성은 한 번에 선택할 수 있는 항목의 수를 결정합니다.  
  
## ListBox 컨트롤 변경 방법  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 속성은 목록 상자에서 처음 선택한 항목에 해당하는 정수 값을 반환합니다.  코드에서 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값을 변경하면 선택한 항목을 프로그래밍 방식으로 변경할 수 있으며 목록의 해당 항목이 Windows Form에서 강조되어 나타납니다.  항목이 선택되지 않은 경우 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 \-1입니다.  목록의 첫 번째 항목이 선택되지 않은 경우 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 0입니다.  여러 항목을 선택하면 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 목록에 처음 나타나는 선택한 항목을 반영합니다.  <xref:System.Windows.Forms.ListBox.SelectedItem%2A> 속성은 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>와 비슷하지만 대개 문자열 값인 항목 자체를 반환합니다.  <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성은 목록의 항목 개수를 반영하며 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>가 0부터 시작하기 때문에 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성의 값은 최대 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값보다 항상 1이 더 큽니다.  
  
 <xref:System.Windows.Forms.ListBox> 컨트롤에서 항목을 추가하거나 삭제하려면 <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> 또는 <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> 메서드를 사용합니다.  또한 디자인 타임에 <xref:System.Windows.Forms.ListBox.Items%2A> 속성을 사용하여 목록에 항목을 추가할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListBox>   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [ComboBox 컨트롤 개요](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [CheckedListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)