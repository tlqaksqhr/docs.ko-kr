---
title: PrintForm 구성 요소(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3269a980d19466205e6c67a18f22dded9301ec59
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="printform-component-visual-basic"></a>PrintForm 구성 요소(Visual Basic)
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Visual basic의 경우 구성 요소를 사용 하면 런타임 시 Windows Form의 이미지를 인쇄할 수 있습니다. 해당 동작은 이전 Visual Basic 버전에서 `PrintForm` 메서드의 동작을 대체합니다.  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
## <a name="printform-component-overview"></a>PrintForm 구성 요소 개요  
 Windows Forms에 대한 일반적인 시나리오는 용지 형식이나 보고서와 유사하게 형식이 지정되는 폼을 만들고 나서 폼 이미지를 인쇄하는 것입니다. <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하여 이 작업을 할 수 있지만 많은 코드가 필요합니다. <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 사용하면 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하지 않고 폼 이미지를 프린터, 인쇄 미리 보기 창 또는 파일로 인쇄할 수 있습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소는 **도구 상자** 의 **Visual Basic PowerPacks**탭에 있습니다. 이 구성 요소를 폼으로 끌면 구성 요소가 폼의 아래쪽 테두리 아래 작은 영역인 구성 요소 트레이에 표시됩니다. 구성 요소를 선택하면 해당 동작을 정의하는 속성을 **속성** 창에서 설정할 수 있습니다. 이러한 속성은 모두 코드에서 설정할 수도 있습니다. 코드에서 디자인 타임에 구성 요소를 추가하지 않고 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소의 인스턴스를 만들 수도 있습니다.  
  
 폼을 인쇄할 때 폼의 클라이언트 영역에 있는 모든 항목이 인쇄됩니다. 여기에는 모든 컨트롤과 그래픽 메서드로 폼에 그려진 모든 그래픽이나 텍스트가 포함됩니다. 기본적으로 폼의 제목 표시줄, 스크롤 막대 및 테두리가 인쇄되지 않습니다. 또한 기본적으로 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소는 폼의 표시 가능한 부분만 인쇄합니다. 예를 들어 사용자가 런타임에 폼 크기를 조정하면 현재 표시된 컨트롤 및 그래픽만 인쇄됩니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소에서 사용되는 기본 프린터는 운영 체제의 제어판 설정에 따라 결정됩니다.  
  
 인쇄가 시작된 후 표준 <xref:System.Drawing.Printing.PrintDocument> 인쇄 대화 상자가 표시됩니다. 이 대화 상자에서 사용자가 인쇄 작업을 취소할 수 있습니다.  
  
### <a name="key-methods-properties-and-events"></a>주요 메서드, 속성 및 이벤트  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소의 주요 메서드는 폼 이미지를 프린터, 인쇄 미리 보기 창 또는 파일로 인쇄하는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> 메서드입니다. <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> 메서드에는 다음 두 가지 버전이 있습니다.  
  
-   매개 변수가 없는 기본 버전: `Print()`  
  
-   인쇄 동작을 지정하는 매개 변수가 있는 오버로드된 버전: `Print(printForm As Form, printFormOption As PrintOption)`  
  
     오버로드된 메서드의 `PrintOption` 매개 변수는 폼의 제목 표시줄, 스크롤 막대 및 테두리를 인쇄할지, 폼의 스크롤 가능한 부분을 인쇄할지, 그리고 폼을 인쇄하는 데 사용되는 기본 구현을 결정합니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소의 주요 속성입니다. 이 속성은 출력이 프린터로 전송되거나, 인쇄 미리 보기 창에 표시되거나, Encapsulated PostScript 파일로 저장될지를 결정합니다. <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 속성을 <xref:System.Drawing.Printing.PrintAction.PrintToFile>로 설정하면 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> 속성은 경로와 파일 이름을 지정합니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> 속성은 사용할 프린터, 인쇄 매수 등의 설정을 지정하는 데 사용되는 기본 <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> 개체에 대한 액세스를 제공합니다. 컬러 또는 양면 인쇄 지원과 같은 프린터 기능을 쿼리할 수도 있습니다. 이 속성은 **속성** 창이 표시되지 않고, 코드에서만 액세스할 수 있습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 프로그래밍 방식으로 호출할 때 인쇄할 폼을 지정하는 데 사용됩니다. 디자인 타임에 구성 요소가 폼에 추가되면 해당 폼이 기본값입니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소에 대한 주요 이벤트는 다음과 같습니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> 이벤트 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> 메서드가 호출될 때 문서의 첫 페이지가 인쇄되기 전에 발생합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> 이벤트 마지막 페이지가 인쇄된 후 발생합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> 이벤트 각 페이지가 인쇄되기 직전에 발생합니다.  
  
### <a name="remarks"></a>설명  
 폼에 <xref:System.Drawing.Graphics> 메서드로 그려진 텍스트나 그래픽이 포함되면 기본 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> (`Print()`) 메서드를 사용하여 인쇄합니다. 오버로드된 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> 메서드가 사용될 때 일부 운영 체제에서는 그래픽을 렌더링할 수 없습니다.  
  
 폼 너비가 프린터의 용지 너비보다 더 넓으면 폼의 오른쪽이 잘릴 수 있습니다. 인쇄용으로 폼을 디자인할 때 폼이 표준 크기 용지에 맞는지 확인합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소의 일반적인 사용을 보여 줍니다.  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 [방법: PrintForm 구성 요소를 사용하여 폼 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)  
 [방법: 폼의 클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [방법: 폼의 클라이언트 영역 및 비클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [방법: 스크롤 가능 폼 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
