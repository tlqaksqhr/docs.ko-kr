---
title: "XML 리터럴의 공백(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 리터럴의 공백(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러를 만들 때 XML 리터럴의 공백 문자만 포함 한 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. 유효 하지 않은 공백 문자는 포함 되지 않습니다.  
  
## <a name="significant-and-insignificant-white-space"></a>중요 하 고 불필요 한 공백  
 XML 리터럴의 공백 문자는 3 개의 영역에 중요 한 있습니다.  
  
-   이러한 특성 값에 있는 경우  
  
-   요소의 텍스트 콘텐츠의 일부인 시점과 텍스트도 다른 문자를 포함 합니다.  
  
-   요소의 텍스트 내용에 대 한 포함된 된 식에 서로 하는 경우입니다.  
  
 그렇지 않으면 컴파일러에서는으로 불필요 한 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 리터럴에 대 한 개체입니다.  
  
 무효 공백이 xml 리터럴에 포함 하려면 공백 리터럴 문자열이 포함 된 포함된 식을 사용 합니다.  
  
> [!NOTE]
>  경우는 `xml:space` 특성이 XML 요소 리터럴에에 나타날는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에서 특성을 포함 하는 <xref:System.Xml.Linq.XElement> 개체가 아니라이 특성에는 컴파일러에서 공백을 처리 하는 방법을 변경 하지 않습니다 추가 합니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 외부 및 내부 두 XML 요소를 포함합니다. 두 요소에 텍스트 내용에 공백이 포함 되어 있습니다. 공백 및 XML 요소가 포함 되어 있기 때문에 외부 요소에서 공백을 중요 하지 않습니다. 요소의 내부에서 공백을 기능은 공백 및 텍스트 포함 되어 있기 때문에 중요 합니다.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 실행 되는 경우이 코드는 다음 텍스트를 표시 합니다.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
