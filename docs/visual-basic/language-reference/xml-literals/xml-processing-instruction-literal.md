---
title: "XML 처리 명령 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2903297fa22cd8dc10bc4b12abaa754d4f6284f2
ms.lasthandoff: 03/13/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML 처리 명령 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction>개체.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="syntax"></a>구문  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>요소  
 `<?`  
 필수 요소. XML 처리 명령 리터럴의 시작을 나타냅니다.  
  
 `piName`  
 필수 요소. 이름을 응용 프로그램을 나타내는 처리 명령 대상으로 합니다. "Xml" 또는 "XML"로 시작할 수 없습니다.  
  
 `piData`  
 선택적 요소. 응용 프로그램이 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.  
  
 `?>`  
 필수 요소. 처리 명령의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XProcessingInstruction>개체.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="remarks"></a>주의  
 XML 처리 명령 리터럴 응용 프로그램은 XML 문서를 처리 하는 방법을 나타냅니다. 응용 프로그램에서 XML 문서를 로드할 때 문서를 처리 하는 방법을 결정 하는 XML 처리 명령을 확인할 수 있습니다. 응용 프로그램의 의미를 해석 `piName` 및 `piData`합니다.  
  
 XML 문서 리터럴 XML 처리 명령 하는 유사한 구문을 사용 합니다. 자세한 내용은 참조 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
> [!NOTE]
>  `piName` 요소는 XML 1.0 사양에는 이러한 식별자는 예약 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.  
  
 리터럴 XML 문서에 포함 하거나 XML 처리 명령 리터럴 변수에 할당할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴은 줄 연속 문자가 필요 없이 여러 줄으로 나타날 수 있습니다. 이렇게 하면 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수 있습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 변환에 대 한 호출 하는 XML 처리 명령 리터럴는 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>생성자.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.  
  
 [!code-vb[VbXMLSamples #&28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
