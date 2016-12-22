---
title: "Sub Expression (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lambda expressions [Visual Basic], sub expression"
  - "Sub Expression [Visual Basic]"
  - "subroutines [Visual Basic], sub expressions"
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

서브루틴 람다 식을 정의하는 코드 및 매개 변수를 선언합니다.  
  
## 구문  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`parameterlist`|선택적 요소.  프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록입니다.  목록이 비어 있는 경우에도 괄호는 있어야 합니다.  자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)를 참조하십시오.|  
|`statement`|필수 요소.  단일 문입니다.|  
|`statements`|필수 요소.  문의 목록입니다.|  
  
## 설명  
 *람다 식*은 이름이 없고 하나 이상의 문을 실행하는 서브루틴입니다.  대리자 형식을 사용할 수 있는 모든 위치에 람다 식을 사용할 수 있습니다. 단 `RemoveHandler`에 대한 인수로는 사용할 수 없습니다.  대리자에 대한 정보 및 대리자와 함께 람다 식을 사용하는 방법은 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오.  
  
## 람다 식 구문  
 람다 식의 구문은 표준 서브루틴의 구문과 유사합니다.  차이점은 다음과 같습니다.  
  
-   람다 식에는 이름이 없습니다.  
  
-   람다 식에는 `Overloads` 또는 `Overrides`와 같은 한정자가 있을 수 없습니다.  
  
-   한 줄로 된 람다 식의 본문은 식이 아니라 문이어야 합니다.  본문은 함수 프로시저에 대한 호출이 아니라 하위 프로시저에 대한 호출로 구성할 수 있습니다.  
  
-   람다 식에서는 모든 매개 변수에 지정된 데이터 형식이 있거나 모든 매개 변수가 유추되어야 합니다.  
  
-   람다 식에는 선택적 및 `ParamArray` 매개 변수가 허용되지 않습니다.  
  
-   람다 식에는 제네릭 매개 변수가 허용되지 않습니다.  
  
## 예제  
 다음 예제는 콘솔에 값을 쓰는 람다 식입니다.  다음 예제에서는 한 줄과 여러 줄로 구성된 서브루틴에 대한 람다 식 구문을 보여 줍니다.  추가 예제는 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)를 참조하십시오.  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## 참고 항목  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)