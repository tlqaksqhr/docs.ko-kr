---
title: "Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36548"
  - "vbc36548"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36548"
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러에서는 익명 형식의 속성 하나가 익명 형식의 다른 속성을 초기화하는 데 사용되는 경우, 해당 익명 형식을 식 트리로 변환하는 것을 허용하지 않습니다.  예를 들어 다음 코드에서 `Prop1`은 초기화 목록에 선언된 후 `Prop2`의 초기 값으로 사용됩니다.  
  
```vb#  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **오류 ID:** BC36548  
  
### 이 오류를 해결하려면  
  
-   `Prop1`의 초기 값으로 지역 변수를 할당한 후  다음 코드와 같이 이 변수를 `Prop1`과 `Prop2` 모두에 할당합니다.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## 참고 항목  
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 식 트리를 사용하여 동적 쿼리 빌드](../Topic/How%20to:%20Use%20Expression%20Trees%20to%20Build%20Dynamic%20Queries%20\(C%23%20and%20Visual%20Basic\).md)