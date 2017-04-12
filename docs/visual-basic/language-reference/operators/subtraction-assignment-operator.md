---
title: "-= 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: f640bd288c677954bae189c2e86ef096e7a73a2b
ms.lasthandoff: 03/13/2017

---
# <a name="--operator-visual-basic"></a>-= 연산자(Visual Basic)
변수 또는 속성의 값에서 식의 값을 빼고 변수 또는 속성에 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>주의  
 왼쪽에는 요소는 `-=` 연산자는 단순 스칼라 변수, 속성 또는 배열의 요소를 사용할 수 있습니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `-=` 연산자는 변수 또는 연산자의 왼쪽) (에 대 한 속성의 값에서 먼저 (연산자의 오른쪽)에 대 한 식의 값을 뺍니다. 연산자는 다음 변수 또는 속성에 해당 작업의 결과 할당 합니다.  
  
## <a name="overloading"></a>오버로딩  
 [-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 오버 로드는 `-` 연산자의 동작에 영향을 줍니다는 `-=` 연산자입니다. 코드를 사용 하는 경우 `-=` 클래스 또는 구조체에 오버 로드에서 `-`, 다시 정의 된 동작을 알고 있어야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `-=` 연산자를 빼면 `Integer` 에서 다른 변수 및 결과를 두 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators #&11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)   
 [대입 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Visual Basic의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [문](../../../visual-basic/programming-guide/language-features/statements.md)

