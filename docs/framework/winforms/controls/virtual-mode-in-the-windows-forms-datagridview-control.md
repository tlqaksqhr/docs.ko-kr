---
title: "Windows Forms DataGridView 컨트롤의 가상 모드 | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 가상 모드"
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Windows Forms DataGridView 컨트롤의 가상 모드
가상 모드를 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤과 사용자 지정 데이터 캐시 간의 상호 작용을 관리할 수 있습니다.  가상 모드를 구현하려면 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정하고 이 항목에서 설명하는 이벤트를 하나 이상 처리합니다.  적어도 컨트롤이 데이터 캐시에서 값을 조회할 수 있게 해주는 `CellValueNeeded` 이벤트를 처리합니다.  
  
## 바인딩된 모드 및 가상 모드  
 가상 모드는 바인딩된 모드를 추가하거나 바꾸는 경우에만 필요합니다.  바인딩된 모드에서 사용자가 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정하면 컨트롤은 지정된 소스에서 데이터를 자동으로 로드하고 이 데이터에 사용자 변경 내용을 다시 전송합니다.  사용자는 표시할 바인딩된 열을 제어할 수 있으며 데이터 소스 자체는 일반적으로 정렬과 같은 작업을 처리합니다.  
  
## 바인딩된 모드 추가  
 바인딩된 열과 함께 바인딩되지 않은 열을 표시하여 바인딩된 모드를 추가할 수 있습니다.  이를 "혼합 모드"라고도 하며 계산된 값 또는 UI\(사용자 인터페이스\) 컨트롤과 같은 것을 표시하는 데 유용합니다.  
  
 바인딩되지 않은 열은 데이터 소스의 외부에 있으므로 데이터 소스 정렬 작업에서 무시됩니다.  따라서 혼합 모드에서의 정렬을 설정한 경우 로컬 캐시에서 바인딩되지 않은 데이터를 관리하고 가상 모드를 구현하여 <xref:System.Windows.Forms.DataGridView> 컨트롤과 상호 작용할 수 있게 해야 합니다.  
  
 가상 모드를 사용하여 바인딩되지 않은 열의 값을 유지 관리하는 방법은 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=fullName> 속성 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName> 클래스 참조 항목의 예제를 참조하십시오.  
  
## 바인딩된 모드 바꾸기  
 바인딩된 모드가 성능 요구 사항을 만족하지 않을 경우 가상 모드 이벤트 처리기를 통해 사용자 지정 캐시의 모든 데이터를 관리할 수 있습니다.  예를 들어, 가상 모드를 사용하여 네트워크로 연결된 데이터베이스에서 최적의 성능을 위해 필요한 만큼의 데이터만 검색하는 Just\-In\-Time 데이터 로드 메커니즘을 구현할 수 있습니다.  이 시나리오는 느린 네트워크 연결을 통해 많은 양의 데이터를 작업해야 하는 경우 또는 RAM이나 저장 공간이 제한적인 클라이언트 컴퓨터에서 작업해야 하는 경우에 특히 유용합니다.  
  
 Just\-In\-Time 시나리오에서 가상 모드를 사용하는 방법은 [Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)을 참조하십시오.  
  
## 가상 모드 이벤트  
 데이터가 읽기 전용인 경우 `CellValueNeeded` 이벤트만 처리하면 됩니다.  가상 모드 이벤트를 추가로 사용하면 사용자 편집, 행 추가 및 삭제, 행 수준 트랜잭션과 같은 특정 기능을 설정할 수 있습니다.  
  
 사용자가 행을 추가하거나 삭제할 때 발생하는 이벤트 또는 셀 값이 편집되거나 구문 분석되는 경우 또는 셀 값의 유효성을 검사하거나 서식이 지정될 때 발생하는 이벤트와 같은 일부 표준 <xref:System.Windows.Forms.DataGridView> 이벤트는 가상 모드에서도 유용합니다.  또한 셀 도구 설명 텍스트, 셀 및 행 오류 텍스트, 셀 및 행 바로 가기 메뉴 데이터, 행 높이 데이터 등과 같이 일반적으로 바인딩된 데이터 소스에 저장되지 않는 값을 관리할 수 있게 해주는 이벤트를 처리할 수 있습니다.  
  
 행 수준 커밋 범위로 읽기\/쓰기 데이터를 관리하는 가상 모드를 구현하는 방법은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
 셀 수준 커밋 범위로 가상 모드를 구현하는 예제는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 참조 항목을 참조하십시오.  
  
 다음 이벤트는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`로 설정된 경우에만 발생합니다.  
  
|Event|설명|  
|-----------|--------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|데이터 캐시에서 표시할 셀 값을 검색하기 위해 컨트롤에서 사용됩니다.  이 이벤트는 바인딩되지 않은 열의 셀에 대해서만 발생합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|셀에 대한 사용자 입력을 데이터 캐시로 커밋하기 위해 컨트롤에서 사용됩니다.  이 이벤트는 바인딩되지 않은 열의 셀에 대해서만 발생합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기 외부의 캐시된 값을 변경할 때 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 메서드를 호출하여 현재 값이 컨트롤에 표시되었는지 확인하고 현재 적용되는 자동 크기 조정 모드를 적용합니다.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|데이터 캐시에 새 행이 필요함을 나타내기 위해 컨트롤에서 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|행에 커밋되지 않은 변경 사항이 있는지 여부를 확인하기 위해 컨트롤에서 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|행을 캐시된 값으로 되돌려야 함을 나타내기 위해 컨트롤에서 사용됩니다.|  
  
 다음 이벤트는 가상 모드에서 유용하지만 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 설정에 관계없이 사용할 수 있습니다.  
  
|이벤트|설명|  
|---------|--------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|행이 삭제 또는 추가되면 그 결과에 따라 데이터 캐시를 업데이트할 수 있도록 허용함을 나타내기 위해 컨트롤에서 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|표시할 셀 값의 서식을 지정하고, 사용자 입력의 구문 분석 및 유효성 검사를 위해 컨트롤에서 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|<xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정되었거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`인 경우 셀 도구 설명 텍스트를 검색하기 위해 컨트롤에서 사용됩니다.<br /><br /> 셀 도구 설명은 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 속성 값이 `true`인 경우에만 표시됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|<xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정되었거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`인 경우 셀 또는 행 오류 텍스트를 검색하기 위해 컨트롤에서 사용됩니다.<br /><br /> 현재 값이 컨트롤에 표시되도록 셀 또는 행 오류 텍스트를 변경하면 <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> 메서드 또는 <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> 메서드를 호출합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> 및 <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> 속성 값이 `true`인 경우 셀 및 행 오류 문자 표시가 나타납니다.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|컨트롤 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정되었거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`인 경우 셀 또는 행 <xref:System.Windows.Forms.ContextMenuStrip>을 검색하기 위해 컨트롤에서 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|데이터 캐시에서 행 높이 정보를 검색 또는 저장하기 위해 컨트롤에서 사용됩니다.  현재 값이 컨트롤 표시에 사용되도록 <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> 이벤트 처리기 외부의 캐시된 행 높이 정보를 변경하는 경우 <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> 메서드를 호출합니다.|  
  
## 가상 모드에서 유용한 정보  
 많은 양의 데이터를 효율적으로 작업하기 위해 가상 모드를 구현하는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤 자체를 효율적으로 사용할 수도 있습니다.  셀 스타일, 자동 크기 조정, 선택 및 행 공유의 효율적인 사용에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)