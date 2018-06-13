---
title: '방법: 폼의 클라이언트 영역 인쇄(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: 361db89f0880a03273aac7fc36b5c5faa825486f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583993"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a>방법: 폼의 클라이언트 영역 인쇄(Visual Basic)
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 사용하면 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하지 않고 폼 이미지를 빠르게 인쇄할 수 있습니다. 다음 절차에서는 제목 표시줄, 테두리 및 스크롤 막대 없이 폼의 클라이언트 영역만 인쇄하는 방법을 보여 줍니다.  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
### <a name="to-print-the-client-area-of-a-form"></a>폼의 클라이언트 영역을 인쇄하려면  
  
1.  **도구 상자**에서 **Visual Basic PowerPacks** 탭을 클릭하고 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 폼으로 끕니다.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 구성 요소 트레이에 추가됩니다.  
  
2.  **속성** 창에서 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 속성을 <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>로 설정합니다.  
  
3.  `Click` 인쇄 **용**`Button`이벤트 처리기와 같은 적절한 이벤트 처리기에 다음 코드를 추가합니다.  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  일부 운영 체제에서는 <xref:System.Drawing.Graphics> 메서드로 그려진 텍스트나 그래픽이 제대로 인쇄되지 않을 수 있습니다. 이 경우 호환되는 인쇄 메서드를 사용합니다. `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [PrintForm 구성 요소](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [방법: 폼의 클라이언트 영역 및 비클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [방법: 스크롤 가능 폼 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
