---
title: "방법: XML 리터럴 (Visual Basic) 식 포함 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 40b0e4273223093262bc54a2b13d28fc93a44c69
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>방법: XML 리터럴에 식 포함(Visual Basic)
XML 리터럴 XML 문서, 조각 또는 런타임 시 생성 된 콘텐츠가 포함 된 요소를 만드는 포함 된 식으로 결합할 수 있습니다. 다음 예제에 포함 된 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름이 채우는 방법을 보여 줍니다.  
  
 포함된 된 식의 구문은 `<%=` `exp` `%>`, 즉 동일한 구문을 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 사용 합니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
 사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Api를 만드는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 을 참조 하십시오.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-insert-text-as-element-content"></a>요소 내용으로 텍스트를 삽입 하려면  
  
-   다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `contactName` 열기 및 닫기 이름 요소 간의 변수입니다.  
  
     [!code-vb[VbXMLSamples #&39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>특성 값으로 텍스트를 삽입 하려면  
  
-   다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `phoneType` 의 값으로 변수는 `type` 특성입니다.  
  
     [!code-vb[VbXMLSamples #&40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>요소 이름에 대 한 텍스트를 삽입 하려면  
  
-   다음 예제에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `elementName` 요소 이름으로 변수입니다.  
  
     이 기술을 사용 하 여 요소를 만들 때 닫아야를 사용 하 여는 \</ > 태그입니다.  
  
     [!code-vb[VbXMLSamples #&41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: XML 리터럴 만들기](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [XML의 포함된 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
