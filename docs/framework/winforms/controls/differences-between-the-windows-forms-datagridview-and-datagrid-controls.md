---
title: "Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점 | Microsoft Docs"
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
  - "데이터 표"
  - "DataGrid 컨트롤[Windows Forms], DataGridView 컨트롤 비교"
  - "DataGridView 컨트롤[Windows Forms], DataGrid 컨트롤 비교"
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점
<xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하는 새 컨트롤입니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 없는 다양한 기본 기능 및 고급 기능을 제공합니다.  또한 <xref:System.Windows.Forms.DataGridView> 컨트롤의 아키텍처를 사용하면 <xref:System.Windows.Forms.DataGrid> 컨트롤보다 훨씬 용이하게 확장 및 사용자 지정할 수 있습니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 없고 <xref:System.Windows.Forms.DataGridView> 컨트롤에서만 사용할 수 있는 몇 가지 주요 기능을 설명합니다.  
  
|DataGridView 컨트롤 기능|설명|  
|-------------------------|--------|  
|여러 가지 열 형식|<xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤보다 다양한 열 형식을 기본적으로 제공합니다.  이러한 열 형식은 가장 일반적인 시나리오의 요구 사항을 만족하며 <xref:System.Windows.Forms.DataGrid> 컨트롤의 열 형식보다 훨씬 용이하게 확장 또는 대체할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)을 참조하십시오.|  
|데이터를 표시하는 여러 가지 방법|<xref:System.Windows.Forms.DataGrid> 컨트롤은 외부 데이터 소스의 데이터만 표시하도록 제한되어 있습니다.  그러나 <xref:System.Windows.Forms.DataGridView> 컨트롤은 컨트롤에 저장된 바인딩되지 않은 데이터, 바인딩된 데이터 소스의 데이터 또는 바인딩되거나 바인딩되지 않은 데이터를 함께 표시할 수 있습니다.  또한 <xref:System.Windows.Forms.DataGridView> 컨트롤에 가상 모드를 구현하여 사용자 지정 데이터 관리를 제공할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)를 참조하십시오.|  
|데이터가 표시되는 방식을 사용자 지정하는 여러 가지 방법|<xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 형식 지정 및 표시 방법을 지정할 수 있는 여러 가지 속성과 이벤트를 제공합니다.  예를 들어, 셀, 행 및 열에 포함된 데이터에 따라 이들의 모양을 변경하거나 한 데이터 형식의 데이터를 다른 형식의 같은 데이터로 바꿀 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)을 참조하십시오.|  
|셀, 행, 열, 머리글의 모양 및 동작을 변경하는 여러 가지 옵션|<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 개별 표 구성 요소를 다양한 방법으로 사용할 수 있습니다.  예를 들어, 행 및 열을 스크롤되지 않도록 고정하거나, 행, 열 및 머리글을 숨기거나, 행, 열 및 머리글 크기 조정 방식을 변경하거나, 사용자가 선택하는 방법을 변경하거나, 개별 셀, 행 및 열에 대한 도구 설명과 바로 가기 메뉴를 제공할 수 있습니다.|  
  
 <xref:System.Windows.Forms.DataGrid> 컨트롤은 이전 버전과의 호환성 및 특별한 경우를 위해 그대로 유지되었습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤은 거의 모든 용도에 사용됩니다.  그러나 단일 컨트롤에서 서로 관련된 두 테이블의 정보를 계층적으로 표시하는 기능은 <xref:System.Windows.Forms.DataGrid> 컨트롤에서만 사용할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서는 이 기능을 사용할 수 없습니다.  마스터\/세부 사항 관계에 있는 두 테이블의 정보를 표시하려면 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용해야 합니다.  
  
## DataGridView 컨트롤로 업그레이드  
 간단한 데이터 바인딩 시나리오에서 사용자 지정 없이 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용하는 기존 응용 프로그램이 있는 경우 간단하게 기존 컨트롤을 새 컨트롤로 바꿀 수 있습니다.  두 컨트롤 모두 표준 Windows Forms 데이터 바인딩 아키텍처를 사용하므로 <xref:System.Windows.Forms.DataGridView> 컨트롤이 추가 구성 없이 바인딩된 데이터를 표시합니다.  데이터 바인딩의 향상된 기능을 사용하려면 데이터를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩합니다.  자세한 내용은 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 아키텍처는 완전히 새로운 것이기 때문에 <xref:System.Windows.Forms.DataGrid> 사용자 지정을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 사용할 수 있도록 직접 변환하는 방법은 없습니다.  그러나 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기본 제공 기능에는 <xref:System.Windows.Forms.DataGrid> 사용자 지정을 대신하는 여러 가지 기능이 있으므로 이러한 사용자 지정을 사용할 필요가 없습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에 사용할 <xref:System.Windows.Forms.DataGrid> 컨트롤의 사용자 지정 열 형식을 만들었다면 새 아키텍처를 사용하여 이 열 형식을 다시 구현해야 합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Windows.Forms.BindingSource>   
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 열 정렬 모드](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 선택 모드](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)