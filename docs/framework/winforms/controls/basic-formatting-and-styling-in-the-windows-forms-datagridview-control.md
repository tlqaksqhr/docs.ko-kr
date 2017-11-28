---
title: "Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c6ae9c4159f8f9eafd73608e4fc3f4a646c1eaa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정
`DataGridView` 컨트롤을 사용 하면 쉽게 셀의 기본 모양과 셀 값의 표시 형식을 정의할 수 있습니다. 모양을 정의할 수 있습니다 및 속성을 설정 하 여 개별 셀, 특정 열과 행의 셀 또는 컨트롤에 있는 모든 셀에 대 한 스타일 서식을 `DataGridViewCellStyle` 다양 한를 통해 액세스 되는 개체 `DataGridView` 속성을 제어 합니다. 또한 처리 하 여 셀 값 등의 요인에 따라 동적으로 이러한 스타일을 수정할 수는 `CellFormatting` 이벤트입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 설정 하는 방법에 설명 `DataGridView` 셀 사이의 경계 선과 컨트롤 테두리의 모양을 정의 하는 속성입니다.  
  
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 설명의 `DataGridViewCellStyle` 클래스 및 해당 형식의 속성은 컨트롤에서 셀을 표시 하는 방법을 정의 하려면 상호 작용 하는 방법을 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 사용 하는 방법에 설명 `DataGridViewCellStyle` 전체 컨트롤 및 특정 행과 열에서 셀의 기본 모양을 정의 하는 속성입니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 사용 하 여 셀 표시 값의 형식을 지정 하는 방법을 설명 `DataGridViewCellStyle` 속성입니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 사용 하는 방법에 설명 된 `DefaultCellStyle` 속성을 기본 설정 컨트롤에 모든 셀에 대 한 특성을 표시 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 다르게 표시 되는 행에 번갈아 표시를 사용 하 여 컨트롤에서 장부와 비슷한 효과 만드는 방법을 설명 합니다.  
  
 [방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 사용 하는 방법에 설명 된 `RowTemplate` 속성을 컨트롤의 모든 행에 사용할 행 속성을 설정 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 셀, 행 및 열 속성을 사용 하는 일반적으로 설명 하는 항목을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
