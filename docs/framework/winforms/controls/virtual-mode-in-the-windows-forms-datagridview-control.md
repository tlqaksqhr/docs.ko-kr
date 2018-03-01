---
title: "Windows Forms DataGridView 컨트롤의 가상 모드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 06c5bb1d4a36d51bb07d59b48c730f722af23f8c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 가상 모드
가상 모드 간의 상호 작용을 관리할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 제어 및 사용자 지정 데이터 캐시 합니다. 가상 모드를 구현 하려면 설정는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true` 하 고이 항목에서 설명 하는 이벤트 중 하나 이상을 처리 합니다. 일반적으로 처리 합니다 적어도 `CellValueNeeded` 데이터 캐시에서 값 조회 컨트롤 수 있도록 하는 이벤트입니다.  
  
## <a name="bound-mode-and-virtual-mode"></a>바인딩된 모드 및 가상 모드  
 가상 모드는 보완 하거나 바꿀 바인딩된 모드 필요할 때만 필요 합니다. 바인딩된 모드에서 설정 된 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성 및 컨트롤이 자동으로 지정된 된 소스에서 데이터를 로드 하 고 사용자 변경 내용을 다시 제출 합니다. 데이터 원본 자체는 일반적으로 정렬 하는 등의 작업을 처리 및 다음을 표시 되는 바인딩된 열을 제어할 수 있습니다.  
  
## <a name="supplementing-bound-mode"></a>바인딩된 모드 추가  
 바인딩된 열과 함께 바인딩되지 않은 열을 표시 하 여 바인딩된 모드를 보완할 수 있습니다. 이 "혼합된 모드" 라고도 이며 계산 된 값 또는 사용자 인터페이스 (UI)를 제어 하는 같은 것을 표시 하는 데 유용 합니다.  
  
 이기 때문에 바인딩되지 않은 열 데이터 원본이 외부 데이터 소스 정렬 작업에서 무시 됩니다. 따라서 혼합된 모드에서 정렬을 사용 하도록 설정 하면 로컬 캐시에 바인딩되지 않은 데이터를 관리 하며 수 있도록 가상 모드 구현에서 <xref:System.Windows.Forms.DataGridView> 컨트롤과 상호 작용할 합니다.  
  
 가상 모드를 사용 하 여 바인딩되지 않은 열에서 해당 값을 유지 하는 방법에 대 한 자세한 내용은 예제를 참조는 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> 클래스 참조 항목입니다.  
  
## <a name="replacing-bound-mode"></a>바인딩된 모드 바꾸기  
 바인딩된 모드 사용자의 요구를 충족 하지 않으면 가상 모드 이벤트 처리기를 통해 사용자 지정 캐시의 모든 데이터를 관리할 수 있습니다. 가상 모드를 사용 하 여 적시에 데이터 로드만 검색 하는 메커니즘을 구현 하는 예를 들어 데이터 모두 네트워크로 연결 된 데이터베이스에서 최적의 성능을 위해 필요 합니다. 이 시나리오는 많은 양의 데이터 느린 네트워크 연결을 통해 또는 제한 된 양의 RAM 또는 저장소 공간이 있는 클라이언트 컴퓨터를 작업 하는 경우 특히 유용 합니다.  
  
 적시에 시나리오에서 가상 모드를 사용 하는 방법에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드와 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)합니다.  
  
## <a name="virtual-mode-events"></a>가상 모드 이벤트  
 데이터 읽기 전용인 경우는 `CellValueNeeded` 이벤트 유일한 이벤트를 처리 해야 할 수 있습니다. 추가 가상 모드 이벤트를 사용 하 여 사용자 편집 내용을, 행 추가 및 삭제 및 행 수준 트랜잭션을 같은 특정 기능을 사용할 수 있도록 설정 합니다.  
  
 몇 가지 일반적인 <xref:System.Windows.Forms.DataGridView> 이벤트 (예: 사용자가 추가 행을 삭제 하거나 때 셀 값을 발생 하는 이벤트는 편집, 구문 분석, 유효성을 검사 하거나 포맷)는 가상 모드에 유용 합니다. 또한 일반적 도구 설명 텍스트를 셀, 셀 및 행 오류 텍스트, 셀 및 행 바로 가기 메뉴 데이터 및 행 높이 데이터 등의 바인딩된 데이터 소스에 저장 된 값을 유지 관리할 수 있도록 하는 이벤트를 처리할 수 있습니다.  
  
 행 수준 커밋 범위를 사용 하 여 읽기/쓰기 데이터를 관리 하는 가상 모드 구현 하는 방법에 대 한 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
 셀 수준 커밋 범위를 사용 하 여 가상 모드 구현 하는 예제를 참조 하십시오.는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 참조 항목입니다.  
  
 다음 이벤트가 발생만 때는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`합니다.  
  
