---
title: "Function Expression (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Function expression [Visual Basic]"
  - "functions [Visual Basic], function expressions"
  - "lambda expressions [Visual Basic], function expression"
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Function Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

함수 람다 식을 정의하는 코드 및 매개 변수를 선언합니다.  
  
## 구문  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`parameterlist`|선택적 요소.  이 프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록입니다.  목록이 비어 있는 경우에도 괄호는 있어야 합니다.  자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)를 참조하십시오.|  
|`expression`|필수 요소.  단일 식입니다.  식의 형식이 함수의 반환 형식입니다.|  
|`statements`|필수 요소.  `Return` 문을 사용하여 값을 반환하는 문의 목록입니다.  [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)을 참조하십시오. 반환 값의 형식이 함수의 반환 형식입니다.|  
  
## 설명  
 *람다 식*은 단일 값을 계산하고 반환하는 이름이 없는 함수입니다.  대리자 형식을 사용할 수 있는 모든 위치에 람다 식을 사용할 수 있습니다. 단 `RemoveHandler`에 대한 인수로는 사용할 수 없습니다.  대리자에 대한 정보 및 대리자와 함께 람다 식을 사용하는 방법은 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오.  
  
## 람다 식 구문  
 람다 식의 구문은 표준 함수의 구문과 유사합니다.  차이점은 다음과 같습니다.  
  
-   람다 식에는 이름이 없습니다.  
  
-   람다 식에는 `Overloads` 또는 `Overrides`와 같은 한정자가 있을 수 없습니다.  
  
-   람다 식은 `As` 절을 사용하여 함수의 반환 형식을 지정하지 않습니다.  대신 한 줄 람다 식의 본문이 평가되는 값 또는 여러 줄 람다 식의 반환 값에서 형식이 유추됩니다.  예를 들어 한 줄 람다 식의 본문이 `Where cust.City = "London"`이면 반환 형식은 `Boolean`입니다.  
  
-   한 줄로 된 람다 식의 본문은 문이 아니라 식이어야 합니다.  본문은 하위 프로시저에 대한 호출이 아니라 함수 프로시저에 대한 호출로 구성되어야 합니다.  
  
-   모든 매개 변수에 지정된 데이터 형식이 있거나 모든 매개 변수가 유추되어야 합니다.  
  
-   Optional 및 Paramarray 매개 변수가 허용되지 않습니다.  
  
-   제네릭 매개 변수가 허용되지 않습니다.  
  
## 예제  
 다음 예제에서는 간단한 람다 식을 만드는 두 가지 방법을 보여 줍니다.  첫 방법에서는 `Dim`을 사용하여 함수의 이름을 제공합니다.  함수를 호출하려면 매개 변수에 대한 값을 전달합니다.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## 예제  
 또는 함수를 동시에 선언하고 실행할 수 있습니다.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## 예제  
 다음 예제에서는 인수를 점증적으로 늘리고 값을 반환하는 람다 식입니다.  다음 예제에서는 한 줄과 여러 줄로 구성된 함수에 대한 람다 식 구문을 보여 줍니다.  추가 예제는 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)를 참조하십시오.  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## 예제  
 람다 식은 [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)]의 여러 쿼리 연산자의 기반이 되며 메서드 기반 쿼리에서 명시적으로 사용할 수 있습니다.  다음 예제에서는 일반적인 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리와 이 쿼리를 메서드 형식으로 변환한 코드를 보여 줍니다.  
  
```vb#  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 쿼리 메서드에 대한 자세한 내용은 [Queries](../../../visual-basic/language-reference/queries/queries.md)를 참조하십시오.  표준 쿼리 연산자에 대한 자세한 내용은 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)