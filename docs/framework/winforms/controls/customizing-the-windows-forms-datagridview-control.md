---
title: "Windows Forms DataGridView 컨트롤 사용자 지정 | Microsoft Docs"
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
  - "데이터 표, 사용자 지정"
  - "DataGridView 컨트롤[Windows Forms], 사용자 지정"
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms DataGridView 컨트롤 사용자 지정
`DataGridView` 컨트롤에는 컨트롤의 셀, 행 및 열의 모양과 기본 동작\(모양과 느낌\)을 조정하는 데 사용할 수 있는 여러 속성이 있습니다.  그러나 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 기능을 특별히 확장해야 할 필요가 있는 경우에는 사용자 지정 셀, 열 및 행을 만들어서 컨트롤에 대한 소유자 그리기를 구현하거나 컨트롤의 기능을 확장할 수도 있습니다.  
  
 다양한 `DataGridView` 그리기 이벤트를 처리하여 셀과 행을 직접 그릴 수 있습니다.  기존 `DataGridViewCell`, `DataGridViewColumn` 및 `DataGridViewRow` 형식에서 파생된 고유 형식을 만들어서 기존 기능을 수정하거나 새 기능을 제공할 수 있습니다.  또한 셀이 편집 모드에 있을 때 선택한 컨트롤을 표시하는 파생 형식을 만들어서 새 편집 기능을 제공할 수 있습니다.  
  
## 단원 내용  
 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 셀을 수동으로 그리기 위해 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 사용자 지정 그라데이션 배경 및 여러 열에 확장된 내용으로 행을 그리기 위해 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트를 처리하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 마우스 포인터가 셀 위에 있을 때 셀을 강조 표시하기 위해 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생된 사용자 지정 형식을 만드는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 비활성화된 단추를 단추 열에 표시하기 위해 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn>에서 파생된 사용자 지정 형식을 만드는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 `IDataGridViewEditingControl` 인터페이스를 구현하고 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생되는 사용자 지정 형식을 만들어서 셀이 편집 모드에 있을 때 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 표시하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewColumn> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스에 대한 참조 설명서를 제공합니다.  
  
## 관련 단원  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.  
  
## 참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)