---
title: "방법: 스크롤 가능 폼 인쇄(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "전체 폼, 인쇄"
  - "스크롤 가능 폼, 인쇄"
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# 방법: 스크롤 가능 폼 인쇄(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 사용하면 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하지 않고 폼 이미지를 빠르게 인쇄할 수 있습니다. 기본적으로 폼의 현재 표시되는 부분만 인쇄되고, 사용자가 런타임에 폼 크기를 변경하면 이미지가 의도대로 인쇄되지 않을 수 있습니다. 다음 절차에서는 폼 크기가 조정되었더라도 스크롤 가능한 폼의 전체 클라이언트 영역을 인쇄하는 방법을 보여 줍니다.  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
### 스크롤 가능한 폼의 전체 클라이언트 영역을 인쇄하려면  
  
1.  **도구 상자**에서 **Visual Basic PowerPacks** 탭을 클릭하고 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 폼으로 끕니다.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 구성 요소 트레이에 추가됩니다.  
  
2.  **속성** 창에서 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 속성을 <xref:System.Drawing.Printing.PrintAction>로 설정합니다.  
  
3.  **인쇄** `Button`용 `Click` 이벤트 처리기와 같은 적절한 이벤트 처리기에 다음 코드를 추가합니다.  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  일부 운영 체제에서는 <xref:System.Drawing.Graphics> 메서드로 그려진 텍스트나 그래픽이 제대로 인쇄되지 않을 수 있습니다. 이 경우 `Scrollable` 매개 변수를 사용해서 인쇄할 수 없습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)   
 [방법: 폼의 클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [방법: 폼의 클라이언트 영역 및 비클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)