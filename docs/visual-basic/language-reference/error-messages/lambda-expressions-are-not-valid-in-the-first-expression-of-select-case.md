---
title: 람다 식의 첫 번째 식에 유효 하지 않은 &#39; 대/소문자 &#39;를 선택 합니다. 문
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>람다 식의 첫 번째 식에 유효 하지 않은 &#39; 대/소문자 &#39;를 선택 합니다. 문
테스트 식에 람다 식을 사용할 수 없습니다는 `Select Case` 문. 람다 식 정의는 함수를 테스트 식의 반환을 `Select Case` 문은 기본 데이터 형식 이어야 합니다.  
  
 다음 코드에이 오류가 발생합니다.  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **오류 ID:** BC36635  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   코드를 검사하여 `If...Then...Else` 문과 같은 다른 조건부 생성이 적합한지 결정합니다.  
  
-   계획 했던 함수를 호출 하려면 다음 코드에 나와 있는 것 처럼:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Select...Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)
