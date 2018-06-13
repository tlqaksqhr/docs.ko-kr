---
title: 함수 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604889"
---
# <a name="function-expression-visual-basic"></a>함수 식(Visual Basic)
매개 변수 및 함수가 람다 식을 정의 하는 코드를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`parameterlist`|선택 사항입니다. 이 절차의 매개 변수를 나타내는 로컬 변수 이름의 목록. 괄호는 목록이 비어 있는 경우에 있어야 합니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|  
|`expression`|필수. 단일 식입니다. 식의 형식이 함수 반환 형식입니다.|  
|`statements`|필수. 문 목록을 사용 하 여 값을 반환 하는 `Return` 문. (참조 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md).) 반환 값의 유형 함수의 반환 형식이입니다.|  
  
## <a name="remarks"></a>설명  
 A *람다 식을* 계산 하 고 값을 반환 하는 이름 없는 함수입니다. 람다 식을 사용할 수 있습니다 인수를 제외 하 고 대리자를 사용할 수는 아무 곳 이나 `RemoveHandler`합니다. 대리자 및 대리자와 람다 식 사용 하는 방법에 대 한 자세한 내용은 참조 [대리자 문을](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.  
  
## <a name="lambda-expression-syntax"></a>람다 식 구문  
 람다 식의 구문 표준 함수와 유사합니다. 차이점은 다음과 같습니다.  
  
-   람다 식에 이름이 없습니다.  
  
-   람다 식은와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.  
  
-   람다 식 사용 하지 않는 프로그램 `As` 절을 함수 반환 형식을 지정 합니다. 대신, 유형은 한 줄 람다 식의 본문이 계산 되는 값 또는 여러 줄 람다 식의 반환 값에서 유추 됩니다. 예를 들어 한 줄 람다 식의 본문이 `Where cust.City = "London"`, 해당 반환 형식이 `Boolean`합니다.  
  
-   한 줄 람다 식의 본문은 문이 식 이어야 합니다. Function 프로시저를 호출 하지만 sub 프로시저를 호출 하지 본문 구성할 수 있습니다.  
  
-   데이터 형식 중 하나 또는 모두를 유추 합니다 모든 매개 변수에 지정 해야 합니다.  
  
-   선택 사항 및 Paramarray 매개 변수는 허용 되지 않습니다.  
  
-   제네릭 매개 변수가 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 간단한 람다 식을 만드는 두 가지 방법을 보여 줍니다. 첫 번째 예제는 `Dim` 함수에 대 한 이름을 제공 합니다. 함수를 호출 하려면 매개 변수 값에 보냅니다.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>예제  
 또는 선언 하 고 동시에 함수를 실행할 수 있습니다.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>예제  
 다음은 인수를 증가 시키고 값을 반환 하는 람다 식의 예입니다. 함수에 대 한 두에서는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다. 더 많은 예제를 참조 하십시오. [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>예제  
 람다 식의 쿼리 연산자의 여러 기반이 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], 메서드 기반 쿼리에 명시적으로 사용할 수 있습니다. 다음 예제에서는 일반적인 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리의 다음 메서드 형식을를 쿼리 합니다.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 쿼리 메서드에 대 한 자세한 내용은 참조 하십시오. [쿼리](../../../visual-basic/language-reference/queries/queries.md)합니다. 표준 쿼리 연산자에 대 한 자세한 내용은 참조 [표준 쿼리 연산자 개요](../../programming-guide/concepts/linq/standard-query-operators-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)  
 [값 비교](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [부울 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [If 연산자](../../../visual-basic/language-reference/operators/if-operator.md)  
 [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
