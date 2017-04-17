---
title: "DataGridView 컨트롤(Windows Forms) | Microsoft Docs"
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
  - "데이터[Windows Forms], 표 형식으로 표시"
  - "데이터 표"
  - "데이터 표시"
  - "DataGridView 컨트롤[Windows Forms]"
  - "데이터 집합[Windows Forms], DataGridView 컨트롤에 표시"
  - "데이터 집합[Windows Forms], 사용자 인터페이스"
  - "표 컨트롤[Windows Forms]"
  - "테이블[Windows Forms]"
  - "표 형식 데이터, Windows Forms에 표시"
  - "Windows Forms, 데이터 표시"
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# DataGridView 컨트롤(Windows Forms)
`DataGridView` 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.  `DataGridView` 컨트롤을 사용하여 적은 양의 데이터에 대한 읽기 전용 보기를 표시하거나, 컨트롤을 확장하여 매우 큰 데이터 집합에 대한 편집 가능한 보기를 표시할 수 있습니다.  
  
 다양한 방법으로 `DataGridView` 컨트롤을 확장하여 사용자 지정 동작을 응용 프로그램에 빌드할 수 있습니다.  예를 들어 프로그래밍 방식으로 고유한 정렬 알고리즘을 지정하고 고유한 셀 형식을 만들 수도 있습니다.  여러 속성 중에서 선택하여 `DataGridView` 컨트롤의 모양을 쉽게 사용자 지정할 수 있습니다.  대부분 데이터 저장소 형식을 데이터 소스로 사용하거나 `DataGridView` 컨트롤을 바인딩된 데이터 소스 없이 작동할 수 있습니다.  
  
 이 섹션의 항목에서는 `DataGridView` 기능을 응용 프로그램에 빌드하는 데 사용할 수 있는 개념 및 기술을 설명합니다.  
  
## 단원 내용  
 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 Windows Forms `DataGridView` 컨트롤의 아키텍처와 핵심 개념을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 기본 기능](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 데이터 소스에 바인딩될 때 Windows Forms `DataGridView` 컨트롤의 기본 모양과 동작에 대해 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 데이터를 표시하고 사용자가 데이터를 수정 또는 추가할 수 있도록 하는 데 사용되는 Windows Forms `DataGridView` 컨트롤의 열 형식을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 일반적으로 사용되는 셀, 행 및 열 속성을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 수동으로 또는 외부 데이터 소스에서 컨트롤을 데이터로 채우는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 셀 내용에 맞추거나 컨트롤의 사용 가능한 너비에 맞춰서 행 및 열 크기를 자동으로 조정할 수 있는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 데이터 정렬](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 정렬 기능을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 컨트롤의 셀, 행 및 열 선택 기능을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 셀, 행 및 열 개체를 사용하여 프로그래밍하는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 `DataGridView` 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 컨트롤을 효율적으로 사용하여 대용량 데이터를 사용할 때 성능 문제를 방지하는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 사용자가 키보드와 마우스를 통해 `DataGridView` 컨트롤을 조작할 수 있는 방법을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 `DataGridView` 컨트롤로 <xref:System.Windows.Forms.DataGrid> 컨트롤을 개선하고 대체하는 방법을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤에 디자이너 사용](http://msdn.microsoft.com/library/ms171593\(v=vs.110\))을 참조하세요.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소는 서로 긴밀하게 작동하도록 설계되었습니다.  
  
## 참고 항목  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)