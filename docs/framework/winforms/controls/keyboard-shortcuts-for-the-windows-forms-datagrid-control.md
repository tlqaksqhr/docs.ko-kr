---
title: "Windows Forms DataGrid 컨트롤을 위한 바로 가기 키 | Microsoft Docs"
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
  - "DataGrid 컨트롤[Windows Forms], 탐색 키"
  - "바로 가기 키, DataGrid 컨트롤"
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Windows Forms DataGrid 컨트롤을 위한 바로 가기 키
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 다음 표에는 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤 내에서 탐색할 때 사용할 수 있는 바로 가기 키가 나열되어 있습니다.  
  
|동작|바로 가기|  
|--------|-----------|  
|셀 입력을 완료하고 아래쪽 다음 셀로 이동합니다.<br /><br /> 포커스가 자식 테이블 링크에 있는 경우에는 해당 테이블로 이동합니다.|Enter|  
|셀 편집 모드에 있는 경우 셀 편집을 취소합니다.<br /><br /> 움직이는 텍스트 선택 모드에 있는 경우 행 편집을 취소합니다.|Esc|  
|셀을 편집할 때 삽입 지점 앞에 있는 문자를 삭제합니다.|백스페이스|  
|셀을 편집할 때 삽입 지점 뒤에 있는 문자를 삭제합니다.|DELETE|  
|현재 행의 첫째 셀로 이동합니다.|Home|  
|현재 행의 마지막 셀로 이동합니다.|End|  
|현재 셀의 문자를 강조 표시하고 삽입 지점을 줄 끝으로 이동합니다.  이것은 셀을 두 번 클릭하는 것과 같습니다.|F2|  
|포커스가 셀에 있는 경우 행의 다음 셀로 이동합니다.<br /><br /> 포커스가 행의 마지막 셀에 있는 경우 행의 첫째 자식 테이블 링크로 이동하여 이를 확장합니다.<br /><br /> 포커스가 자식 링크에 있는 경우 다음 자식 링크로 이동합니다.<br /><br /> 포커스가 마지막 자식 링크에 있는 경우 다음 행의 첫째 셀로 이동합니다.|TAB|  
|포커스가 셀에 있는 경우 행의 이전 셀로 이동합니다.<br /><br /> 포커스가 행의 첫째 셀에 있는 경우 이전 행에서 마지막으로 확장된 자식 테이블 링크로 이동하거나 이전 행의 마지막 셀로 이동합니다.<br /><br /> 포커스가 자식 링크에 있는 경우 이전 자식 링크로 이동합니다.<br /><br /> 포커스가 첫째 자식 링크에 있는 경우 이전 행의 마지막 셀로 이동합니다.|Shift\+Tab|  
|탭 순서에서 다음 컨트롤로 이동합니다.|Ctrl\+Tab|  
|탭 순서에서 이전 컨트롤로 이동합니다.|Ctrl\+Shift\+Tab|  
|자식 테이블에 있는 경우 부모 테이블로 이동합니다.  이것은 뒤로 단추를 클릭하는 것과 같습니다.|Alt\+왼쪽 화살표|  
|자식 테이블 링크를 확장합니다.  Alt\+아래쪽 화살표를 누르면 선택한 링크뿐만 아니라 모든 링크가 확장됩니다.|Alt\+아래쪽 화살표  또는  Ctrl\+더하기 기호|  
|자식 테이블 링크를 축소합니다.  Alt\+위쪽 화살표를 누르면 선택한 링크뿐만 아니라 모든 링크가 축소됩니다.|Alt\+위쪽 화살표  또는  Ctrl\+빼기 기호|  
|화살표 방향으로 가장 멀리 떨어진 비어 있지 않은 셀로 이동합니다.|Ctrl\+화살표|  
|선택 영역을 화살표 방향으로 한 행 확장합니다\(자식 테이블 링크 제외\).|Shift\+위쪽\/아래쪽 화살표|  
|선택 영역을 화살표 방향으로 가장 멀리 떨어진 비어 있지 않은 행까지 확장합니다\(자식 테이블 링크 제외\).|Ctrl\+Shift\+위쪽\/아래쪽 화살표|  
|왼쪽 위 셀로 이동합니다.|Ctrl\+Home|  
|오른쪽 아래 셀로 이동합니다.|Ctrl\+End|  
|선택 영역을 맨 위 행까지 확장합니다.|Ctrl\+Shift\+Home|  
|선택 영역을 맨 아래 행까지 확장합니다.|Ctrl\+Shift\+End|  
|현재 행을 선택합니다\(자식 테이블 링크 제외\).|Shift\+스페이스바|  
|모눈 전체를 선택합니다\(자식 테이블 링크 제외\).|Ctrl\+A|  
|자식 테이블에 있는 경우 부모 행을 표시합니다.|Ctrl\+Page Down|  
|자식 테이블에 있는 경우 부모 행을 숨깁니다.|Ctrl\+Page Up|  
|선택 영역을 한 화면 아래까지 확장합니다\(자식 테이블 링크 제외\).|Shift\+Page Down|  
|선택 영역을 한 화면 위까지 확장합니다\(자식 테이블 링크 제외\).|Shift\+Page Up|  
|현재 행에 대해 <xref:System.Windows.Forms.DataGrid.EndEdit%2A> 메서드를 호출합니다.|Ctrl\+Enter|  
|편집 모드에 있는 경우 셀에 <xref:System.DBNull.Value?displayProperty=fullName> 값을 입력합니다.|CTRL\+0|  
  
## 참고 항목  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)