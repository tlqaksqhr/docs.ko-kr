---
title: "Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32053"
  - "vbc32053"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32053"
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저는 해당 매개 변수 형식으로 확대 변환되는 인수로 호출되며 매개 변수에서 인수로 축소 변환됩니다.  
  
 클래스 또는 구조체를 정의할 때 하나 이상의 변환 연산자를 정의하여 해당 클래스 또는 구조체 형식을 다른 형식으로 변환할 수 있습니다.  또한 역변환 연산자를 정의하여 이들 다른 형식을 원래의 클래스 또는 구조체 형식으로 변환할 수도 있습니다.  프로시저 호출에서 클래스 또는 구조체 형식을 사용할 때 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 이러한 변환 연산자를 사용하여 인수의 형식을 해당 매개 변수의 형식으로 변환할 수 있습니다.  
  
 인수에 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)를 전달하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 참조를 전달하는 대신에 인수 값을 프로시저의 지역 변수에 복사합니다.  이러한 경우 프로시저가 반환되면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 지역 변수 값을 호출 코드의 인수에 다시 복사해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수와 매개 변수의 형식이 같으면 변환이 필요하지 않습니다.  그러나 형식이 다르면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 양방향으로 변환해야 합니다.  형식 중 하나가 사용자의 클래스 또는 구조체 형식이면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 이들 형식을 다른 형식과 양방향 변환해야 합니다.  이들 변환 중 하나가 확대 변환이면 역변환은 축소 변환이 됩니다.  
  
 **오류 ID:** BC32053  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 프로시저 매개 변수와 같은 형식의 호출 인수를 사용합니다. 그러면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 변환이 필요하지 않습니다.  
  
-   매개 변수 형식과 다른 인수 형식으로 프로시저를 호출해야 하지만 호출 인수에 값을 반환하지 않아도 되는 경우에는 매개 변수를 `ByRef` 대신 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)로 정의합니다.  
  
-   호출 인수에 값을 반환하려면, 가능한 경우 역변환 연산자를 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)으로 정의합니다.  
  
## 참고 항목  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)