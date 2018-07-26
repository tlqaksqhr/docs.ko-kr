---
title: XML 리터럴의 공백(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245161"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 리터럴의 공백(Visual Basic)
Visual Basic 컴파일러를 만들 때 XML 리터럴에서 유효 공백 문자만 포함 된 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. 불필요 한 공백 문자는 포함 되지 않습니다.  
  
## <a name="significant-and-insignificant-white-space"></a>유효 공백과 무효 공백  
 만 세 가지 영역에서 XML 리터럴의 공백 문자 사항이 중요 합니다.  
  
-   특성 값에 있을 때.  
  
-   요소의 텍스트 콘텐츠 일부가 텍스트에도 다른 문자가 시점과 합니다.  
  
-   요소의 텍스트 콘텐츠에 대 한 포함된 식을에 있을 때.  
  
 그렇지 않으면 컴파일러를 불필요 한 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 리터럴의 개체입니다.  
  
 무효 공백은 리터럴 XML에 포함 하려면 공백을 사용 하 여 리터럴 문자열을 포함 하는 포함 된 식을 사용 합니다.  
  
> [!NOTE]
>  경우는 `xml:space` XML 요소 리터럴에 표시 되는 특성, Visual Basic 컴파일러에서 특성을 포함 합니다 <xref:System.Xml.Linq.XElement> 개체가 아니라이 특성에 컴파일러는 공백 문자를 처리 하는 방법을 변경 하지 않습니다 추가 합니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 두 개의 XML 요소를 외부 및 내부를 포함합니다. 두 요소 텍스트 내용에 공백이 포함 되어 있습니다. 공백 및 XML 요소가 포함 되어 있으므로 외부 요소에서 공백을 중요 하지 않습니다. 요소의 내부에 공백을 공백 및 텍스트 있기 때문에 유효 합니다.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 를 실행 하는 경우이 코드는 다음 텍스트를 표시 합니다.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
