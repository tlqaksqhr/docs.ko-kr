---
title: "- 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7f45094da7bc61687d9c767d25858aa214bf1978
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

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
 결과 차이점은 `expression1` 및 `expression2`, 또는의 부정된 값 `expression1`합니다.  
  
 결과 데이터 형식이의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다. "정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식입니다. 부호 없는 및 부동 소수점 형식 포함 및 `Decimal`합니다.  
  
## <a name="remarks"></a>설명  
 이전에 표시 된 구문에 나오는 첫 번째 사용에는 `–` 연산자는는 *이진* 두 숫자 식의 차이점에 대 한 산술 빼기 연산자입니다.  
  
 이전에 표시 된 구문에 나오는 두 번째 사용은 `–` 연산자는는 *단항* 부정 연산자는 식의 음수 값입니다. 이런이 의미에서 부정은의 부호를 반대로 `expression1` 결과 양수 경우 `expression1` 음수입니다.  
  
 두 식 중 하나가 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), `–` 연산자&0;으로 처리 합니다.  
  
> [!NOTE]
>  `–` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스 또는 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `–` 연산자를 계산 하 여 두 숫자 간의 차이 반환 하 고 숫자를 부정 합니다.  
  
 [!code-vb[VbVbalrOperators #&10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 이러한 문을 실행 하 고는 `binaryResult` 124.45 포함 및 `unaryResult` –334.90을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Visual Basic의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

