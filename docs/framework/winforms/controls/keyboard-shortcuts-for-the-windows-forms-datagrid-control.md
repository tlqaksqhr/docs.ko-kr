---
title: "Windows Forms DataGrid 컨트롤을 위한 바로 가기 키"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e80281f3a89737f060804aa5237705386232763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Windows Forms DataGrid 컨트롤을 위한 바로 가기 키
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 다음 표에서 Windows Forms 내의 탐색에 사용할 수 있는 바로 가기 키를 보여 줍니다. <xref:System.Windows.Forms.DataGrid> 제어:  
  
|작업|바로 가기|  
|------------|--------------|  
|셀 입력을 완료 하 고 셀으로 아래로 이동 합니다.<br /><br /> 자식 테이블 링크에 포커스가 있으면 해당 테이블로 이동 합니다.|Enter 키|  
|셀 편집 모드에 있는 경우 셀 편집을 취소 합니다.<br /><br /> 움직이는 텍스트 선택에 있는 경우 해당 행에서 편집을 취소 합니다.|Esc 키|  
|셀을 편집할 때에 삽입 지점 앞에 있는 문자를 삭제 합니다.|백스페이스|  
|셀을 편집할 때에 삽입 지점 뒤의 문자를 삭제 합니다.|Delete|  
|현재 행의 첫 번째 셀으로 이동 합니다.|홈|  
|현재 행에서 셀을 마지막으로 이동 합니다.|End |  
|현재 셀의에서 문자를 강조 표시 하 고 줄의 끝 부분에 삽입 지점 위치를 지정 합니다. 셀을 두 번 클릭 하는 것과 같습니다.|F2|  
|셀에 포커스가 있으면 행의 다음 셀으로 이동 합니다.<br /><br /> 포커스가 행의 마지막 셀에 있으면 행의 첫 번째 자식 테이블 링크로 확장 합니다.<br /><br /> 자식 링크에 포커스가 있는 경우에 다음 자식 링크를 이동 합니다.<br /><br /> 마지막 자식 링크에 포커스가 있으면 다음 행의 첫 번째 셀으로 이동 합니다.|Tab|  
|포커스가 셀에 있는 경우 이전 행의 셀으로 이동 합니다.<br /><br /> 포커스가 행의 첫 번째 셀에 있으면 이전 행의 마지막 확장 된 자식 테이블 링크로 이동 하거나 이전 행의 셀을 마지막으로 이동 합니다.<br /><br /> 자식 링크에 포커스가 있으면 이전 자식 링크를 이동 합니다.<br /><br /> 첫 번째 자식 링크에 포커스가 있으면 이전 행의 셀 마지막으로 이동 합니다.|Shift+Tab|  
|탭 순서의 다음 컨트롤로 이동 합니다.|Ctrl+Tab|  
|탭 순서에서 이전 컨트롤로 이동 합니다.|Ctrl+Shift+Tab|  
|자식 테이블에 있는 경우 부모 테이블을 위로 이동 합니다. 뒤로 단추를 클릭 하는 것과 같습니다.|Alt+왼쪽 화살표|  
|자식 테이블 링크를 확장 합니다. ALT + 아래쪽 화살표를 모든 링크를 선택 하는 것 뿐 아니라 확장 합니다.|ALT + 아래쪽 화살표 또는 CTRL + 더하기 기호|  
|자식 테이블 링크를 축소 합니다. ALT + 위쪽 화살표를 모든 링크를 선택 하는 것 뿐 아니라 축소 합니다.|ALT + 위쪽 화살표 또는 CTRL + 빼기 기호|  
|화살표 방향에서 가장 멀리 비어 있지 않은 셀으로 이동 합니다.|CTRL + 화살표|  
|방향 화살표 (자식 테이블 링크는 제외)의 선택 영역 한 행을 확장 합니다.|SHIFT + 위쪽/아래쪽 화살표|  
|가장 멀리 비어 있지 않은 행 (자식 테이블 링크는 제외) 화살표의 방향 선택 영역을 확장 합니다.|CTRL + SHIFT + 위쪽/아래쪽 화살표|  
|왼쪽 위 셀으로 이동 합니다.|CTRL + HOME|  
|오른쪽 아래 셀으로 이동 합니다.|CTRL + END|  
|맨 위 행 선택 영역을 확장 합니다.|CTRL + SHIFT + HOME|  
|맨 아래 행 선택 영역을 확장 합니다.|CTRL + SHIFT + END|  
|현재 행 (자식 테이블 링크는 제외)를 선택 합니다.|SHIFT + 스페이스바|  
|전체 표 (자식 테이블 링크는 제외)를 선택 합니다.|Ctrl+A|  
|자식 테이블에 있는 경우 부모 행을 표시 합니다.|Ctrl+Page Down|  
|자식 테이블에 있는 경우 부모 행을 숨깁니다.|Ctrl+Page Up|  
|(자식 테이블 링크는 제외) 한 화면 아래로 선택 영역을 확장 합니다.|Shift+Page Down|  
|(자식 테이블 링크는 제외) 한 화면 위로 선택 영역을 확장 합니다.|Shift+Page Up|  
|호출 된 <xref:System.Windows.Forms.DataGrid.EndEdit%2A> 메서드는 현재 행에 대 한 합니다.|Ctrl+Enter|  
|입력 한 <xref:System.DBNull.Value?displayProperty=nameWithType> 편집 모드에 있을 때 셀에는 값입니다.|Ctrl+0|  
  
## <a name="see-also"></a>참고 항목  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
