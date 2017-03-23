---
title: "즉, 의사 결정 구조 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: c69b487322dc75ae8d54f42c1c62f8f5cc35757d
ms.lasthandoff: 03/13/2017

---
# <a name="decision-structures-visual-basic"></a>판단 구조(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]조건을 테스트 하 고 해당 테스트의 결과 따라 다른 작업을 수행할 수 있습니다. True 또는 false 이면 식의 다양 한 값 또는 일련의 문 실행할 때 생성 되는 다양 한 예외에 대 한 조건에 대해 테스트할 수 있습니다.  
  
 다음 그림에는 조건이 true 인지 테스트 하 고 true 또는 false 인지에 따라 다른 작업을 수행 하는 의사 결정 구조를 보여 줍니다.  
  
 ![If의 순서도... 다음 중... 다른 생성](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
조건이 true와 false 하는 경우 다른 작업을 수행 합니다.  
  
## <a name="ifthenelse-construction"></a>다음과 같은 경우... 다음 중... 다른 생성  
 `If...Then...Else`구문을 사용 하면 하나 이상의 조건을 테스트 하 고 각 조건에 따라 하나 이상의 문을 실행 합니다. 조건을 테스트 하 고 다음과 같은 방법으로 작업을 수행할 수 있습니다.  
  
-   조건이 하나 이상의 문 실행`True`  
  
-   조건이 하나 이상의 문 실행`False`  
  
-   조건이 일부 문을 실행 `True` 및 다른 경우`False`  
  
-   이전 조건이 추가 조건을 테스트 합니다.`False`  
  
 이러한 모든 가능성을 제공 하는 제어 구조는 [경우... 다음 중... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다. 하나의 테스트와 실행 하는 문이 있는 경우 단일 행 버전을 사용할 수 있습니다. 좀 더 복잡 한 조건 및 작업 집합이 있으면 여러 행 버전을 사용할 수 있습니다.  
  
## <a name="selectcase-construction"></a>선택... Case 구문  
 `Select...Case` 생성 식을 한 번 평가 하 고 여러 다른 가능한 값을 기반으로 하는 문을 실행할 수 있습니다. 자세한 내용은 참조 [선택... Case 문](../../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.  
  
## <a name="trycatchfinally-construction"></a>시도 중... Catch... 마지막으로 생성  
 `Try...Catch...Finally`구문을 사용 하 여 문 중 하나는 예외가 발생 하는 경우 제어를 유지 하는 환경에서 문 집합을 실행할 수 있습니다. 다른 예외에 대 한 다양 한 작업을 수행할 수 있습니다. 전체를 종료 하기 전에 실행 되는 코드 블록을 선택적으로 지정할 수 `Try...Catch...Finally` 어떤 일이 발생 하는 것에 관계 없이 생성 합니다. 자세한 내용은 참조 [시도 중... Catch... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.  
  
> [!NOTE]
>  대부분의 제어 구조에 대 한 키워드를 클릭할 때 모든 구조에 키워드가 강조 표시 됩니다. 예를 들어, 클릭 하면 `If` 에 `If...Then...Else` 생성, 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다. 다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [중첩된 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If 연산자](../../../../visual-basic/language-reference/operators/if-operator.md)
