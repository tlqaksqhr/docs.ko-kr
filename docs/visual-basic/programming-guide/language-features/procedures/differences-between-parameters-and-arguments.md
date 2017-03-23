---
title: "Differences Between Parameters and Arguments (Visual Basic) | Microsoft Docs"
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
  - "procedures, arguments"
  - "procedures, parameters"
  - "parameters, and arguments"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], and parameters"
  - "procedure parameters"
  - "parameters, definition"
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Differences Between Parameters and Arguments (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

대부분의 경우 프로시저에는 프로시저를 호출한 환경에 대한 정보가 제공되어야 합니다.  반복적인 작업이나 공유 작업을 수행하는 프로시저는 각 호출에 대해 서로 다른 정보를 사용합니다.  이 정보는 프로시저가 호출될 때 프로시저로 전달되는 변수, 상수 및 식으로 구성됩니다.  
  
 이 정보를 프로시저에 전달하기 위해 프로시저는 *매개 변수*를 정의하고 호출 코드는 해당 매개 변수에 *인수*를 전달합니다.  매개 변수를 주차장이라고 한다면 인수는 자동차라고 할 수 있습니다.  여러 종류의 자동차가 다양한 시점에 주차장에 주차될 수 있는 것처럼 호출 코드는 프로시저를 호출할 때마다 다른 인수를 동일한 매개 변수에 전달할 수 있습니다.  
  
## 매개 변수  
 *매개 변수*는 프로시저를 호출할 때 프로시저에 전달해야 하는 값입니다.  프로시저의 선언에 해당 매개 변수가 정의됩니다.  
  
 `Function` 또는 `Sub` 프로시저를 정의할 때는 프로시저 이름 바로 다음에 *매개 변수 목록*을 괄호로 묶어 지정합니다.  각 매개 변수에는 이름, 데이터 형식, 전달 메커니즘\([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\)을 지정합니다.  매개 변수가 선택적임을 지정할 수도 있습니다.  이 경우는 호출 코드가 해당 매개 변수 값을 전달할 필요가 없음을 의미합니다.  
  
 각 매개 변수의 이름은 프로시저에서 *지역 변수*로 사용됩니다.  다른 변수를 사용할 때와 같은 방법으로 매개 변수 이름을 사용합니다.  
  
## 인수  
 *인수*는 프로시저를 호출할 때 프로시저 매개 변수에 전달하는 값입니다.  호출 코드는 프로시저를 호출할 때 인수를 제공합니다.  
  
 `Function` 또는 `Sub` 프로시저를 호출할 때는 프로시저 이름 바로 다음에 *인수 목록*을 괄호로 묶어 지정합니다.  인수는 목록에서 같은 위치에 있는 매개 변수에 각각 해당합니다.  
  
 매개 변수 정의와 달리 인수에는 이름이 없습니다.  모든 인수는 0개 이상의 변수, 상수 및 리터럴을 포함할 수 있는 식입니다.  계산된 식의 데이터 형식은 일반적으로 해당 매개 변수에 대해 정의된 데이터 형식과 일치해야 하며, 어떤 경우이든 매개 변수 형식으로 변환될 수 있어야 합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Parameter for a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)