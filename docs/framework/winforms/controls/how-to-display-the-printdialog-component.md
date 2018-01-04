---
title: "방법: PrintDialog 구성 요소 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a>방법: PrintDialog 구성 요소 표시
<xref:System.Windows.Forms.PrintDialog> 구성 요소는 표준 Windows 인쇄 대화 상자 많은 사용자 익숙할 것입니다. 사용자가 즉시 만족 하기 때문에 있다면 좋을 것 사용할 수는 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.  
  
### <a name="to-display-the-printdialog-component"></a>PrintDialog 구성 요소를 표시하려면  
  
-   호출 된 <xref:System.Windows.Forms.Form.ShowDialog%2A> 응용 프로그램의 코드에서 메서드를 합니다.  
  
     구성 요소가 표시되면 사용자가 이 구성 요소와 상호 작용하여 인쇄 작업의 속성을 설정합니다. 이러한 파일에 저장 되는 <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` 클래스 (및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용자가 액세스 하는 경우는 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 통해는 <xref:System.Windows.Forms.PrintDialog> 구성 요소) 인쇄 작업에 연결 된 합니다. 그런 다음 설정한 속성을 호출하여 인쇄 작업의 세부 사항을 결정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 표준 Windows Forms 인쇄 작업 만들기](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [방법: 런타임에 PrintDialog에서 사용자 입력 캡처](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)
