---
title: '방법: 런타임에 PrintDialog에서 사용자 입력 캡처'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 554c3c43f8ac4d41ddfc8651472d0b7fbed960bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>방법: 런타임에 PrintDialog에서 사용자 입력 캡처
디자인 타임에 인쇄와 관련 된 옵션을 설정할 수 있지만 런타임 시 사용자가을 선택한 경우에 가능성이 가장 높은 이러한 옵션을 변경 하려는 경우에 따라 합니다. 사용 하 여 문서 인쇄를 위한 사용자 입력을 캡처할 수 있습니다는 <xref:System.Windows.Forms.PrintDialog> 및 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.  
  
### <a name="to-change-print-options-programmatically"></a>인쇄 옵션을 프로그래밍 방식으로 변경 하려면  
  
1.  추가 <xref:System.Windows.Forms.PrintDialog> 및 <xref:System.Drawing.Printing.PrintDocument> 폼 구성 요소입니다.  
  
2.  설정의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 의 속성은 <xref:System.Windows.Forms.PrintDialog> 에 <xref:System.Drawing.Printing.PrintDocument> 폼에 추가 합니다.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  표시는 <xref:System.Windows.Forms.PrintDialog> 를 사용 하 여 구성 요소는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  사용자의 인쇄 선택 대화 상자에서 복사할 수는 <xref:System.Drawing.Printing.PrinterSettings> 의 속성은 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
