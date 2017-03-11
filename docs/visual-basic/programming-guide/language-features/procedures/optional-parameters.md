---
title: "Optional Parameters (Visual Basic) | Microsoft Docs"
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
  - "parameters, optional"
  - "Visual Basic code, procedures"
  - "procedures, optional arguments"
  - "optional arguments"
  - "named arguments, and optional arguments"
  - "optional parameters"
  - "Optional keyword, optional arguments"
  - "arguments [Visual Basic], optional"
  - "optional arguments, and named arguments"
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Optional Parameters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저 매개 변수를 선택적 요소로 지정하여 프로시저를 호출할 때 인수를 지정하지 않아도 되도록 할 수 있습니다.  *선택적 매개 변수*는 프로시저 선언에서 `Optional` 키워드로 표시됩니다.  이 때 적용되는 규칙은 다음과 같습니다.  
  
-   프로시저 정의의 모든 선택적 매개 변수에는 기본값을 지정해야 합니다.  
  
-   선택적 매개 변수의 기본값은 상수 식이어야 합니다.  
  
-   프로시저 정의에서 선택적 매개 변수 뒤에 오는 매개 변수도 모두 선택적 요소여야 합니다.  
  
 다음 구문은 선택적 매개 변수를 사용하여 프로시저를 선언하는 방법을 보여 줍니다.  
  
```  
Sub sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## 선택적 매개 변수가 있는 프로시저 호출  
 선택적 매개 변수가 있는 프로시저를 호출하는 경우 해당 인수를 지정할지 여부를 선택할 수 있습니다.  선택하지 않으면 선택적 매개 변수에 대해 선언된 기본값이 사용됩니다.  
  
 인수 목록에서 하나 이상의 선택적 인수를 생략하는 경우 그 자리에 쉼표를 사용하여 생략된 위치를 표시합니다.  다음 호출 샘플에서는 첫 번째와 네 번째 인수가 제공되고 두 번째와 세 번째 인수는 제공되지 않습니다.  
  
```  
  
sub name(argument 1, , , argument 4)  
```  
  
 다음 예제에서는 `MsgBox` 함수를 여러 번 호출합니다.  `MsgBox`에는 필수적 매개 변수 하나와 선택적 매개 변수 두 개가 사용됩니다.  
  
 `MsgBox`에 대한 첫 번째 호출에서 `MsgBox`에서 정의하는 순서대로 세 개의 인수를 모두 제공합니다.  두 번째 호출에서는 필수적 인수만 지정합니다.  세 번째와 네 번째 호출에서는 첫 번째 인수와 세 번째 인수를 지정합니다.  세 번째 호출에서는 위치로 인수를 지정하고, 네 번째 호출에서는 이름으로 인수를 지정합니다.  
  
 [!code-vb[VbVbcnProcedures#47](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/optional-parameters_1.vb)]  
  
## 선택적 인수의 존재 여부 확인  
 프로시저는 지정된 인수가 생략되었는지 또는 호출 코드가 명시적으로 기본값을 제공했는지 여부를 런타임에서 감지할 수 없습니다.  이를 알아보려면 특이한 값을 기본값으로 설정하면 됩니다.  다음 예제에서는 선택적 매개 변수 `office`를 정의하고 기본값  `QJZ`를 테스트하여 호출에서 해당 매개 변수가 생략되었는지 확인합니다.  
  
 [!code-vb[VbVbcnProcedures#46](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/optional-parameters_2.vb)]  
  
 선택적 매개 변수가 `String`과 같은 참조 형식일 경우 `Nothing`이 그 인수에 예상된 값이 아니면 이 값을 기본값으로 사용할 수 있습니다.  
  
## 선택적 매개 변수 및 오버로드  
 선택적 매개 변수가 있는 프로시저를 정의하는 또 다른 방법은 오버로드를 사용하는 것입니다.  선택적 매개 변수가 하나이면 프로시저의 오버로드된 두 버전을 매개 변수를 사용하는 버전과 매개 변수를 사용하지 않는 버전으로 정의할 수 있습니다.  이러한 방식은 선택적 매개 변수의 개수가 증가할수록 더욱 복잡해지지만  호출 프로그램이 각 선택적 인수를 제공했는지 여부를 확실히 알 수 있다는 장점이 있습니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)