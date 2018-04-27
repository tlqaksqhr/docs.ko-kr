---
title: XML 처리 명령 리터럴(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d2df93a46d426358988b3ad7f3161c7ae0c7b9e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML 처리 명령 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>요소  
 `<?`  
 필수. XML 처리 명령 리터럴의 시작을 나타냅니다.  
  
 `piName`  
 필수. 이름을 응용 프로그램을 나타내는 처리 명령의 대상입니다. "Xml" 또는 "XML"로 시작할 수 없습니다.  
  
 `piData`  
 선택 사항입니다. 응용 프로그램이 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.  
  
 `?>`  
 필수. 처리 명령의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML 처리 명령 리터럴 응용 프로그램은 XML 문서를 처리 하는 방법을 나타냅니다. 응용 프로그램에 XML 문서 로드 되 면 문서를 처리할 방법을 결정 하기 위해 XML 처리 명령을 확인할 수 있습니다. 응용 프로그램의 의미를 해석 `piName` 및 `piData`합니다.  
  
 XML 문서 리터럴의 XML 처리 명령 유사한 구문을 사용 합니다. 자세한 내용은 참조 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
> [!NOTE]
>  `piName` 요소는 XML 1.0 사양에 이러한 식별자는 예약 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.  
  
 XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴의에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴은 줄 연속 문자 필요 없이 여러 줄으로 나타날 수 있습니다. 따라서 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 Visual Basic 컴파일러를 호출 하는 XML 처리 명령 리터럴를 변환의 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
