---
title: "유형의 &#39; &lt;variablename&gt;&#39; 루프 범위와 단계 변수가 같은 형식으로 확대 되지 않으므로 유추할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords: BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>유형의 &#39; &lt;variablename&gt;&#39; 루프 범위와 단계 변수가 같은 형식으로 확대 되지 않으므로 유추할 수 없습니다.
사용자가 작성 한 `For...Next` 루프는 다음 조건에 해당 하기 때문에 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.  
  
-   `As` 절을 사용하여 루프 제어 변수의 데이터 형식을 지정하지 않았습니다.  
  
-   루프 범위와 단계 변수에 두 개 이상의 데이터 형식이 포함되어 있습니다.  
  
-   데이터 형식 간의 표준 변환이 없습니다.  
  
 따라서 컴파일러는 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.  
  
 다음 예에서 단계 변수는 문자가 고 루프 범위는 모두 정수입니다. 문자와 정수 간에 변환 작업 없이 표준 이기 때문에이 오류가 보고 됩니다.  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **오류 ID:** BC30982  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   다른 항목으로 확장 된 형식이 하나 이상 있도록 루프 범위와 단계 변수가 필요에 따라의 종류를 변경 합니다. 앞의 예제에서 변경 유형을 `stepVar` 를 `Integer`합니다.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     또는  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   루프 범위와 단계 변수에 적합 한 형식으로 변환 하려면 명시적 변환 함수를 사용 합니다. 앞의 예제에서 적용 된 `Val` 함수를 `stepVar`합니다.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
