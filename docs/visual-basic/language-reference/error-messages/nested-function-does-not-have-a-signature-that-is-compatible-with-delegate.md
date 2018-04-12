---
title: 중첩 된 함수에 대리자 &#39;에 호환 되는 서명이 없는 &lt;delegatename&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>중첩 된 함수에 대리자 &#39;에 호환 되는 서명이 없는 &lt;delegatename&gt;&#39;
람다 식에 호환 되지 않는 서명이 대리자에 할당 되었습니다. 예를 들어 다음 코드를 위임할 `Del` 은 두 개의 정수 매개 변수입니다.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 하나의 인수를 포함 하는 람다 식을 형식으로 선언 된 경우 오류는 발생 `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **오류 ID:** BC36532  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   시그니처는 호환 되도록 할당 된 람다 식 또는 대리자 정의 조정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
