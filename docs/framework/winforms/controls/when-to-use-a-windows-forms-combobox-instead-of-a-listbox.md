---
title: "ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우 | Microsoft Docs"
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
  - "바인딩 컨트롤, 콤보 상자"
  - "콤보 상자, 목록 상자와 비교"
  - "ComboBox 컨트롤[Windows Forms], ListBox와 비교"
  - "ListBox 컨트롤[Windows Forms], 항목 액세스"
  - "ListBox 컨트롤[Windows Forms], 항목 추가 및 제거"
  - "ListBox 컨트롤[Windows Forms], ComboBox와 비교"
  - "ListCount 속성"
  - "ListIndex 속성"
  - "Windows Forms 컨트롤, 데이터 바인딩"
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우
<xref:System.Windows.Forms.ComboBox>와 <xref:System.Windows.Forms.ListBox> 컨트롤은 유사하게 동작하며 어떤 경우는 서로 바꿔 사용할 수도 있습니다.  그러나 작업에 따라 두 컨트롤 중 하나가 더 적합한 경우도 있습니다.  
  
 일반적으로 콤보 상자는 추천 목록이 있는 경우에 적합하고 목록 상자는 목록에 대해 항목 입력을 제한하려는 경우에 적합합니다.  콤보 상자에는 텍스트 상자 필드가 있으므로 목록에 없는 항목을 입력할 수 있습니다.  그러나 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle>로 설정되어 있는 경우에는 예외적으로  항목의 첫 글자만 입력하면 컨트롤에서 해당 항목이 자동으로 선택됩니다.  
  
 또한 콤보 상자를 사용하면 폼의 공간을 절약할 수 있습니다.  콤보 상자는 아래쪽 화살표를 클릭하기 전까지는 전체 목록이 표시되지 않기 때문에 목록 상자를 사용하기에는 부적합한 좁은 공간에도 쉽게 맞출 수 있습니다.  그러나 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle>로 설정된 경우는 예외입니다. 이 경우 전체 목록이 표시되기 때문에 콤보 상자가 목록 상자보다 더 많은 공간을 차지합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)