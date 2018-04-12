---
title: '연산자 선언 중 하나 여야 합니다: +,-, *,-,-, ^, &amp;, 같은, Mod, 및, Or, Xor, Not, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>연산자 선언 중 하나 여야 합니다: +,-, *,\,/, ^, &amp;, 같은, Mod, 및, Or, Xor, Not, &lt; &lt;, &gt; &gt;...
오버 로드할 수 있는 연산자만 선언할 수 있습니다. 다음 표에서 연산자를 선언할 수 있습니다.  
  
|형식|연산자|  
|----------|---------------|  
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|이항|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|변환(단항)|`CType`|  
  
 `=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.  
  
 **오류 ID:** BC33000  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.  
  
2.  직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
