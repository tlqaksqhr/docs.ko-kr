---
title: '- 연산자 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ffb7c96fe95e73dc857a15608df94ed8468f9df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a>- 연산자(Visual Basic)
두 숫자 식 또는 숫자 식의 음수 값의 차이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>요소  
 `expression1`  
 필수 요소. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수 하지 않는 경우는 `–` 연산자가 음수 값을 계산 합니다. 임의의 숫자 식입니다.  
  
## <a name="result"></a>결과  
 결과 차이 `expression1` 및 `expression2`, 또는의 부정된 값 `expression1`합니다.  
  
 결과 데이터 형식이 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다. "정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식입니다. 여기에 서명 되지 않은 부동 소수점 형식과 및 `Decimal`합니다.  
  
## <a name="remarks"></a>설명  
 이전에 나와 있는 구문에서 표시 된 첫 번째 사용에는 `–` 연산자는는 *이진* 두 숫자 식의 차이점에 대해 빼기 산술 연산자.  
  
 이전에 나와 있는 구문에 표시 된 두 번째 사용에서는 `–` 연산자는는 *단항* 부정 연산자는 식의 음수 값입니다. 이러한 관점에서 부정은의 부호를 반대로 `expression1` 결과 양수 경우 `expression1` 음수입니다.  
  
 두 식 중 하나가 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), `–` 연산자 0으로 처리 합니다.  
  
> [!NOTE]
>  `–` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `–` 계산 하 고 두 숫자 간의 차이 반환 하는 연산자 및 숫자를 부정 합니다.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 이러한 문 실행 한 후 다음 `binaryResult` 124.45 포함 및 `unaryResult` –334.90을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
