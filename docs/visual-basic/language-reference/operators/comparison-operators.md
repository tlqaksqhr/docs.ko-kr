---
title: "Comparison Operators (Visual Basic) | Microsoft Docs"
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
  - "vb.<>"
  - "vb.>="
  - "vb.<="
  - "vb.>"
  - "vb.<"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "greater than or equal to operator [Visual Basic]"
  - ">= operator [Visual Basic]"
  - "= operator [Visual Basic]"
  - "< operator [Visual Basic]"
  - "less than operator [Visual Basic]"
  - "relational operators, syntax"
  - "Like operator [Visual Basic]"
  - "<> operator [Visual Basic]"
  - "> operator [Visual Basic]"
  - "equal operator [Visual Basic]"
  - "less than or equal to operator [Visual Basic]"
  - "symbols, operators"
  - "greater than operator [Visual Basic]"
  - "comparing values [Visual Basic]"
  - "operators [Visual Basic], relational"
  - "string comparison [Visual Basic]"
  - "not equal to comparison operator [Visual Basic]"
  - "<= operator [Visual Basic]"
  - "operators [Visual Basic], comparison"
  - "Is operator [Visual Basic]"
  - "comparison operators, Visual Basicl"
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Comparison Operators (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음은 Visual Basic에 정의된 비교 연산자입니다.  
  
 `<` 연산자  
  
 `<=` 연산자  
  
 `>` 연산자  
  
 `>=` 연산자  
  
 `=` 연산자  
  
 `<>` 연산자  
  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 이러한 연산자는 두 개의 식을 비교하여 서로 같은지 확인하고 같지 않을 경우 차이가 얼마나 나는지 확인합니다.  `Is`, `IsNot` 및 `Like`에 대해서는 별도의 도움말 페이지에서 자세하게 설명합니다.  이 페이지에서는 관계 비교 연산자에 대해 자세하게 설명합니다.  
  
## 구문  
  
```  
  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## 요소  
 `result`  
 필수 요소.  비교 결과를 나타내는 `Boolean` 값입니다.  
  
 `expression`  
 필수 요소.  임의의 식입니다.  
  
 `comparisonoperator`  
 필수 요소.  임의의 관계 비교 연산자입니다.  
  
 `object1`, `object2`  
 필수 요소.  임의의 참조 개체 이름입니다.  
  
 `string`  
 필수 요소.  `String` 식입니다.  
  
 `pattern`  
 필수 요소.  임의의 `String` 식 또는 문자의 범위입니다.  
  
## 설명  
 다음 표에서는 `result`가 `True` 또는 `False`인지를 결정하는 관계 비교 연산자 및 조건을 보여 줍니다.  
  
|Operator|결과가 `True`인 조건|결과가 `False`인 조건|  
|--------------|--------------------|---------------------|  
|`<`\(보다 작음\)|`expression1` \< `expression2`|`expression1` \>\= `expression2`|  
|`<=`\(작거나 같음\)|`expression1` \<\= `expression2`|`expression1` \> `expression2`인 경우|  
|`>`\(보다 큼\)|`expression1` \> `expression2`인 경우|`expression1` \<\= `expression2`|  
|`>=`\(크거나 같음\)|`expression1` \>\= `expression2`|`expression1` \< `expression2`|  
|`=`\(같음\)|`expression1` \= `expression2`|`expression1` \<\> `expression2`|  
|`<>`\(같지 않음\)|`expression1` \<\> `expression2`|`expression1` \= `expression2`|  
  
> [!NOTE]
>  [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)는 할당 연산자로도 사용할 수 있습니다.  
  
 `Is`, `IsNot` 및 `Like` 연산자에는 위의 표에 있는 연산자와는 다른 특별한 비교 기능이 있습니다.  
  
## 숫자 비교  
 `Single` 형식의 식이 `Double` 형식의 식과 비교되면 `Single` 식이 `Double`로 변환됩니다.  이 동작은 Visual Basic 6에서 수행되는 동작과 반대입니다.  
  
 마찬가지로 `Decimal` 형식의 식이 `Single` 또는 `Double` 형식의 식과 비교되면 `Decimal` 식이 `Single` 또는 `Double`로 변환됩니다.  `Decimal` 식의 경우 1E\-28보다 작은 소수 값은 손실됩니다.  소수 값이 손실되면 두 값이 서로 다르더라도 같은 값으로 비교될 수 있습니다.  따라서 두 개의 부동 소수점 변수를 비교하는 경우 주의하여 상등 연산자\(`=`\)를 사용해야 합니다.  두 숫자의 차에 대한 절대 값이 허용 오차보다 작은지 테스트하는 것이 더 안전합니다.  
  
### 부동 소수점 부정확성  
 부동 소수점 숫자로 작업할 때에는 메모리에 정밀한 표현이 항상 제공되지는 않는다는 것을 염두에 두고 있어야 합니다.  따라서 값 비교, [Mod 연산자](../../../visual-basic/language-reference/operators/mod-operator.md)와 같은 특정 연산에서 예기치 않은 결과가 나타날 수 있습니다.  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)를 참조하십시오.  
  
## 문자열 비교  
 문자열을 비교하는 경우 문자열 식은 사전순으로 계산되며 이 순서는 `Option Compare` 설정에 따라 달라집니다.  
  
 `Option Compare Binary`는 문자의 내부 이진 표현에서 파생된 정렬 순서에 따라 문자열을 비교합니다.  정렬 순서는 코드 페이지에 의해 결정됩니다.  다음 예제에서는 일반적인 이진 정렬 순서를 보여 줍니다.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text`는 응용 프로그램의 로캘에서 결정된 대\/소문자를 구분하지 않는 텍스트 정렬 순서에 따라 문자열을 비교합니다.  위의 예제에서 `Option Compare Text`를 설정하고 문자를 정렬하면 다음 텍스트 정렬 순서가 적용됩니다.  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### 로캘 종속성  
 `Option Compare Text`를 설정하면 문자열 비교 결과는 응용 프로그램이 실행되고 있는 로캘에 따라 달라집니다.  한 로캘에서는 두 문자가 동일한 것으로 비교되지만 다른 로캘에서는 그렇지 않습니다.  문자열 비교를 사용하여 중요한 결정\(예: 로그온 시도를 허용할지 여부\)을 내리는 경우 로캘 구분에 주의해야 합니다.  `Option Compare Binary`를 설정하거나 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>를 호출하여 로캘을 살펴볼 수 있습니다.  
  
## 관계 비교 연산자는 있지만 관대한 형식의 프로그래밍  
 `Option Strict On`인 경우 `Object` 식에 관계 비교 연산자를 사용할 수 없습니다.  `Option Strict`가 `Off`이고 `expression1` 또는 `expression2`가 `Object` 식이면 런타임 형식에 따라 비교 방법이 결정됩니다.  다음 표에서는 피연산자의 런타임 형식에 따라 식이 비교되는 방식과 비교 결과를 보여 줍니다.  
  
|피연산자|비교 방법|  
|----------|-----------|  
|둘 다 `String`인 경우|문자열 정렬 특성에 따라 비교를 정렬합니다.|  
|둘 다 숫자인 경우|개체가 `Double`로 변환되고 숫자가 비교됩니다.|  
|하나는 숫자이고 다른 하나는 `String`인 경우|`String`이 `Double`로 변환되고 숫자가 비교됩니다.  `String`을 `Double`로 변환할 수 없으면 <xref:System.InvalidCastException>이 throw됩니다.|  
|하나 또는 둘 모두가 `String`이 아닌 다른 참조 형식인 경우|<xref:System.InvalidCastException>이 throw됩니다.|  
  
 숫자 비교는 `Nothing`을 0으로 간주합니다.  문자열 비교는 `Nothing`을 `""`\(빈 문자열\)로 취급합니다.  
  
## 오버로딩  
 관계형 비교 연산자\(`<`,  `<=`, `>`, `>=`, `=`, `<>`\)는 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체의 형식인 경우 해당 클래스나 구조체에서 해당 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
 [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)는 할당 연산자가 아니라 관계 비교 연산자로만 오버로드할 수 있다는 점에 주의합니다.  
  
## 예제  
 다음 예제에서는 관계 비교 연산자를 사용하여 식을 비교하는 여러 가지 방법을 보여 줍니다.  관계 비교 연산자는 식이 `True`인지 여부를 나타내는 `Boolean` 결과를 반환합니다.  `>` 및 `<` 연산자를 문자열에 적용하면 해당 문자열이 표준 사전순으로 비교됩니다.  이 순서는 로캘 설정에 따라 달라질 수 있습니다.  정렬 순서의 대\/소문자 구분 여부는[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)설정에 따라 결정됩니다.  
  
 [!CODE [VbVbalrOperators#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#1)]  
  
 위 예제에서 첫 번째 비교는 `False`를 반환하고 나머지 비교는 `True`를 반환합니다.  
  
## 참고 항목  
 <xref:System.InvalidCastException>   
 [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)