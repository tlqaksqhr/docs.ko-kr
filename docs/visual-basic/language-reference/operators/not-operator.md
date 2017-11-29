---
title: "Not 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a>Not 연산자(Visual Basic)
논리 부정을 수행는 `Boolean` 식 또는 숫자 식에 비트 부정을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 `Boolean` 식, 다음 표에서 설명 방법을 `result` 결정 됩니다.  
  
|경우 `expression` 은|값 `result` 은|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 숫자 식에 대 한는 `Not` 임의의 숫자 식의 비트 값을 반전 하 고의 해당 비트를 설정 하는 연산자 `result` 다음 표에 따라 합니다.  
  
|경우에 비트 `expression` 은|에 있는 비트 `result` 은|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 부울 부정에 대 한 데이터의 결과 형식이 `Boolean`합니다. 비트 부정에 대 한 결과 데이터 형식이 구문과 같습니다 `expression`합니다. 그러나 식이 `Decimal`, 결과 `Long`합니다.  
  
## <a name="overloading"></a>오버로딩  
 `Not` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Not` 에 논리 부정을 수행 하는 연산자는 `Boolean` 식입니다. 결과는 `Boolean` 식의 값의 역순을 나타내는 값입니다.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 앞 예제의 결과는 `False` 및 `True`각각.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Not` 숫자 식의 개별 비트의 논리 부정을 수행 하는 연산자입니다. 결과 패턴의 비트는 부호 비트를 포함 하 여 피연산자 패턴에 해당 비트의 역순으로 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 앞의 예제는 각각 – 11, – 9,-7의 결과 생성합니다.  
  
## <a name="see-also"></a>참고 항목  
 [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
