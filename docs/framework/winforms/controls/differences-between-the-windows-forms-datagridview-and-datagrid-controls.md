---
title: Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: d0a82d5724ebe142ae080fc930665733e701e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점
<xref:System.Windows.Forms.DataGridView> 컨트롤은 대체 하는 새 컨트롤의 <xref:System.Windows.Forms.DataGrid> 제어 합니다. <xref:System.Windows.Forms.DataGridView> 에 누락 된 다양 한 기본 및 고급 기능을 제공 하는 컨트롤의 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 또한의 아키텍처는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 훨씬 쉽게 확장 및 보다 사용자 지정할 수는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.  
  
 다음 표에에서 사용할 수 있는 주요 기능 중 몇 가지는 <xref:System.Windows.Forms.DataGridView> 에서 누락 된 컨트롤의 <xref:System.Windows.Forms.DataGrid> 컨트롤입니다.  
  
|DataGridView 컨트롤의 기능|설명|  
|----------------------------------|-----------------|  
|여러 열 유형|<xref:System.Windows.Forms.DataGridView> 컨트롤 보다 더 많은 기본 제공 열 형식을 제공 합니다.는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 이러한 열 유형에 가장 일반적인 시나리오의 요구를 충족 하면서도 쉽게를 확장할지 또는 대체할지의 열 형식 보다는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)합니다.|  
|여러 가지 방법으로 데이터를 표시 하려면|<xref:System.Windows.Forms.DataGrid> 컨트롤 외부 데이터 원본에서 데이터를 표시 하는로 제한 됩니다. 그러나 <xref:System.Windows.Forms.DataGridView> 컨트롤을 표시할 수 바인딩되지 않은 데이터를 함께 컨트롤, 바인딩된 데이터 원본에서 데이터 또는 바인딩된 바인딩되지 않은 데이터에 저장 합니다. 가상 모드를 구현할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용자 지정 데이터 관리를 제공 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)합니다.|  
|여러 가지 방법으로 데이터의 표시를 사용자 지정 하려면|<xref:System.Windows.Forms.DataGridView> 컨트롤은 여러 속성 및 데이터 형식이 지정 및 표시 방법을 지정할 수 있도록 하는 이벤트를 제공 합니다. 예를 들어 셀, 행 및 열 포함 된 데이터에 따라의 모양을 변경할 수 있습니다 또는 다른 형식의 해당 하는 데이터와 함께 하나의 데이터 형식의 데이터를 바꿀 수 있습니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤에서 데이터 서식](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)합니다.|  
|셀, 행, 열 및 헤더 모양 및 동작을 변경 하기 위한 여러 옵션|<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 여러 가지 방식으로 표를 개별 구성 요소로 작업할 수 있습니다. 예를 들어 행과; 스크롤을 방지 하려면 열을 고정할 수 있습니다. 행, 열 및 머리글 숨기기 행, 열 및 헤더 크기를 조정; 방식을 변경합니다 사용자가 선택할; 방식을 변경합니다 고 개별 셀, 행 및 열에 대 한 도구 설명 및 바로 가기 메뉴를 제공 합니다.|  
  
 <xref:System.Windows.Forms.DataGrid> 및 특별 한 요구에 따라 이전 버전과 호환성에 대 한 컨트롤을 계속 유지 합니다. 거의 모든 목적을 위해 사용 해야는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 사용할 수 있는 유일한 기능은 <xref:System.Windows.Forms.DataGrid> 에서 사용할 수 있는 컨트롤의 <xref:System.Windows.Forms.DataGridView> 컨트롤은 단일 컨트롤에 관련 된 두 테이블에서 정보를 계층적으로 표시 합니다. 두 개를 사용 해야 <xref:System.Windows.Forms.DataGridView> 컨트롤은 마스터/세부 관계에 있는 두 테이블의 정보를 표시 합니다.  
  
## <a name="upgrading-to-the-datagridview-control"></a>DataGridView 컨트롤에서로 업그레이드  
 사용 하는 기존 응용 프로그램의 경우는 <xref:System.Windows.Forms.DataGrid> 컨트롤에서 사용자 지정 하지 않고는 간단한 데이터 바인딩 시나리오를 대체할 수 있습니다 단순히 이전 컨트롤 새 컨트롤이 포함 됩니다. 두 컨트롤에는 표준 Windows Forms 데이터 바인딩 아키텍처를 사용 하므로 <xref:System.Windows.Forms.DataGridView> 컨트롤 추가 구성이 필요 없는 된 바인딩된 데이터 표시 됩니다. 하지만 데이터 바인딩 향상, 데이터를 바인딩하여 사용 하려는 경우는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 바인딩할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 참조 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)합니다.  
  
 때문에 <xref:System.Windows.Forms.DataGridView> 컨트롤 아키텍처는 완전히 새로운 값, 사용할 수 있도록 변환 하는 방법은 경로가 없기 <xref:System.Windows.Forms.DataGrid> 사용자 지정으로는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 하지만 많은 <xref:System.Windows.Forms.DataGrid> 사용자 지정으로 필요 하지 않습니다는 <xref:System.Windows.Forms.DataGridView> 새 컨트롤에 사용할 수 있는 기본 제공 기능으로 인해 제어 합니다. 에 대 한 사용자 지정 열 형식을 만든 경우의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용 하면 원하는 <xref:System.Windows.Forms.DataGridView> 컨트롤, ´ ë ç 새로운 아키텍처를 사용 하 여 다시 구현 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
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
