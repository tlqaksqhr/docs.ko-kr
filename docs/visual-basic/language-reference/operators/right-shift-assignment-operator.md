---
title: "&gt;&gt;= 연산자 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;= 연산자 (Visual Basic)
변수 또는 속성의 값에 산술 오른쪽 시프트를 수행 하 고 결과 다시 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 변수 또는 정수 계열 형식의 속성 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).  
  
 `amount`  
 필수 요소. 숫자 식으로 확대 되는 데이터 형식의 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 왼쪽에 요소는 `>>=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다. 변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `>>=` 연산자 먼저 변수 또는 속성의 값에 산술 오른쪽 시프트를 수행 합니다. 연산자는 다음 다시 변수 또는 속성에 해당 작업의 결과 할당 합니다.  
  
 이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다. 산술 오른쪽 시프트 연산 가장 오른쪽 위치를 넘어 이동 하는 비트는 무시 되 고 왼쪽 비트는 비워진 왼쪽 비트 위치로 전파 됩니다. 즉 `variableorproperty` 음수 값을 가진 비워진된 위치 1로 설정 됩니다. 경우 `variableorproperty` 이 양수인 경우 또는 해당 데이터 형식이 부호 없는 형식이 면 하는 경우 비워진된 위치 0으로 설정 됩니다.  
  
## <a name="overloading"></a>오버로딩  
 [>> 연산자](../../../visual-basic/language-reference/operators/right-shift-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 오버 로드는 `>>` 연산자의 동작에 영향을 줍니다는 `>>=` 연산자입니다. 코드에서 `>>=` 클래스 또는 구조체에 오버 로드에서 `>>`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `>>=` 의 비트 패턴을 이동할 연산자는 `Integer` 변수 오른쪽으로 지정 된 크기 및 결과를 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [>> 연산자](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
