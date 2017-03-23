---
title: "Boolean Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.FALSE"
  - "vb.TRUE"
  - "vb.Boolean"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean data type"
  - "Boolean values, False keyword"
  - "False keyword [Visual Basic]"
  - "True keyword [Visual Basic]"
  - "Boolean values, True keyword"
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Boolean Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`True`나 `False`만 될 수 있는 값입니다.  `True`와 `False` 키워드는 `Boolean` 변수의 두 가지 상태에 해당합니다.  
  
## 설명  
 true\/false, yes\/no 또는 on\/off 같은 두 가지 상태의 값을 포함하려면 [Boolean Data Type \(Visual Basic\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)을 사용합니다.  
  
 `Boolean`의 기본값은 `False`입니다.  
  
 `Boolean` 값은 숫자로 저장되지 않고 저장된 값은 숫자가 아닙니다.  `True`와 `False`를 숫자 값으로 나타내도록 코드를 작성하지 마십시오.  `Boolean` 변수에는 가능하면 원래 용도에 맞는 논리 값이 사용되도록 제한해야 합니다.  
  
## 형식 변환  
 Visual Basic에서 숫자 데이터 형식 값을 `Boolean`으로 변환하는 경우 0은 `False`가 되고 다른 모든 값은 `True`가 됩니다.  Visual Basic에서 `Boolean` 값을 숫자 값으로 변환하는 경우 `False`는 0이 되고 `True`는 \-1이 됩니다.  
  
 `Boolean` 값과 숫자 데이터 형식을 상호 변환할 때는 .NET Framework 변환 메서드 실행 결과가 Visual Basic 변환 키워드의 경우와 동일하지 않을 수도 있음을 염두에 두어야 합니다.  이렇게 결과가 다를 수 있는 이유는 Visual Basic에서 수행되는 변환 과정에 이전 버전과 호환되는 동작이 있기 때문입니다.  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)의 "숫자 형식으로 정확하게 변환되지 않는 부울 형식"을 참조하십시오.  
  
## 프로그래밍 팁  
  
-   **음수.** `Boolean`은 숫자 형식이 아니므로 음의 값을 나타낼 수 없습니다.  어떤 경우이든 `Boolean`에 숫자 값을 지정할 수는 없습니다.  
  
-   **형식 문자.** `Boolean`에는 리터럴 형식 문자나 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Boolean?displayProperty=fullName> 구조체입니다.  
  
## 예제  
 다음 예제에서 `runningVB`은 `Boolean` 변수이며 yes\/no 설정값만을 저장합니다.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## 참고 항목  
 <xref:System.Boolean?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)