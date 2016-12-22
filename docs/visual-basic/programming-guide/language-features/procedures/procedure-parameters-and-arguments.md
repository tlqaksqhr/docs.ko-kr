---
title: "Procedure Parameters and Arguments (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, arguments"
  - "procedures, argument lists"
  - "values, passing to procedures"
  - "arguments [Visual Basic], passing"
  - "procedures, parameters"
  - "Visual Basic code, argument lists"
  - "Visual Basic code, procedures"
  - "parameters, Visual Basic procedures"
  - "parameters, lists"
  - "arguments [Visual Basic], Visual Basic procedures"
  - "arguments [Visual Basic], procedures"
  - "parameter lists"
  - "Visual Basic code, parameter lists"
  - "argument lists"
  - "procedures, parameter lists"
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedure Parameters and Arguments (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

대부분의 경우 프로시저에는 프로시저를 호출한 환경에 대한 정보가 제공되어야 합니다.  반복적인 작업이나 공유 작업을 수행하는 프로시저는 각 호출에 대해 서로 다른 정보를 사용합니다.  이 정보는 프로시저가 호출될 때 프로시저로 전달되는 변수, 상수 및 식으로 구성됩니다.  
  
 *매개 변수*는 프로시저를 호출할 때 프로시저에 제공해야 하는 값입니다.  프로시저의 선언에 해당 매개 변수가 정의됩니다.  
  
 매개 변수 없이 또는 하나 또는 그 이상의 매개 변수를 사용하여 프로시저를 정의할 수 있습니다.  프로시저에서 매개 변수가 정의되는 부분을 *매개 변수 목록*이라고 합니다.  
  
 *인수*는 프로시저를 호출할 때 프로시저 매개 변수에 제공하는 값입니다.  호출 코드는 프로시저를 호출할 때 인수를 제공합니다.  프로시저 호출에서 인수가 지정되는 부분을 *인수 목록*이라고 합니다.  
  
 다음은 서로 다른 두 위치에서 `safeSquareRoot` 프로시저를 호출하는 코드에 대한 설명입니다.  첫 번째 호출에서는 `x` 변수 값\(4.0\)을 `number` 매개 변수에 전달하고 `root`의 반환 값\(2.0\)을 `y` 변수에 할당합니다.  두 번째 호출에서는 리터럴 값 9.0을 `number`에 전달하고 반환 값\(3.0\)을 `z` 변수에 할당합니다.  
  
 ![매개 변수에 인수를 전달하는 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/procedures/media/parametersargue.gif "ParametersArgue")  
매개 변수에 인수 전달  
  
 자세한 내용은 [Differences Between Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)을 참조하십시오.  
  
## 매개 변수 데이터 형식  
 매개 변수 선언에서 `As` 절을 사용하여 해당 데이터 형식을 정의합니다.  예를 들어, 다음 함수에서는 문자열과 정수를 받아들입니다.  
  
 [!code-vb[VbVbcnProcedures#32](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 `Off`이면 `As` 절을 생략할 수 있습니다. 단, 매개 변수 중 어느 하나라도 이 절을 사용하면 모든 매개 변수에서 이 절을 사용해야 합니다.  형식 검사가 `On`이면 모든 프로시저 매개 변수에 `As` 절을 사용해야 합니다.  
  
 호출 코드에서 해당 매개 변수의 형식과 다른 형식의 인수를 지정해야 하는 경우\(예: `String` 매개 변수에 `Byte` 지정\)에는 다음 중 하나를 수행해야 합니다.  
  
-   매개 변수 데이터 형식으로 확대 변환되는 데이터 형식의 인수만 지정합니다.  
  
-   암시적 축소 변환이 가능하도록 `Option Strict Off`를 설정합니다.  
  
-   변환 키워드를 사용하여 데이터 형식을 명시적으로 변환합니다.  
  
### 형식 매개 변수  
 *제네릭 프로시저*도 일반 매개 변수 외에 하나 이상의 *형식 매개 변수*를 정의합니다.  제네릭 프로시저를 사용하면 호출 코드에서 프로시저를 호출할 때마다 다른 데이터 형식을 전달할 수 있으므로 각 개별 호출의 요구 사항에 맞게 데이터 형식을 조정할 수 있습니다.  [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)를 참조하십시오.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Parameter for a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)