---
title: "Passing Arguments by Value and by Reference (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByRef keyword, passing arguments by reference"
  - "Visual Basic code, procedures"
  - "passing arguments, by value or by reference"
  - "ByVal keyword, passing arguments by value"
  - "arguments [Visual Basic], passing by value or by reference"
  - "argument passing, by value or by reference"
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Passing Arguments by Value and by Reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 인수를 프로시저에 *값으로* 또는 *참조로* 전달할 수 있습니다.  이러한 *전달 메커니즘*에 따라 프로시저에서 호출 코드의 내부 인수로 사용하는 프로그래밍 요소를 수정할 수 있는지 여부가 결정됩니다.  프로시저 선언에서는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 지정하여 각 매개 변수의 전달 메커니즘을 결정합니다.  
  
## 차이점  
 인수를 프로시저에 전달할 때는 서로 영향을 줄 수 있는 다음 몇 가지 차이점에 주의해야 합니다.  
  
-   해당 프로그래밍 요소를 수정할 수 있는지 여부  
  
-   인수 자체를 수정할 수 있는지 여부  
  
-   인수를 값으로 전달하는지 아니면 참조로 전달하는지  
  
-   인수 데이터 형식이 값 형식인지 아니면 참조 형식인지  
  
 자세한 내용은 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md) 및 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)를 참조하십시오.  
  
## 전달 메커니즘의 선택  
 각각의 인수에 대해 전달 메커니즘을 주의해서 선택해야 합니다.  
  
-   **보호**.  두 전달 메커니즘 중 하나를 선택할 때 가장 중요한 기준은 호출 변수의 변경 가능 여부입니다.  `ByRef`로 인수를 전달하면 프로시저가 해당 인수를 통해 호출 코드로 값을 반환할 수 있다는 장점이 있고  `ByVal`로 인수를 전달하면 프로시저가 변경하지 못하도록 변수를 보호할 수 있습니다.  
  
-   **성능**.  전달 메커니즘이 코드 성능에 영향을 미칠 수 있으나 큰 차이는 없습니다.  여기에서 한 가지 예외는 `ByVal`로 전달되는 값 형식입니다.  이 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 인수의 전체 데이터 내용을 복사하므로  구조체처럼 큰 값 형식의 경우는 `ByRef`로 전달하는 것이 더 효율적입니다.  
  
     참조 형식의 경우는 데이터에 대한 포인터만 복사됩니다\(32비트 플랫폼은 4바이트, 64비트 플랫폼은 8바이트\).  따라서 성능에 영향을 주지 않고 `String` 또는 `Object` 형식의 인수를 값으로 전달할 수 있습니다.  
  
## 전달 메커니즘의 결정  
 프로시저를 선언할 때 각 매개 변수의 전달 메커니즘을 지정합니다.  호출 코드에서 재정의할 수 없습니다.는 `ByVal` 메커니즘입니다.  
  
 매개 변수를 선언 하는 경우 `ByRef`, 메커니즘을 호출 하는 코드를 강제로 수 있습니다 `ByVal` 으로 괄호 안에 호출에서 인수 이름을 둘러싸는.  자세한 내용은 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)을 참조하십시오.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 기본적으로 인수를 값으로 전달합니다.  
  
## 인수를 값으로 전달해야 하는 경우  
  
-   내부 인수로 사용하는 호출 코드 요소가 수정할 수 없는 요소이면 해당 매개 변수를 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 선언합니다.  수정할 수 없는 요소의 값은 어떤 코드에서도 변경할 수 없습니다.  
  
-   해당 요소가 수정할 수 있는 요소이지만 프로시저에서 해당 값을 변경하지 못하도록 하려면 매개 변수를 `ByVal`로 선언합니다.  호출 코드에서는 값으로 전달된 수정 가능한 요소의 값만 변경할 수 있습니다.  
  
## 인수를 참조로 전달해야 하는 경우  
  
-   프로시저의 호출 코드에서 해당 요소를 반드시 변경해야 하는 경우 해당 매개 변수를 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 선언합니다.  
  
-   호출 코드에서 해당 요소를 변경해야만 프로시저 코드가 올바르게 실행되는 경우 매개 변수를 `ByRef`로 선언합니다.  인수를 값으로 전달하는 경우 또는 호출 코드에서 인수를 괄호로 묶어 `ByRef` 전달 메커니즘을 재정의하는 경우에는 프로시저 호출에서 예기치 않은 결과가 발생할 수 있습니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 인수를 값으로 전달해야 하는 경우와 참조로 전달해야 하는 경우를 보여 줍니다.  `Calculate` 프로시저에는 `ByVal` 매개 변수와 `ByRef` 매개 변수가 모두 있습니다.  이율인 `rate`와 금액 합계인 `debt`가 지정되면 프로시저는 `debt`의 원래 값에 이율을 적용한 결과인 `debt`의 새 값을 계산합니다.  `debt`가 `ByRef` 매개 변수이므로 새 합계는 `debt`에 해당하는 호출 코드의 인수 값에 반영됩니다.  `rate` 매개 변수는 `Calculate`에서 해당 값을 변경하지 않아야 하므로 `ByVal` 매개 변수입니다.  
  
### 코드  
 [!code-vb[VbVbcnProcedures#74](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-val_1.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)