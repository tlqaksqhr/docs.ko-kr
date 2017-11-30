---
title: "변수 &#39; &lt;variablename&gt;&#39; 바깥쪽 블록의 변수를 숨깁니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>변수 &#39; &lt;variablename&gt;&#39; 바깥쪽 블록의 변수를 숨깁니다.
블록에 포함 된 변수의 동일한 이름으로 다른 지역 변수에 있습니다.  
  
 **오류 ID:** BC30616  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   블록 내부에서 변수를 이름을 다른 지역 변수와 동일 하지 않습니다. 예:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   이 오류에 대 한 일반적인 원인의 사용입니다 `Catch e As Exception` 이벤트 처리기 내 합니다. 이 경우 이름을 `Catch` 블록 변수가 `ex` 대신 `e`합니다.  
  
-   이 오류가 발생 하는 또 다른 일반적인 소스 내에서 선언 된 지역 변수에 액세스 하려고 하는 한 `Try` 별개의 차단 `Catch` 블록입니다. 이 문제를 해결 하려면 외부 변수를 선언에서 `Try...Catch...Finally` 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
