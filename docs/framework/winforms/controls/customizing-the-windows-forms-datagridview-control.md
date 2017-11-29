---
title: "Windows Forms DataGridView 컨트롤 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d1246a8052af19057f7aa9d6729e34203177f8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤 사용자 지정
`DataGridView` 컨트롤은 모양과 해당 셀, 행 및 열의 기본 동작 (모양 및 느낌)를 조정 하는 데 사용할 수 있는 몇 가지 속성을 제공 합니다. 기능 이외에 특별 한 요구 사항이 있으면는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스, 있지만 수 또한 소유자 그리기 컨트롤에 대 한 구현 하거나 사용자 지정 셀, 열 및 행을 만들어 기능을 확장 합니다.  
  
 그릴 셀 및 행 직접 다양 한 처리할 수 있습니다 `DataGridView` 그리기 이벤트입니다. 를 기존 기능을 수정 하거나 새로운 기능을 제공 하려면 기존에서 파생 된 형식을 사용자를 만들 수 있습니다 `DataGridViewCell`, `DataGridViewColumn`, 및 `DataGridViewRow` 형식입니다. 또한 선택한 셀이 편집 모드일 때 컨트롤을 표시 하는 파생된 형식을 만들면 새 편집 기능을 제공할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.CellPainting> 셀을 수동으로 그리기 위해 이벤트입니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트는 사용자 지정, 그라데이션 배경의 행을 그릴 하 고는 콘텐츠의 하기 위해 여러 열에 확장 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 파생 된 사용자 정의 형식을 만드는 방법을 설명 `DataGridViewCell` 및 `DataGridViewColumn` 에 마우스 포인터를 놓으면 셀을 강조 표시 하기 위해.  
  
 [방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 파생 된 사용자 정의 형식을 만드는 방법을 설명 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn> 단추 열에서 비활성화 된 단추를 표시 하기 위해 합니다.  
  
 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 구현 하는 방법에 설명는 `IDataGridViewEditingControl` 인터페이스 및에서 파생 된 사용자 지정 형식을 만들 `DataGridViewCell` 및 `DataGridViewColumn` 표시 하기 위해는 <xref:System.Windows.Forms.DateTimePicker> 때 셀이 편집 모드를 제어 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewCell> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewRow> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스입니다.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
