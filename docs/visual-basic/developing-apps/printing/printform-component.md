---
title: "PrintForm 구성 요소 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0c51ef0131c874ed33af7a19f9145a790d14ade
ms.lasthandoff: 03/13/2017

---
# <a name="printform-component-visual-basic"></a>PrintForm 구성 요소(Visual Basic)
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>에 대 한 구성 요소 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 런타임에 Windows Form의 이미지를 인쇄할 수 있습니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 해당 동작은 이전 Visual Basic 버전에서 `PrintForm` 메서드의 동작을 대체합니다.  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
## <a name="printform-component-overview"></a>PrintForm 구성 요소 개요  
 Windows Forms에 대한 일반적인 시나리오는 용지 형식이나 보고서와 유사하게 형식이 지정되는 폼을 만들고 나서 폼 이미지를 인쇄하는 것입니다. 사용할 수 있지만 한 <xref:System.Drawing.Printing.PrintDocument>이 수행 하는 구성 요소는 많은 코드가 필요 합니다.</xref:System.Drawing.Printing.PrintDocument> <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소를 사용 하면 사용 하지 않고 프린터, 인쇄 미리 보기 창 또는 파일을 폼의 이미지를 인쇄 하는 <xref:System.Drawing.Printing.PrintDocument>구성 요소.</xref:System.Drawing.Printing.PrintDocument> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>에 있는 구성 요소는 **Visual Basic PowerPacks** 탭은 **도구 상자**.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 이 구성 요소를 폼으로 끌면 구성 요소가 폼의 아래쪽 테두리 아래 작은 영역인 구성 요소 트레이에 표시됩니다. 구성 요소를 선택하면 해당 동작을 정의하는 속성을 **속성** 창에서 설정할 수 있습니다. 이러한 속성은 모두 코드에서 설정할 수도 있습니다. 인스턴스를 만들 수도 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>디자인 타임에 구성 요소를 추가 하지 않고 코드에서 구성 요소.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 폼을 인쇄할 때 폼의 클라이언트 영역에 있는 모든 항목이 인쇄됩니다. 여기에는 모든 컨트롤과 그래픽 메서드로 폼에 그려진 모든 그래픽이나 텍스트가 포함됩니다. 기본적으로 폼의 제목 표시줄, 스크롤 막대 및 테두리가 인쇄되지 않습니다. 또한 기본적으로 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소를 폼의 보이는 부분에만 출력 합니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 예를 들어 사용자가 런타임에 폼 크기를 조정하면 현재 표시된 컨트롤 및 그래픽만 인쇄됩니다.  
  
 사용 하는 기본 프린터는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소는 운영 체제의 제어판 설정에 의해 결정 됩니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 인쇄 작업이 초기화 되는 표준 <xref:System.Drawing.Printing.PrintDocument>인쇄 대화 상자가 표시 됩니다.</xref:System.Drawing.Printing.PrintDocument> 이 대화 상자에서 사용자가 인쇄 작업을 취소할 수 있습니다.  
  
### <a name="key-methods-properties-and-events"></a>주요 메서드, 속성 및 이벤트  
 주요 메서드는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>프린터, 인쇄 미리 보기 창 또는 파일에 폼의 이미지를 인쇄 하는 메서드를.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 두 가지 버전의는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>메서드:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   매개 변수 없이 기본 버전:`Print()`  
  
-   인쇄 동작을 지정 하는 매개 변수를 사용 하는 오버 로드 된 버전:`Print(printForm As Form, printFormOption As PrintOption)`  
  
     오버로드된 메서드의 `PrintOption` 매개 변수는 폼의 제목 표시줄, 스크롤 막대 및 테두리를 인쇄할지, 폼의 스크롤 가능한 부분을 인쇄할지, 그리고 폼을 인쇄하는 데 사용되는 기본 구현을 결정합니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>속성의 키 속성은는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 이 속성은 출력이 프린터로 전송되거나, 인쇄 미리 보기 창에 표시되거나, Encapsulated PostScript 파일로 저장될지를 결정합니다. 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>속성이 <xref:System.Drawing.Printing.PrintAction>, <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>속성 경로 파일 이름을 지정 합니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> </xref:System.Drawing.Printing.PrintAction> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A>속성은 원본 <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A>사용 하 여 프린터 및 인쇄할 복사본 수 같은 설정을 지정할 수 있도록 하는 개체</xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> 에 대 한 액세스 제공</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> 컬러 또는 양면 인쇄 지원과 같은 프린터 기능을 쿼리할 수도 있습니다. 이 속성은 **속성** 창이 표시되지 않고, 코드에서만 액세스할 수 있습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A>속성 폼을 호출할 때 인쇄 지정을 사용 하 여 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소 프로그래밍 방식으로.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> 구성 요소가 디자인 타임에 폼에 추가되면 해당 폼이 기본값입니다.  
  
 주요 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소는 다음과 같습니다:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint>이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> 발생 경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>메서드를 호출 하 고 첫 번째 페이지 문서 인쇄 하기 전에.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint>이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> 마지막 페이지가 인쇄된 후 발생합니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings>이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> 각 페이지가 인쇄되기 직전에 발생합니다.  
  
### <a name="remarks"></a>주의  
 양식에 텍스트를 포함 하는 경우 또는 그린 그래픽 <xref:System.Drawing.Graphics>메서드를 사용 하 여 기본 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>(`Print()`) 메서드를 인쇄 하십시오.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:System.Drawing.Graphics> 일부 운영 체제에서 그래픽 렌더링 되지 않을 수 있습니다 때 오버 로드 된 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>메서드를 사용 합니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
 폼 너비가 프린터의 용지 너비보다 더 넓으면 폼의 오른쪽이 잘릴 수 있습니다. 인쇄용으로 폼을 디자인할 때 폼이 표준 크기 용지에 맞는지 확인합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 일반적인 용도 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 [방법: PrintForm 구성 요소를 사용 하 여 폼 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)   
 [방법: 폼의 클라이언트 영역 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [방법: 폼의 클라이언트 이외의 영역 및 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [방법: 스크롤 가능 폼 인쇄](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
