---
title: "DataGridView 컨트롤 시나리오(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 919197d8fdb40f0e0fb7b91fecae38f4e0e061bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-scenarios-windows-forms"></a>DataGridView 컨트롤 시나리오(Windows Forms)
와 <xref:System.Windows.Forms.DataGridView> 컨트롤을 다양 한 데이터 원본에서에서 테이블 형식 데이터를 표시할 수 있습니다. 간단한 용도로 수동으로 차원을 채울 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 제어를 통해 직접 데이터를 조작 합니다. 그러나 일반적으로는 외부 데이터 원본에 데이터를 저장 한 키를 통해에 컨트롤 바인딩는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
 이 항목에서는 몇 가지 일반적인 시나리오와 관련 된 설명는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>시나리오 1: 적은 양의 데이터를 표시합니다.  
 에 표시 하기 위해 외부 데이터 원본에 데이터를 저장할 필요가 없습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 적은 양의 데이터를 사용 하는 경우에 사용자가 직접 컨트롤을 채울 수 있으며 제어를 통해 데이터를 조작할 수 있습니다. 이 라고 *바인딩되지 않은 모드*합니다. 자세한 내용은 참조 [하는 방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   바인딩되지 않은 모드에서 하면 컨트롤을 수동으로 채웁니다.  
  
-   바인딩되지 않은 모드는 적은 양의 데이터에 특히 적합 합니다.  
  
-   바인딩되지 않은 모드는 스프레드시트 모양의 또는 근거가 테이블도 적합 합니다.  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>시나리오 2: 보기 및 외부 데이터 원본에 저장 된 데이터를 업데이트 합니다.  
 사용할 수는 <xref:System.Windows.Forms.DataGridView> 데이터베이스 테이블 또는 비즈니스 개체의 컬렉션에 같은 데이터 원본에 유지 하는 데이터에 액세스할 수 있는 사용자를 통해 사용자 인터페이스 (UI)으로 제어 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   바인딩된 모드를 사용 하 여 데이터 원본에 연결, 데이터 원본 속성 또는 데이터베이스 열을 기준으로 열을 자동으로 생성 하 고 컨트롤을 채울 수 있습니다.  
  
-   바인딩된 모드는 많은 사용자 데이터와 상호 작용에 대 한 적합 합니다. 표시 되는 데이터 형식을 지정할 수 및 사용자 지정 데이터를 데이터 원본에서 예상 되는 형식으로 구문 분석할 수 있습니다. 사용자가 경고를 보낼 수 및 오류가 있는 셀을 해결할 수 있도록 서식 오류 및 데이터베이스 제약 조건 오류는 데이터 입력을 검색할 수 있습니다.  
  
-   열 정렬 등의 추가 기능, 고정 및 다시 사용자가을 자신의 워크플로에 대 한 가장 편리한 방식으로 데이터를 볼 사용 합니다.  
  
-   클립보드 지원을 통해 사용자가 다른 응용 프로그램으로 응용 프로그램에서 데이터를 복사할 수 있습니다.  
  
## <a name="scenario-3-advanced-data"></a>시나리오 3: 고급 데이터  
 표준 데이터 바인딩 모델 해결 되지 않는 경우 컨트롤과 데이터 간의 상호 작용을 구현 하 여 관리할 수 있습니다 *가상 모드*합니다. 구현 정보로 셀에 대 한 제어 요청 정보 수 있는 하나 이상의 이벤트 처리기를 구현 하는 가상 모드 의미 필요 합니다.  
  
 예를 들어 많은 양의 데이터를 사용 하는 경우 최적의 효율성을 위해 가상 모드 구현 하는 것이 좋습니다. 가상 모드는 다른 데이터 원본에서 검색 하는 열과 함께 표시 하는 바인딩되지 않은 열의 값을 유지 관리 하기 위한 유용 합니다.  
  
 가상 모드에 대 한 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   가상 모드는 성능을 미세 조정 해야 할 때 매우 많은 양의 데이터를 표시 하기 위한 적합 합니다.  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>시나리오 4: 자동으로 크기 조정 행 및 열  
 정기적으로 업데이트 하는 데이터를 표시 하면 행과 열 모든 콘텐츠 표시 되는지 확인을 자동으로 조정할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 크기 조정 자동으로 콘텐츠가 변경 될 때마다 또는 컨트롤 사용 또는 사용 안 함 수동 크기 조정, 특정 시간에 프로그래밍 방식으로 크기를 조정할 수 있는 몇 가지 옵션을 제공 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   수동 크기 조정을 통해 셀 높이 너비를 조정할 수 있습니다.  
  
-   자동 크기 조정 셀 내용이 잘리지 않도록 셀 크기를 유지할 수 있습니다.  
  
-   프로그래밍 방식의 크기 연속 자동 크기 조정의 성능 저하를 방지 하기 위해 특정 시간에 크기를 조정할 수 있습니다.  
  
## <a name="scenario-5-simple-customization"></a>시나리오 5: 단순 사용자 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기본 모양과 동작을 변경할 수 있는 여러 가지 방법이 제공 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>개체를 사용 하면 색, 글꼴, 서식 및 여러 수준에서 및 컨트롤의 개별 요소에 대 한 위치 정보를 제공할 수 있습니다.  
  
-   셀 스타일 및 계층 코드를 재사용할 수 있으므로 여러 요소를 공유할 수 있습니다.  
  
## <a name="scenario-6-advanced-customization"></a>시나리오 6: 고급 사용자 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 모양과 동작을 사용자 지정할 수 있는 여러 가지 방법이 제공 합니다.  
  
### <a name="scenario-key-points"></a>시나리오 주요 사항  
  
-   셀 그리기 코드를 제공할 수 있습니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)합니다.  
  
-   고유한 행 그리기를 제공할 수 있습니다. 이 값은 유용 예를 들어 여러 열에 걸쳐 있는 내용이 있는 행을 만들려고 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)합니다.  
  
-   셀 모양 사용자 지정 하려면 사용자 고유의 셀과 열 클래스를 구현할 수 있습니다. 자세한 내용은 참조 [하는 방법: 확장 해당 동작과 모양은 하 여 Windows Forms DataGridView 컨트롤에서 사용자 지정 셀 및 열](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)합니다.  
  
-   기본 제공 열 형식으로 제공 되지 않는 호스트 컨트롤에 사용자 고유의 셀과 열 클래스를 구현할 수 있습니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 셀에서 호스트 컨트롤](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
