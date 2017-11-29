---
title: "PrintPreviewDialog 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c898dc24c9a4418e3af45fce507e6befcf905a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>PrintPreviewDialog 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 표시 하는 데 사용 되는 미리 구성 된 대화 상자가 어떻게는 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 인쇄할 때 표시 됩니다. 고유한 대화 상자를 구성 하는 대신 간단한 솔루션으로 Windows 기반 응용 프로그램 내에서 사용 합니다. 컨트롤에는 인쇄, 확대, 한 페이지 또는 여러 페이지 표시 및 대화 상자 닫기 단추가 포함되어 있습니다.  
  
## <a name="key-properties-and-methods"></a>키 속성 및 메서드  
 컨트롤의 키 속성은 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>를 미리 볼 수 있도록 문서를 설정 하는 합니다. 해당 문서는 <xref:System.Drawing.Printing.PrintDocument> 개체입니다. 대화 상자를 표시 하기 위해 호출 해야 해당 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드. 앤티앨리어싱 매끄럽게, 표시 텍스트를 만들 수 있지만 느린; 디스플레이 축소할 수 있습니다. 이 기능을 사용 하려면 설정는 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`합니다.  
  
 특정 속성을 통해 사용할 수는 <xref:System.Windows.Forms.PrintPreviewControl> 하 고 <xref:System.Windows.Forms.PrintPreviewDialog> 포함 합니다. (이 추가할 필요가 없습니다 <xref:System.Windows.Forms.PrintPreviewControl> 을 폼은 자동으로 포함 되어는 <xref:System.Windows.Forms.PrintPreviewDialog> 폼에 대화 상자를 추가 합니다.) 통해 사용할 수 있는 속성의 예는 <xref:System.Windows.Forms.PrintPreviewControl> 됩니다는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 가로 및 세로로 컨트롤에 표시 되는 페이지 수를 결정 하는 속성입니다. 에 액세스할 수 있습니다는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성으로 `PrintPreviewDialog1.PrintPreviewControl.Columns` 에 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` 에 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], 또는 `printPreviewDialog1->PrintPreviewControl->Columns` 에서 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [PrintPreviewControl 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [대화 상자 컨트롤 및 구성 요소](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
