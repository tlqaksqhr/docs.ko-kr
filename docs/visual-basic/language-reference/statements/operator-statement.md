---
title: "Operator Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.operator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operators [Visual Basic]"
  - "procedures, operator"
  - "Narrowing keyword, conversion operators"
  - "Visual Basic code, operators"
  - "Widening keyword, conversion operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "overloaded operators"
  - "operator overloading"
  - "operator procedures"
  - "Operator statement"
  - "CType function, Operator statement"
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operator Statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

클래스 또는 구조체의 연산자 프로시저를 정의하는 연산자 기호, 피연산자 및 코드를 선언합니다.  
  
## 구문  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## 요소  
 `attrlist`  
 선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.  
  
 `Public`  
 필수 요소.  이 연산자 프로시저에 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스 권한이 있음을 나타냅니다.  
  
 `Overloads`  
 선택적 요소.  자세한 내용은 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)를 참조하십시오.  
  
 `Shared`  
 필수 요소.  이 연산자 프로시저가 [Shared](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저임을 나타냅니다.  
  
 `Shadows`  
 선택적 요소.  자세한 내용은 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.  
  
 `Widening`  
 `Narrowing`을 지정하지 않는 경우 변환 연산자에 필수적 요소입니다.  이 연산자 프로시저가 [Widening](../../../visual-basic/language-reference/modifiers/widening.md) 변환을 정의함을 나타냅니다.  이 도움말 페이지의 "확대 변환과 축소 변환"을 참조하십시오.  
  
 `Narrowing`  
 `Widening`을 지정하지 않는 경우 변환 연산자에 필수적 요소입니다.  이 연산자 프로시저가 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환을 정의함을 나타냅니다.  이 도움말 페이지의 "확대 변환과 축소 변환"을 참조하십시오.  
  
 `operatorsymbol`  
 필수 요소.  이 연산자 프로시저에서 정의하는 연산자의 기호 또는 식별자입니다.  
  
 `operand1`  
 필수 요소.  단항 연산자\(변환 연산자 포함\)의 단일 피연산자 또는 이항 연산자의 왼쪽 피연산자의 이름과 형식입니다.  
  
 `operand2`  
 이항 연산자에 필수적 요소입니다.  이항 연산자의 오른쪽 피연산자의 이름과 형식입니다.  
  
 `operand1` 및 `operand2`의 구문과 구성 요소는 다음과 같습니다.  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|파트|설명|  
|--------|--------|  
|`ByVal`|선택적 요소이지만 전달 메커니즘이 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)이어야 합니다.|  
|`operandname`|필수 요소.  이 피연산자를 나타내는 변수의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`operandtype`|`Option Strict`가 `On`이 아닌 경우 선택적 요소입니다.  이 피연산자의 데이터 형식입니다.|  
  
 `type`  
 `Option Strict`가 `On`이 아닌 경우 선택적 요소입니다.  연산자 프로시저에서 반환하는 값의 데이터 형식입니다.  
  
 `statements`  
 선택적 요소.  피연산자 프로시저에서 실행되는 문의 블록입니다.  
  
 `returnvalue`  
 필수 요소.  연산자 프로시저에서 호출 코드로 반환하는 값입니다.  
  
 `End` `Operator`  
 필수 요소.  이 연산자 프로시저의 정의를 끝냅니다.  
  
## 설명  
 클래스나 구조체에서만 `Operator`를 사용할 수 있습니다.  즉, 연산자의 *선언 컨텍스트*는 소스 파일, 네임스페이스, 모듈, 인터페이스, 프로시저 또는 블록일 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 모든 연산자는 `Public Shared`여야 합니다.  `ByRef`, `Optional` 또는 `ParamArray`를 피연산자로 지정할 수 없습니다.  
  
 연산자 기호나 식별자를 사용하여 반환 값을 저장할 수 없습니다.  `Return` 문을 사용하여 값을 지정해야 합니다.  프로시저 내의 임의의 위치에 여러 개의 `Return` 문을 사용할 수 있습니다.  
  
 `Overloads` 키워드를 사용하는지 여부에 관계없이 이 방법으로 연산자를 정의하는 것을 *연산자 오버로드*라고 합니다.  다음 표에서는 정의할 수 있는 연산자를 보여 줍니다.  
  
|형식|연산자|  
|--------|---------|  
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|변환\(단항\)|`CType`|  
  
 이진 목록의 `=` 연산자는 할당 연산자가 아니라 비교 연산자입니다.  
  
 `CType`을 정의하는 경우 `Widening` 또는 `Narrowing`을 지정해야 합니다.  
  
