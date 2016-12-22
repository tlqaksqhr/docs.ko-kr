---
title: "Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30982"
  - "vbc30982"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30982"
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

작성한 `For...Next` 루프에서 다음과 같은 조건으로 인해 컴파일러가 루프 컨트롤 변수의 데이터 형식을 유추할 수 없습니다.  
  
-   `As` 절을 사용하여 루프 컨트롤 변수의 데이터 형식을 지정하지 않았습니다.  
  
-   루프 범위와 단계 변수에 둘 이상의 데이터 형식이 있습니다.  
  
-   데이터 형식 사이에 가능한 표준 변환이 없습니다.  
  
 따라서 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.  
  
 다음 예제에서는 단계 변수는 문자이고 루프 범위는 둘 모두 정수입니다.  문자와 정수 사이에는 표준 변환이 가능하지 않기 때문에 이 오류가 보고됩니다.  
  
```vb#  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **오류 ID:** BC30982  
  
### 이 오류를 해결하려면  
  
-   필요에 따라 루프 범위 및 단계 변수의 형식 중 하나 이상을 다른 형식이 확대 변환될 수 있는 형식으로 변경합니다.  앞의 예제에서 `stepVar`의 형식을 `Integer`로 변경합니다.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     — 또는 —  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   명시적 변환 함수를 사용하여 루프 범위 및 단계 변수를 적절한 형식으로 변환합니다.  앞의 예제에서 `Val` 함수를 `stepVar`에 적용합니다.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)