---
title: "배타적 or 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b14f11f2df2df9c29e88e9188390cfe245d2cb58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xor-operator-visual-basic"></a>배타적 or 연산자(Visual Basic)
에 두 논리 제외를 수행 `Boolean` 식 또는 두 숫자 식에 비트 제외 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 변수입니다. 부울 비교 `result` 는 두 논리 제외 (배타적 논리합) `Boolean` 값입니다. 비트 연산에 대 한 `result` 는 두 개의 숫자 비트 패턴의 배타적 비트 연산 (배타적 비트 논리합)를 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 부울 비교 `result` 은 `True` 경우에 중 하나만 `expression1` 및 `expression2` 계산 `True`합니다. 즉, 경우에 `expression1` 및 `expression2` 평가 반대 `Boolean` 값입니다. 다음 표에서 설명 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 은|및 `expression2` 은|값 `result` 은|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  부울 비교에는 `Xor` 연산자는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다. 에 해당 하는 단락 항목이 `Xor`, 결과 항상 두 피연산자 모두에 종속 되기 때문입니다. 에 대 한 *단락 (short-circuiting)* 논리 연산자 참조 [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 및 [OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md)합니다.  
  
 비트 연산에 대 한는 `Xor` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.  
  
|경우에 비트 `expression1` 은|비트 `expression2` 은|에 있는 비트 `result` 은|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.  
  
 예를 들어 5 `Xor` 3은 6입니다. 그 이유를 확인 하려면, 101 및 011 해당 이진 표현으로 5와 3을 변환 합니다. 그런 다음 인지 확인할 수 101 Xor 011 110 6 10 진수 숫자의 이진 표현 되는 이전 표를 사용 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 피연산자 중 하나의 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (-1에 대 한 `True` 하 고 0을 `False`) 연산을 수행 하 고 합니다.  
  
 에 대 한는 `Boolean` 비교 데이터의 결과 형식이 `Boolean`합니다. 비트 비교 결과 데이터 형식은의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다. "관계 및 비트 비교" 표를 참조 [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 `Xor` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 알고 있어야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Xor` 두 식에 논리 제외 (배타적 논리합)를 수행 하는 연산자입니다. 결과 한 `Boolean` 식 중 정확히 하나 인지 여부를 나타내는 값 `True`합니다.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 이전 예제의 결과는 `False`, `True`, 및 `False`각각.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Xor` 두 숫자 식의 개별 비트에 논리 제외 (배타적 논리합)를 수행 하는 연산자입니다. 피연산자의 해당 비트 중 정확히 하나를 1로 설정 하는 경우 결과 패턴의 비트가 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 이전 예제의 결과는 2, 12, 및 14, 각각.  
  
## <a name="see-also"></a>참고 항목  
 [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
