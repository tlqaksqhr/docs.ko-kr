---
title: "&lt;&lt;연산자 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56cfb227f7e5c68de802c1f2cfb842a770f65ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;연산자 (Visual Basic)
비트 패턴에 산술 왼쪽된 시프트를 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 정수 계열 숫자 값입니다. 변화 하는 비트 패턴의 결과입니다. 데이터 형식이 같습니다 `pattern`합니다.  
  
 `pattern`  
 필수 요소. 정수 계열 숫자 식입니다. 이동할 비트 패턴입니다. 데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).  
  
 `amount`  
 필수 요소. 숫자 식입니다. 비트 패턴을 이동할 비트 수를 지정 합니다. 데이터 형식이 있어야 `Integer` 으로 확장 또는 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다. 산술 왼쪽 시프트 연산 결과 데이터 형식의 범위를 넘어 이동 하는 비트는 무시 되 고 오른쪽에 비워진 비트 위치 0으로 설정 됩니다.  
  
 Visual Basic의 값을 마스크 비트 결과 표시할 수 있는 양보다 더 많은 횟수가 shift를 방지 하려면 `amount` 의 데이터 형식에 해당 하는 크기 마스크로 `pattern`합니다. 이러한 값의 이진 AND 시프트 횟수에 대 한 사용 됩니다. 마스크 크기는 다음과 같습니다.  
  
|데이터 형식`pattern`|크기 마스크 (10 진수)|마스크 크기 (16 진수)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 경우 `amount` 0의 값이 `result` 의 값과 일치 `pattern`합니다. 경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크를 사용 합니다.  
  
 이동 하는 산술 오버플로 예외를 생성 하지 않습니다.  
  
> [!NOTE]
>  `<<` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<<` 연산자 왼쪽 시프트 정수 값에 산술 연산을 수행 합니다. 결과는 항상 동일한 데이터 이동 되는 식과 같은 형식을 갖습니다.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 이전 예의 결과 다음과 같습니다.  
  
-   `result1`192 (0000 0000 1100 0000)입니다.  
  
-   `result2`3072 (1100 0000 0000 0000)입니다.  
  
-   `result3`-32768 (0000 0000 0000 1000)입니다.  
  
-   `result4`384 (0001 1000 0000 0000)입니다.  
  
-   `result5`0 (왼쪽으로 15 자리 이동된)입니다.  
  
 에 대 한 시프트 횟수가 `result4` 17 같이 계산 됩니다. 1 및 15입니다.  
  
## <a name="see-also"></a>참고 항목  
 [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<<= 연산자](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
