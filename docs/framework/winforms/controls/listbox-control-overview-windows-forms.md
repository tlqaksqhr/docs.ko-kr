---
title: "ListBox 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e73d76a2d9b31a87bf5a693b5ffa387d7ab5cef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListBox> 컨트롤 사용자 하나 이상의 항목을 선택할 수 있는 목록을 표시 합니다. 스크롤 막대에 자동으로 추가 됩니다 총 항목 수가 표시 될 수 있는 수를 초과 하면는 <xref:System.Windows.Forms.ListBox> 제어 합니다. 경우는 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `true`, 여러 열에 있는 항목을 표시 하는 목록 상자 및 가로 스크롤 막대가 나타납니다. 경우는 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `false`, 단일 열에 있는 항목을 표시 하는 목록 상자 및 세로 스크롤 막대가 나타납니다. 때 <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> 로 설정 된 `true`, 항목 수에 관계 없이 스크롤 막대가 나타납니다. <xref:System.Windows.Forms.ListBox.SelectionMode%2A> 속성 결정 목록 항목의 수를 한 번에 선택할 수 있습니다.  
  
## <a name="ways-to-change-the-listbox-control"></a>ListBox 컨트롤을 변경 하는 방법  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 속성 목록 상자에서 선택한 첫 번째 항목에 해당 하는 정수 값을 반환 합니다. 선택한 항목을 변경 하 여 프로그래밍 방식으로 변경할 수 있습니다는 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 코드에서 값; 목록에서 해당 항목을 Windows Form에 강조 표시 됩니다. 선택 된 항목이 있는 경우는 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은-1입니다. 목록에서 첫 번째 항목을 선택 하는 경우는 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 0입니다. 여러 항목을 선택 하는 경우는 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 선택된 목록에 첫 번째로 표시 된 항목을 반영 합니다. <xref:System.Windows.Forms.ListBox.SelectedItem%2A> 속성은 비슷하지만 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, 문자열 값을 일반적으로 항목 자체를 반환 합니다. <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성 목록에 있는 항목의 수와 값은 반영 된 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성은 항상 하나 이상 가장 큰 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 때문에 값 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 는 0부터 시작 합니다.  
  
 에 항목을 추가 하거나 삭제할는 <xref:System.Windows.Forms.ListBox> 컨트롤을 사용 하 여는 <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> 또는 <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> 메서드. 사용 하 여 목록에 항목을 추가할 수는 또한는 <xref:System.Windows.Forms.ListBox.Items%2A> 디자인 타임에 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListBox>  
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [ComboBox 컨트롤 개요](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [옵션 목록 표시에 사용된 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