## 일치하는 쌍  
 특정 연산자를 일치하는 쌍으로 정의해야 합니다.  이러한 일치하는 쌍 중 하나의 연산자를 정의하는 경우 다른 하나에 대한 연산자도 정의해야 합니다.  일치하는 쌍은 다음과 같습니다.  
  
-   `=` 및 `<>`  
  
-   `>` 및 `<`  
  
-   `>=` 및 `<=`  
  
-   `IsTrue` 및 `IsFalse`  
  
## 데이터 형식 제한  
 정의된 모든 연산자에는 연산자를 정의한 클래스나 구조체가 포함되어야 합니다.  즉, 클래스나 구조체가 다음과 같은 데이터 형식으로 표시되어야 합니다.  
  
-   단항 연산자의 피연산자  
  
-   이항 연산자의 하나 이상의 피연산자  
  
-   변환 연산자의 반환 형식 또는 피연산자  
  
 특정 연산자에 다음과 같은 추가 데이터 형식 제한이 있습니다.  
  
-   `IsTrue` 및 `IsFalse` 연산자를 정의하는 경우 두 연산자는 모두 `Boolean` 형식을 반환해야 합니다.  
  
-   `<<` 및 `>>` 연산자를 정의하는 경우 두 연산자는 모두 `operand2`의 `operandtype`으로 `Integer` 형식을 지정해야 합니다.  
  
 반환 형식은 피연산자의 형식과 일치하지 않아도 됩니다.  예를 들어, `=` 또는 `<>`과 같은 비교 연산자는 피연산자가 `Boolean`이 아니더라도 `Boolean`을 반환할 수 있습니다.  
  
## 논리 및 비트 연산자  
 `And`, `Or`, `Not` 및 `Xor` 연산자는 Visual Basic에서 논리 연산이나 비트 연산을 수행할 수 있습니다.  그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의하는 경우에는 비트 연산만 정의할 수 있습니다.  
  
 `AndAlso` 연산자는 `Operator` 문을 사용하여 직접 정의할 수 없습니다.  다음 조건을 충족하는 경우에는 `AndAlso`를 사용할 수 있습니다.  
  
-   `AndAlso`에 사용하려는 것과 동일한 피연산자 형식에 `And`를 정의했습니다.  
  
-   `And` 정의에서는 And를 정의한 클래스 또는 구조체와 동일한 형식을 반환합니다.  
  
-   `And`를 정의한 클래스 또는 구조체에 `IsFalse` 연산자를 정의했습니다.  
  
 마찬가지로 클래스나 구조체의 반환 형식을 사용하여 동일한 피연산자에 `Or`를 정의하고 클래스나 구조체에 `IsTrue`를 정의한 경우 `OrElse`를 사용할 수 있습니다.  
  
## 확대 변환과 축소 변환  
 *확대 변환*은 런타임에서 항상 성공하지만 *축소 변환*은 런타임에서 실패할 수 있습니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
 변환 프로시저를 `Widening`으로 선언하는 경우 프로시저 코드가 실패하지 않아야 합니다.  이것은 다음을 의미합니다.  
  
-   항상 올바른 `type` 형식 값을 반환해야 합니다.  
  
-   가능한 모든 예외와 기타 오류 조건을 처리해야 합니다.  
  
-   호출하는 프로시저의 모든 오류 반환을 처리해야 합니다.  
  
 변환 프로시저가 실패할 확률이 있거나 처리되지 않은 예외가 발생할 수 있는 경우에는 `Narrowing`으로 선언해야 합니다.  
  
## 예제  
 다음 코드 예제에서는 `Operator` 문을 사용하여 `And`, `Or`, `IsFalse` 및 `IsTrue` 연산자에 대한 연산자 프로시저를 포함하는 구조체를 개략적으로 정의합니다.  `And`와 `Or`는 형식이 `abc`이고 반환 형식이 `abc`인 두 개의 피연산자를 사용합니다.  `IsFalse`와 `IsTrue`는 형식이 `abc`이고 반환 형식이 `Boolean`인 단일 피연산자를 사용합니다.  이러한 정의를 사용하면 호출 코드에서 `And`, `AndAlso`, `Or` 및 `OrElse`를 `abc` 형식 피연산자와 함께 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## 참고 항목  
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../Topic/How%20to:%20Call%20an%20Operator%20Procedure%20\(Visual%20Basic\).md)   
 [How to: Use a Class that Defines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)