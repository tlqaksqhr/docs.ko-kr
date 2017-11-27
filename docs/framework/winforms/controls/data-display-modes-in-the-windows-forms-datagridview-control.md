---
title: "Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc7fd3d3012053d8c40edf5fdce8af45c62c98c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드
<xref:System.Windows.Forms.DataGridView> 세 가지 모드로 컨트롤 데이터를 표시할 수 있습니다: 바인딩된, 언바운드 및 가상입니다. 요구 사항에 따라 가장 적합 한 모드를 선택 합니다.  
  
## <a name="unbound"></a>바인딩되지 않은  
 바인딩되지 않은 모드는 상대적으로 적은 양의 프로그래밍 방식으로 관리 하는 데이터를 표시 하기 위한 적합 합니다. 연결 하지 않습니다는 <xref:System.Windows.Forms.DataGridView> 바인딩된 모드에서와 같이 데이터 원본에 직접 제어 합니다. 대신, 채워야 컨트롤을 직접 일반적으로 사용 하 여는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 메서드.  
  
 바인딩되지 않은 모드는 정적, 읽기 전용 데이터 나 외부 데이터 저장소와 상호 작용 하는 코드를 제공 하려는 경우에 특히 유용할 수 있습니다. 그러나 사용자가 외부 데이터 원본과 상호 작용 하도록 하려는 경우 바인딩된 모드 일반적으로 사용 됩니다.  
  
 읽기 전용을 사용 하는 예제에 대 한 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView>, 참조 [하는 방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)합니다.  
  
## <a name="bound"></a>바인딩된  
 바인딩된 모드는 자동 상호 데이터 저장소를 사용 하 여 데이터를 관리 하기 위한 적합 합니다. 연결할 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 설정 하 여 해당 데이터 원본에 직접는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성입니다. 데이터 바인딩된 컨트롤을 사용 하는 경우 데이터 행을 푸시하고 사용자의 명시적 관리 하지 않아도 됩니다. 경우는 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성은 `true`, 데이터 소스의 각 열에에서 해당 컨트롤을 만들어야 하는 열에 발생 합니다. 고유한 열을 만들려면 선호 하는 경우이 속성을 설정할 수 있습니다 `false` 사용 하는 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 속성을 구성할 때 각 열을 바인딩합니다. 기본적으로 생성 되는 형식 이외의 열 형식을 사용 하려는 경우에 유용 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)합니다.  
  
 한계를 사용 하는 예제에 대 한 <xref:System.Windows.Forms.DataGridView> 제어, 참조 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
 바인딩되지 않은 열을 추가할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView> 바인딩된 모드에서 제어 합니다. 사용자가 특정 행에 대해 작업을 수행할 수 있도록 주는 단추 또는 링크의 열을 표시 하려는 경우에 유용 합니다. 또한 바인딩된 열에서 계산 된 값이 포함 된 열을 표시 하는 것이 유용 합니다. 에 대 한 처리기에서 계산 된 열에 대 한 셀 값을 채울 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다. 하지만 사용 하는 경우는 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable> 데이터 원본으로, 필요할 수 있습니다 사용할는 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> 계산된 된 열을 대신 만들어야 하는 속성입니다. 이 경우에 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 데이터 원본에 다른 열과 마찬가지로 계산된 열을 처리 합니다.  
  
 바인딩된 모드에 바인딩되지 않은 열을 정렬할 수 없습니다. 사용자가 편집 가능한 값을 포함 하는 바인딩된 모드에 바인딩되지 않은 열을 만들면 컨트롤은 바인딩된 열에 의해 정렬 될 때 이러한 값을 유지 하기 위해 가상 모드를 구현 해야 합니다.  
  
## <a name="virtual"></a>가상  
 가상 모드에서는 사용자 고유의 데이터 관리 작업을 구현할 수 있습니다. 이 작업이 컨트롤이 바인딩된 열에서 정렬 될 때 바인딩된 모드에 바인딩되지 않은 열의 값을 유지 하기 위해 필요 합니다. 그러나 가상 모드의 주된 용도 많은 양의 데이터와 상호 작용할 때 성능을 최적화 하는 것입니다.  
  
 연결 하는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 관리 하는 캐시 하 고 데이터 행을 푸시하고 경우 사용자 코드를 제어 합니다. 메모리 사용 공간을 작게 유지 하기 위해 캐시 현재 표시 된 행 수가 크기와 유사 해야 합니다. 사용자는 새 행을 뷰로 스크롤합니다, 코드 캐시에서 새 데이터를 요청 하 고 필요에 따라 메모리에서 이전 데이터를 플러시합니다.  
  
 가상 모드를 구현 하는 경우에 새 행은 데이터 모델에 고 필요한 경우 추가를 롤백하는 새 행의 시기를 추적 해야 합니다. 이 기능의 정확한 구현은 데이터 모델의 구현 하 고, 데이터 모델의 트랜잭션 의미 체계에 따라 달라 집니다. 셀 또는 행 수준에서 커밋 범위 인지 여부입니다.  
  
 가상 모드에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)합니다. 가상 모드 이벤트를 사용 하는 방법을 보여 주는 예제를 보려면 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
