---
title: "How to: Pass Arguments to a Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "arguments [Visual Basic], passing to procedures"
  - "procedures, arguments"
  - "procedures, parameters"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, calling"
  - "argument passing, procedures"
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Pass Arguments to a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

프로시저를 호출할 때 프로시저 이름과 괄호로 묶은 인수 목록을 차례로 사용합니다.  프로시저에 정의된 모든 필수 매개 변수에 해당하는 인수를 제공하고 `Optional` 매개 변수에 대한 인수를 선택적으로 제공할 수 있습니다.  호출에 `Optional` 매개 변수를 제공하지 않을 경우 후속 인수를 사용하려면 쉼표를 사용하여 인수 목록에서 해당 위치를 표시해야 합니다.  
  
 `Byte`와 같이 해당 매개 변수와 데이터 형식이 다른 인수를 `String`에 전달하려면 형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)를 `Off`로 설정할 수 있습니다.  `Option Strict`가 `On`인 경우 확대 변환 또는 명시적 변환 키워드를 사용해야 합니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조하십시오.  
  
 자세한 내용은 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)를 참조하십시오.  
  
### 하나 이상의 인수를 프로시저에 전달하려면  
  
1.  호출 문에서 프로시저 이름과 괄호를 차례로 사용합니다.  
  
2.  괄호 안에 인수 목록을 넣습니다.  프로시저에 정의된 각 필수 매개 변수에 대한 인수를 포함하고 각 인수를 쉼표로 구분합니다.  
  
3.  각 인수가 해당 매개 변수에 대해 프로시저에 정의된 형식으로 변환 가능한 데이터 형식을 계산하는 유효한 식인지 확인합니다.  
  
4.  매개 변수가 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)로 정의되어 있는 경우 해당 매개 변수를 인수 목록에 포함하거나 생략할 수 있습니다.  매개 변수를 생략하면 프로시저는 해당 매개 변수에 대해 정의된 기본값을 사용합니다.  
  
5.  `Optional` 매개 변수에 대한 인수를 생략하고 매개 변수 목록의 해당 매개 변수 뒤에 다른 매개 변수가 있는 경우 인수 목록에 쉼표를 추가로 입력하여 생략된 인수의 위치를 표시할 수 있습니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수를 호출합니다.  
  
     [!code-vb[VbVbcnProcedures#34](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     이전 예제에서는 표시할 메시지 문자열인 첫 번째 필수 인수를 제공합니다.  메시지 상자에 표시할 단추를 지정하는 두 번째 매개 변수\(선택적 요소\)에 대한 인수를 생략합니다.  호출에서 값을 제공하지 않기 때문에 `MsgBox`는 기본값 `MsgBoxStyle.OKOnly`를 사용합니다. 이 경우 **확인** 단추만 표시됩니다.  
  
     인수 목록의 두 번째 쉼표는 생략된 두 번째 인수의 위치를 나타내고 마지막 문자열은 제목 표시줄에 표시될 텍스트이며 `MsgBox`의 세 번째 매개 변수\(선택적 요소\)에 전달됩니다.  
  
## 참고 항목  
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Parameter for a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [개체 지향 프로그래밍](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)