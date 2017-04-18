---
title: "Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용 | Microsoft Docs"
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
  - "셀, 표에서 선택"
  - "클립보드, DataGridView 컨트롤"
  - "데이터 표, 셀 선택"
  - "DataGridView 컨트롤[Windows Forms], 클립보드 사용"
  - "DataGridView 컨트롤[Windows Forms], 셀 선택"
  - "선택, DataGridView 컨트롤"
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용
`DataGridView` 컨트롤은 사용자가 셀, 행 및 열을 선택하는 방법을 구성할 수 있는 다양한 옵션을 제공합니다.  예를 들어, 단일 또는 다중 선택을 활성화하거나, 사용자가 셀을 클릭할 때 전체 행 또는 열이 선택되도록 하거나, 사용자가 머리글을 클릭할 때만 전체 행 또는 열이 선택되어 셀을 선택할 수 있도록 할 수 있습니다.  선택 기능에 대한 자체적인 사용자 인터페이스를 제공하려면 일반적인 선택을 비활성화하고 모든 선택을 프로그래밍 방식으로 처리하면 됩니다.  또한 사용자가 선택한 값을 클립보드에 복사하도록 할 수 있습니다.  
  
## 단원 내용  
 [Windows Forms DataGridView 컨트롤의 선택 모드](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 사용자 및 프로그래밍 방식의 선택 기능에 대한 옵션을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 사용자가 한 개의 셀을 클릭할 때 단일 행 선택에 대한 컨트롤을 구성하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 선택한 셀, 행 및 열 컬렉션을 처리하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 컨트롤에서 클립보드 지원을 활성화하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 속성에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 클래스에 대한 참조 설명서를 제공합니다.  
  
## 참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)