---
title: "First operand in a binary &#39;If&#39; expression must be nullable or a reference type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33107"
  - "vbc33107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33107"
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# First operand in a binary &#39;If&#39; expression must be nullable or a reference type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`If` 식에는 두 개 또는 세 개의 인수를 사용할 수 있습니다.  인수를 두 개만 지정할 경우에는 첫 번째 인수가 참조 형식이거나 nullable 형식이어야 합니다.  첫 번째 인수가 `Nothing` 이외의 값으로 계산되면 첫 번째 인수의 값이 반환됩니다.  첫 번째 인수가 `Nothing`으로 계산되면 두 번째 인수가 계산되어 해당 값이 반환됩니다.  
  
 예를 들어 다음 코드에는 두 개의 `If` 식이 포함되어 있으며 이 중에서 하나는 세 개의 인수를 사용하고 다른 하나는 두 개의 인수를 사용합니다.  이 두 식은 계산 결과 같은 값을 반환합니다.  
  
```vb#  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 다음 식에서 이 오류가 발생합니다.  
  
```vb#  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **오류 ID:** BC33107  
  
### 이 오류를 해결하려면  
  
-   첫 번째 인수가 nullable 형식 또는 참조 형식이 되도록 코드를 변경할 수 없는 경우, 세 개의 인수를 사용하는 `If` 식으로 변환하거나 `If...Then...Else` 문으로 변환합니다.  
  
    ```vb#  
    Console.WriteLine(If(choice1 < choice2, 1, 2))  
    Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
    ```  
  
## 참고 항목  
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)