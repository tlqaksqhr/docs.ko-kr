---
title: '&amp;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a>&amp;= 연산자 (Visual Basic)
연결 하는 `String` 식을 `String` 변수 또는 속성 변수 또는 속성에는 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 모든 `String` 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 `String` 식입니다.  
  
## <a name="remarks"></a>설명  
 왼쪽에 요소는 `&=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다. 변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다. `&=` 연산자는 연결의 `String` 는 오른쪽에 식이 `String` 변수나 속성의 왼쪽에는 결과를 변수나 속성의 왼쪽에 할당 합니다.  
  
## <a name="overloading"></a>오버로딩  
 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 오버 로드는 `&` 연산자의 동작에 영향을 줍니다는 `&=` 연산자입니다. 코드에서 `&=` 클래스 또는 구조체에 오버 로드에서 `&`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `&=` 연산자를 두 개의 `String` 변수 및 결과 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [+= 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
