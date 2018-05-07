---
title: PrintPreviewControl 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 330172a2ccf285cb75432572a558363e71de7ab1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>PrintPreviewControl 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> 표시 하는 데 사용 되는 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 표시 됩니다. 이 컨트롤에는 단추나 다른 사용자 인터페이스 요소가 없으므로, 일반적으로 고유한 인쇄 미리 보기 사용자 인터페이스를 작성하려는 경우에만 <xref:System.Windows.Forms.PrintPreviewControl>을 사용합니다. 표준 사용자 인터페이스 사용는 <xref:System.Windows.Forms.PrintPreviewDialog> 제어; 참조 [PrintPreviewDialog 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) 에 대 한 개요입니다.  
  
## <a name="key-properties"></a>키 속성  
 컨트롤의 키 속성은 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>를 미리 볼 수 있도록 문서를 설정 하는 합니다. 해당 문서는 <xref:System.Drawing.Printing.PrintDocument> 개체입니다. 문서 인쇄를 위해 작성 한 개요를 참조 하십시오. [PrintDocument 구성 요소 개요](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) 및 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)합니다. <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성 가로 및 세로로 컨트롤에 표시 되는 페이지 수를 결정 합니다. 앤티 앨리어싱 매끄럽게, 표시 텍스트를 만들 수 있지만 느린; 디스플레이 축소할 수 있습니다. 이 기능을 사용 하려면 설정는 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 속성을 `true`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [PrintPreviewDialog 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [PrintPreviewControl 컨트롤](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [대화 상자 컨트롤 및 구성 요소](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
