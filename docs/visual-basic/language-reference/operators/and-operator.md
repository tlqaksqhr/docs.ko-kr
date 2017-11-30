---
title: "And 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>And 연산자(Visual Basic)
두 개의에 논리 결합을 수행 `Boolean` 식 또는 두 숫자 식에 비트 결합 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다. 부울 비교 `result` 는 두 논리 결합 `Boolean` 값입니다. 비트 연산에 대 한 `result` 는 두 개의 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 부울 비교 `result` 은 `True` 두 경우에 `expression1` 및 `expression2` 로 평가 `True`합니다. 다음 표에서 설명 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 은|및 `expression2` 은|값 `result` 은|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  부울 비교에는 `And` 연산자는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다. [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 수행 *단락 (short-circuiting)*, 즉 `expression1` 은 `False`, 다음 `expression2` 평가 되지 않습니다.  
  
 숫자 값에 적용할 경우의 `And` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.  
  
|경우에 비트 `expression1` 은|비트 `expression2` 은|에 있는 비트 `result` 은|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확한 결과를 얻으려면 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 피연산자 중 하나의 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (-1에 대 한 `True` 하 고 0을 `False`) 연산을 수행 하 고 합니다.  
  
 부울 비교에 대 한 데이터의 결과 형식이 `Boolean`합니다. 비트 비교 결과 데이터 형식은의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다. "관계 및 비트 비교" 표를 참조 [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
> [!NOTE]
>  `And` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `And` 두 식에 논리 결합을 수행 하는 연산자입니다. 결과 한 `Boolean` 두 식이 모두 되는지 여부를 나타내는 값 `True`합니다.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 앞 예제의 결과는 `True` 및 `False`각각.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `And` 두 숫자 식의 개별 비트에 논리 결합을 수행 하는 연산자입니다. 피연산자의 해당 비트가 모두 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 앞의 예제는 각각 8, 2 및 0의 결과 생성합니다.  
  
## <a name="see-also"></a>참고 항목  
 [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
