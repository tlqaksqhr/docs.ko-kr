---
title: "Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 표, 서식 지정"
  - "DataGridView 컨트롤[Windows Forms], 형식 및 스타일 지정"
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정
`DataGridView` 컨트롤을 사용하면 셀의 기본 모양과 셀 값의 표시 형식을 쉽게 정의할 수 있습니다.  다양한 `DataGridView` 컨트롤 속성을 통해 액세스할 수 있는 `DataGridViewCellStyle` 개체의 속성을 설정하여 개별 셀이나, 특정 열과 행에 있는 셀 또는 컨트롤에 있는 모든 셀에 대해 모양과 서식 스타일을 정의할 수 있습니다.  또한 `CellFormatting` 이벤트를 처리하여 셀 값과 같은 요소를 기준으로 이러한 스타일을 동적으로 수정할 수 있습니다.  
  
## 단원 내용  
 [방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 컨트롤 테두리 모양과 셀 간의 경계선 모양을 정의하는 `DataGridView` 속성을 설정하는 방법을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 `DataGridViewCellStyle` 클래스에 대해 설명하고, 셀이 컨트롤에 표시되는 방법을 정의하기 위해 해당 형식의 속성이 상호 작용하는 방식을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 `DataGridViewCellStyle` 속성을 사용하여 특정 행과 열 및 전체 컨트롤에 있는 셀의 기본 모양을 정의하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 `DataGridViewCellStyle` 속성을 사용하여 셀 표시 값의 서식을 지정하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 `DefaultCellStyle` 속성을 사용하여 컨트롤의 모든 셀에 대한 기본 표시 특성을 설정하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 서로 다르게 표시되는 교대로 반복되는 행을 사용하여 컨트롤에 장부와 비슷한 효과를 만드는 방법을 설명합니다.  
  
 [방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 `RowTemplate` 속성을 사용하여 컨트롤의 모든 행에 사용될 행 속성을 설정하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> 속성에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성에 대한 참조 설명서를 제공합니다.  
  
## 관련 단원  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <xref:System.Windows.Forms.DataGridView> 셀과 행을 사용자 지정 방식으로 그리는 방법과 파생 셀, 열 및 행 형식을 만드는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 주로 사용되는 셀, 행 및 열 속성을 설명하는 항목을 제공합니다.  
  
## 참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)