|이벤트(event)|설명|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|컨트롤에서 표시 하기 위해 데이터 캐시에서 셀 값을 검색 하는 데 사용 합니다. 이 이벤트는 바인딩되지 않은 열에 셀에 대해서만 발생합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|데이터 캐시에는 셀에 대 한 사용자 입력을 커밋하지 컨트롤에서 사용 합니다. 이 이벤트는 바인딩되지 않은 열에 셀에 대해서만 발생합니다.<br /><br /> 호출 된 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 메서드 외부의 캐시 된 값을 변경 하는 경우는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 지정 된 컨트롤에 표시 되는지 확인 하 고 현재 유효한 모든 자동 크기 조정 모드를 적용 하는 이벤트 처리기입니다.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|컨트롤에서 데이터 캐시에 새 행에 대 한 필요성을 나타내는 데 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|컨트롤에서 행에 커밋되지 않은 변경 내용이 있는지 확인 하는 데 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|컨트롤에서 행을 캐시 된 값으로 되돌려야 함을 나타내려면 사용 합니다.|  
  
 다음 이벤트는 가상 모드에 유용 하지만 관계 없이 사용할 수는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 설정 합니다.  
  
|이벤트|설명|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|컨트롤에서 때 행이 삭제 됩니다 또는 그에 따라 데이터 캐시를 업데이트할 수 있도록 허용함을 나타내기 위해 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|셀 값의 형식 제어 하 여 표시를 위해 및 구문 분석 하 고 사용자 입력의 유효성을 검사 하는 데 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|셀 도구 설명 텍스트를 검색 하는 컨트롤에서 사용 하는 경우는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 또는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성은 `true`합니다.<br /><br /> 셀 도구 설명을 표시할지 경우에만 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 속성 값은 `true`합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|컨트롤에서 사용 하 여 셀 또는 행을 오류 텍스트를 검색할 때는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 또는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성은 `true`합니다.<br /><br /> 호출의 <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> 메서드 또는 <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> 메서드 지정 된 컨트롤에 표시 되는지 확인 하려면 셀 또는 행을 오류 텍스트를 변경 합니다.<br /><br /> 셀 및 행 오류 문자 모양이 표시 됩니다 때는 <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> 및 <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> 속성 값은 `true`합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|컨트롤에서 셀 또는 행을 검색 하는 데 사용 <xref:System.Windows.Forms.ContextMenuStrip> 때 컨트롤 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 또는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성은 `true`합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|컨트롤에서 검색 하거나 데이터 캐시의 행 높이 정보를 저장 하는 데 사용 합니다. 호출 된 <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> 메서드 외부의 캐시 된 행 높이 정보를 변경 하는 경우는 <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> 이벤트 처리기를 지정 된 컨트롤의 표시에 사용 되도록 합니다.|  
  
## <a name="best-practices-in-virtual-mode"></a>가상 모드에 대 한 모범 사례  
 확인을 사용 하는 효율적으로 할 많은 양의 데이터를 효율적으로 사용 하려면 가상 모드를 구현 하는 경우는 <xref:System.Windows.Forms.DataGridView> 자체를 제어 합니다. 셀 스타일, 자동 크기 조정, 선택 항목 및 행 공유 효율적으로 사용 하는 방법에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
