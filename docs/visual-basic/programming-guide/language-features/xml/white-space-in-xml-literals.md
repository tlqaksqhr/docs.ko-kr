---
title: "XML 리터럴 (Visual Basic)에 있는 공백을 | Microsoft 문서"
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: b98a88696f24cc0b95401812471d13acea4faa6d
ms.lasthandoff: 03/13/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 리터럴의 공백(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러를 만들 때 XML 리터럴에서 유효 공백 문자만 포함 한 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다. 유효 하지 않은 공백 문자는 포함 되지 않습니다.  
  
## <a name="significant-and-insignificant-white-space"></a>유효 공백과 무효 공백의 공백  
 XML 리터럴의 공백 문자는 세 영역에서 상당한:  
  
-   특성 값입니다.  
  
-   요소의 텍스트 콘텐츠의 일부인 시점과 텍스트도 다른 문자를 포함 합니다.  
  
-   요소의 텍스트 내용에 대 한 포함된 된 식에서가 있습니다.  
  
 그렇지 않으면 컴파일러에서는으로 무효 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 리터럴에 대 한 개체입니다.  
  
 무효 공백은 리터럴 xml에서을 포함 하려면 공백 리터럴 문자열이 포함 된 포함된 식을 사용 합니다.  
  
> [!NOTE]
>  하는 경우는 `xml:space` 리터럴, XML 요소에 특성이 표시 되는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서 특성을 포함는 <xref:System.Xml.Linq.XElement>개체가 아니라 추가이 특성은 컴파일러에서 공백을 처리 하는 방법을 변경 되지 않습니다.</xref:System.Xml.Linq.XElement>  
  
## <a name="examples"></a>예제  
 다음 예제에서는 외부 및 내부 두 XML 요소를 포함합니다. 두 요소에 텍스트 내용에 공백이 포함 되어 있습니다. 공백 및 XML 요소가 포함 된 외부 요소에 공백이 중요 하지 않습니다. 요소의 내부에서 공백을 공백 및 텍스트를 포함 하므로 중요 합니다.  
  
 [!code-vb[VbXMLSamples #&29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 를 실행 하는 경우이 코드는 다음 텍스트를 표시 합니다.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
