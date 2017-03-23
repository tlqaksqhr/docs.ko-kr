---
title: "Parameter Arrays (Visual Basic) | Microsoft Docs"
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
  - "parameter arrays, about parameter arrays"
  - "ParamArray keyword, parameter arrays"
  - "Visual Basic code, procedures"
  - "parameters, parameter arrays"
  - "arguments [Visual Basic], parameter arrays"
  - "procedures, indefinite number of argument values"
  - "arrays [Visual Basic], parameter arrays"
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Parameter Arrays (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

일반적으로 프로시저 선언에 지정된 것보다 많은 인수를 가진 프로시저를 호출할 수 없습니다.  인수가 무한대로 필요한 경우에는 *매개 변수 배열*을 선언하여 프로시저가 매개 변수에 대한 값 배열을 받아들이도록 할 수 있습니다.  프로시저를 정의할 때 매개 변수 배열의 요소 수는 몰라도 됩니다.  배열의 크기는 프로시저에 대한 각 호출에 의해 개별적으로 결정됩니다.  
  
## ParamArray 선언  
 매개 변수 배열을 매개 변수 목록으로 나타내려면 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 키워드를 사용합니다.  이때 적용되는 규칙은 다음과 같습니다.  
  
-   프로시저에서 매개 변수 배열을 하나만 정의할 수 있으며 프로시저 정의의 마지막 매개 변수로 정의해야 합니다.  
  
-   매개 변수 배열은 값으로 전달되어야 합니다.  프로시저 정의에 명시적으로 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 키워드를 사용하는 것이 바람직한 프로그래밍 습관입니다.  
  
-   매개 변수 배열은 자동으로 선택적 인수로 지정되며  기본값은 매개 변수 배열 요소 형식의 빈 1차원 배열입니다.  
  
-   매개 변수 배열 앞에 오는 모든 매개 변수는 필수적 요소여야 하며  매개 변수 배열만 선택적 매개 변수여야 합니다.  
  
## ParamArray 호출  
 매개 변수 배열을 정의하는 프로시저를 호출할 때는 다음 중 한 가지 방법으로 인수를 지정할 수 있습니다.  
  
-   없음 즉, [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 인수를 생략할 수 있습니다.  이 경우에는 빈 배열이 프로시저로 전달됩니다.  [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 전달할 수도 있는데, 그 결과는 동일합니다.  
  
-   쉼표로 구분된 임의 개수의 인수 목록.  각 인수의 데이터 형식은 암시적으로 `ParamArray` 요소 형식으로 변환할 수 있어야 합니다.  
  
-   매개 변수 배열의 요소 형식과 동일한 요소 형식의 배열  
  
 모든 경우, 프로시저 내의 코드에서는 매개 변수 배열을 요소의 데이터 형식이 `ParamArray` 데이터 형식과 동일한 1차원 배열로 처리됩니다.  
  
> [!IMPORTANT]
>  무제한으로 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량에 오버런이 발생할 위험이 있습니다.  매개 변수 배열을 받는 경우 호출 코드에서 받은 배열의 크기를 테스트해야 합니다.  이때 크기가 너무 커서 해당 배열을 응용 프로그램에 사용할 수 없을 경우에는 적절한 조치를 취합니다.  자세한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 정의 하 고이 함수를 호출 `calcSum`.  `ParamArray` 매개 변수에 대 한 한정자 `args` 함수가 가변 개수의 인수를 받아들일 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 다음 예제에서는 매개 변수 배열이 있는 프로시저를 정의하고 매개 변수 배열에 전달되는 모든 배열 요소의 값을 출력합니다.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)