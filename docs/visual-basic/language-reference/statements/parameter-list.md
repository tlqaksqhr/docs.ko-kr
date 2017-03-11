---
title: "Parameter List (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "parameters, Visual Basic"
  - "parameters, lists"
  - "parameter lists"
  - "Visual Basic code, parameter lists"
  - "arguments [Visual Basic], Visual Basic"
  - "procedures, parameter lists"
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Parameter List (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저를 호출할 때 프로시저에 필요한 매개 변수를 지정합니다.  매개 변수가 여러 개 있으면 쉼표로 구분됩니다.  다음은 단일 매개 변수 구문입니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## 요소  
 `attributelist`  
 선택적 요소.  이 매개 변수에 적용되는 특성의 목록입니다.  [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md)은 꺾쇠괄호\("`<`" 및 "`>`"\)로 묶어야 합니다.  
  
 `Optional`  
 선택적 요소.  프로시저를 호출할 때 이 매개 변수가 필수적 요소가 아님을 지정합니다.  
  
 `ByVal`  
 선택적 요소.  호출 코드의 내부 인수로 사용하는 변수 요소를 바꾸거나 다시 할당할 수 없도록 지정합니다.  
  
 `ByRef`  
 선택적 요소.  프로시저에서 호출 코드 자체에서 수행되는 방식으로 호출 코드의 내부 변수 요소를 수정할 수 있도록 지정합니다.  
  
 `ParamArray`  
 선택적 요소.  매개 변수 목록의 마지막 매개 변수가 지정된 데이터 형식의 선택적 요소 배열임을 지정합니다.  호출 코드에서 이를 사용하면 프로시저에 임의의 여러 인수를 전달할 수 있습니다.  
  
 `parametername`  
 필수 요소.  인수를 나타내는 로컬 변수의 이름입니다.  
  
 `parametertype`  
 `Option Strict`가 `On`이면 필수적 요소입니다.  인수를 나타내는 로컬 변수의 데이터 형식입니다.  
  
 `defaultvalue`  
 `Optional` 매개 변수에 필수적인 요소입니다.  해당 매개 변수의 데이터 형식으로 계산되는 임의의 상수 또는 상수 식입니다.  형식이 `Object`이거나 클래스, 인터페이스, 배열 또는 구조체인 경우 기본값은 `Nothing`만 될 수 있습니다.  
  
## 설명  
 매개 변수를 괄호로 묶어 쉼표로 구분합니다.  매개 변수는 원하는 데이터 형식으로 선언할 수 있습니다.  `parametertype`을 지정하지 않은 경우 기본값으로 `Object`가 사용됩니다.  
  
 호출 코드는 프로시저를 호출하는 경우 필요한 각 매개 변수에 *인수*를 전달합니다.  자세한 내용은 [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)을 참조하십시오.  
  
 호출 코드가 각 매개 변수에 전달하는 인수는 호출 코드의 내부 요소에 대한 포인터입니다.  *비가변* 요소\(상수, 리터럴, 열거형, 식 등\)는 코드에서 변경할 수 없지만  *가변* 요소\(선언된 변수, 필드, 속성, 배열 요소, 구조체 요소 등\)는 호출 코드에서 변경할 수 있습니다.  자세한 내용은 [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)를 참조하십시오.  
  
 가변 요소가 `ByRef`로 전달되는 경우 프로시저에서 해당 요소를 변경할 수도 있습니다.  자세한 내용은 [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조하십시오.  
  
## 규칙  
  
-   **괄호.** 매개 변수 목록을 지정하는 경우 괄호로 묶어야 합니다.  매개 변수가 없는 경우에도 괄호를 사용하여 빈 목록을 묶을 수 있습니다.  이렇게 하면 해당 요소가 프로시저임이 명확해지므로 코드를 보다 쉽게 읽을 수 있습니다.  
  
-   **선택적 매개 변수.** 매개 변수에 `Optional` 한정자를 사용하는 경우 목록의 모든 후속 매개 변수도 선택적 요소여야 하며 `Optional` 한정자를 사용하여 선언되어야 합니다.  
  
     모든 선택적 매개 변수 선언에는 `defaultvalue` 절을 사용해야 합니다.  
  
     자세한 내용은 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)를 참조하십시오.  
  
-   **매개 변수 배열.** `ByVal`을 `ParamArray` 매개 변수에 지정해야 합니다.  
  
     한 매개 변수 목록에 `Optional`와 `ParamArray`를 모두 사용할 수는 없습니다.  
  
     자세한 내용은 [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)을 참조하십시오.  
  
-   **전달 메커니즘.** 모든 인수의 기본 메커니즘은 `ByVal`이므로 프로시저가 내부 변수 요소를 변경할 수 없습니다.  요소가 참조 형식인 경우 프로시저가 내부 개체 자체를 바꾸거나 다시 할당할 수 없지만 내부 개체의 내용이나 멤버는 수정할 수 있습니다.  
  
-   **매개 변수 이름.** 매개 변수의 데이터 형식이 배열인 경우 `parametername` 바로 뒤에 괄호가 표시됩니다.  매개 변수 이름에 대한 자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 두 매개 변수를 정의하는 `Function` 프로시저를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/parameter-list_1.vb)]  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)