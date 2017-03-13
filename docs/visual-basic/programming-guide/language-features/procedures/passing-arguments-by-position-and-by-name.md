---
title: "Passing Arguments by Position and by Name (Visual Basic) | Microsoft Docs"
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
  - "arguments [Visual Basic], passing by name"
  - "procedures, arguments"
  - ":= passing arguments"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "named arguments, passing arguments"
  - "arguments [Visual Basic], passing by position"
  - "Function procedures, passing arguments"
  - "named parameters, passing arguments"
  - "named arguments"
  - "passing parameters, named parameter arguments"
  - "passing parameters, by position"
  - "procedures, calling"
  - "named parameters"
  - "Sub procedures, passing arguments"
  - "argument passing"
  - "passing parameters, by name"
  - "argument passing, by position"
  - "arguments [Visual Basic], listing by name"
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Passing Arguments by Position and by Name (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Sub` 프로시저나 `Function` 프로시저를 호출할 때 인수를 *위치로*\(프로시저의 정의에 나타난 순서\)로 전달하거나 위치에 관계없이 *이름으로* 전달할 수 있습니다.  
  
 이름으로 인수를 전달하는 경우에는 인수의 선언된 이름 뒤에 콜론과 등호\(`:=`\)가 오고 그 뒤에 인수 값이 오도록 지정합니다.  명명된 인수는 순서에 관계 없이 제공할 수 있습니다.  
  
 예를 들어, 다음 `Sub` 프로시저는 세 개의 인수를 받습니다.  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 이 프로시저를 호출할 경우 위치나 이름으로, 또는 둘을 혼합 사용하여 인수를 제공할 수 있습니다.  
  
## 위치로 인수 전달  
 다음 예제에서처럼 쉼표로 구분한 위치로 인수를 전달하여 `studentInfo` 프로시저를 호출할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 위치 인수 목록에서 선택적 인수를 생략하는 경우 쉼표를 사용하여 그 위치를 남겨두어야 합니다.  다음 예제에서는 `age` 인수 없이`studentInfo`를 호출합니다.  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## 이름으로 인수 전달  
 또한 다음 예제에서처럼 쉼표로 구분한 이름으로 인수를 전달하여 `studentInfo`  프로시저를 호출할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## 위치 및 이름을 함께 사용하여 인수 전달  
 다음 예제에서처럼, 하나의 프로시저 호출에서 위치와 이름을 모두 사용하여 인수를 제공할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 위 예제에서는 `birth`가 이름으로 전달되므로 생략된 `age` 인수의 위치를 쉼표로 남겨두지 않아도 됩니다.  
  
 위치와 이름을 모두 사용하여 인수를 제공하는 경우 항상 위치 인수가 앞에 와야 합니다.  이름으로 인수를 제공하면 남은 인수도 모두 이름으로 제공해야 합니다.  
  
## 이름으로 선택적 인수 제공  
 이름으로 인수를 전달하는 방식은 선택적 인수가 둘 이상인 프로시저를 호출하는 경우에 특히 유용합니다.  이름으로 인수를 제공하면 연속적으로 쉼표를 사용하여 생략된 위치 인수를 표시할 필요가 없기 때문입니다.  또한, 전달할 인수와 생략할 인수를 더 쉽게 구분할 수 있습니다.  
  
## 이름으로 인수를 제공하는 경우 제한 사항  
 인수를 이름으로 전달하더라도 필수적 인수는 반드시 입력해야 하며  선택적 인수만 생략할 수 있습니다.  
  
 매개 변수 배열은 이름으로 전달할 수 없습니다.  배열을 이름으로 전달하면 프로시저를 호출할 때 매개 변수 배열에 대한 인수를 쉼표로 구분하여 끝없이 나열해야 하고, 컴파일러에서 여러 인수를 하나의 이름과 연결하지 못하기 때문입니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)