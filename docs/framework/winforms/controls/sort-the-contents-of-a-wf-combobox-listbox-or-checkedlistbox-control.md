---
title: "방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬 | Microsoft Docs"
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
  - "CheckedListBox 컨트롤[Windows Forms], 정렬"
  - "콤보 상자, 내용 정렬"
  - "ComboBox 컨트롤[Windows Forms], 내용 정렬"
  - "목록 상자, 내용 정렬"
  - "ListBox 컨트롤[Windows Forms], 내용 정렬"
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬
Windows Forms 컨트롤은 데이터 바인딩인 경우 정렬하지 않습니다.  정렬된 데이터를 표시하려면 정렬을 지원하는 데이터 소스를 사용하여 데이터를 정렬합니다.  정렬을 지원하는 데이터 소스는 데이터 뷰, 데이터 뷰 관리자 및 정렬된 배열입니다.  
  
 데이터 바인딩되지 않은 컨트롤은 정렬할 수 있습니다.  
  
### 목록을 정렬하려면  
  
1.  `Sorted`  속성을 `true`로 설정합니다.  
  
     이렇게 설정하면 기존의 모든 목록 항목이 정렬 순서로 위치가 변경됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)