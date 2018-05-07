---
title: PrintDialog 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0b0e516364277133efc83e7324345ccea8328690
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="printdialog-component-overview-windows-forms"></a>PrintDialog 구성 요소 개요(Windows Forms)
Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 구성 요소는 프린터를 선택, 인쇄할 페이지를 선택 하 고 Windows 기반 응용 프로그램에서 다른 인쇄 관련 설정을 결정 하는 데 사용 하는 미리 구성 된 대화 상자. 고유한 대화 상자를 구성하는 대신 이 대화 상자를 프린터 및 인쇄 관련 설정 선택을 위한 간단한 솔루션으로 사용합니다. 사용자가 자신의 문서의 많은 부분을 인쇄 하도록 사용 하도록 설정할 수 있습니다: 모두 인쇄, 선택한 페이지 범위 인쇄 또는 선택 영역을 인쇄 합니다. 표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 응용 프로그램을 만듭니다. <xref:System.Windows.Forms.PrintDialog> 구성 요소에서 상속 된 <xref:System.Windows.Forms.CommonDialog> 클래스입니다.  
  
## <a name="working-with-the-component"></a>구성 요소 작업  
 사용 된 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 런타임 시 대화 상자를 표시 합니다. 이 구성 요소에는 단일 인쇄 작업에 관련 된 속성 (<xref:System.Drawing.Printing.PrintDocument> 클래스) 또는 개별 프린터의 설정 (<xref:System.Drawing.Printing.PrinterSettings> 클래스). 차례로 이러한 속성은 추가 여러 프린터에 공유할 수 있습니다.  
  
 폼에 추가 될 때의 <xref:System.Windows.Forms.PrintDialog> 구성 요소는 Windows Forms 디자이너 아래쪽에서 트레이에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.PrintDialog>  
 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
