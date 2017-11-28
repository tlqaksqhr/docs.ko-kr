---
title: "Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 888fb1cbd960c006dc2705a2b0bd66c038a926f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용
`DataGridView` 컨트롤에서는 다양 한 셀, 행 및 열 사용자가 방법을 선택할 수 구성 옵션을 제공 합니다. 예를 들어 가능 단일 또는 여러 선택 영역, 전체 행 또는 사용자가 셀을 클릭할 때 열을 선택 또는 전체 행 또는 열을 선택할 사용자가 머리글을 클릭할 경우에 셀 선택도를 매핑함으로써 합니다. 선택에 대 한 고유의 사용자 인터페이스를 제공 하려는 경우에 일반적인 선택을 사용 하지 않도록 설정할 수 있으며 모든 선택 항목을 프로그래밍 방식으로 처리할 수 있습니다. 또한 사용자가 선택한 값을 클립보드에 복사할 수를 사용할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Windows Forms DataGridView 컨트롤의 선택 모드](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 사용자 및 컨트롤의 프로그래밍 방식으로 선택에 대 한 옵션을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 사용자가 셀을 클릭 하면 단일 행 선택에 대 한 제어를 구성 하는 방법에 설명 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 선택한 셀, 행 및 열 컬렉션을 사용 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 컨트롤의 클립보드 지원을 사용 하도록 설정 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성입니다.  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 속성입니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
