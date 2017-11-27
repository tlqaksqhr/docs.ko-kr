---
title: "하위 식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a>하위 식(Visual Basic)
매개 변수 및 서브루틴 람다 식을 정의 하는 코드를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`parameterlist`|선택 사항입니다. 목록 프로시저의 매개 변수를 나타내는 지역 변수 이름입니다. 괄호는 목록이 비어 있는 경우에 있어야 합니다. 자세한 내용은 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|  
|`statement`|필수 요소. 단일 문입니다.|  
|`statements`|필수 요소. 문 목록입니다.|  
  
## <a name="remarks"></a>설명  
 A *람다 식을* 이름을 없는 서브루틴은 및 하나 이상의 문을 실행 하는 합니다. 어디 람다 식을 사용할 수는 있습니다으로 사용할 수 대리자 형식을 제외 하 고 인수를 `RemoveHandler`합니다. 대리자 및 대리자와 람다 식 사용 하는 방법에 대 한 자세한 내용은 참조 [대리자 문을](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.  
  
## <a name="lambda-expression-syntax"></a>람다 식 구문  
 람다 식의 구문은 유사 표준 서브루틴의 합니다. 차이점은 다음과 같습니다.  
  
-   람다 식에 이름이 없습니다.  
  
-   람다 식에는 한정자와 같은 없습니다 `Overloads` 또는 `Overrides`합니다.  
  
-   한 줄 람다 식의 본문에는 문, 식 하지 이어야 합니다. Sub 프로시저를 호출 하지만 function 프로시저를 호출 하지 본문 구성할 수 있습니다.  
  
-   람다 식에서 모든 매개 변수에 지정 된 데이터 형식이 나 모든 매개 변수를 유추 합니다.  
  
-   선택적 및 `ParamArray` 매개 변수는 람다 식에 허용 되지 않습니다.  
  
-   제네릭 매개 변수 람다 식에 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음은 콘솔에는 값을 작성 하는 람다 식의 예입니다. 서브루틴에 대 한 두에서는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다. 더 많은 예제를 참조 하십시오. [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)  
 [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
