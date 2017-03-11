---
title: "Comparison Operators in Visual Basic | Microsoft Docs"
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
  - "comparison operators, comparing strings"
  - "comparison operators, comparing objects"
  - "strings [Visual Basic], comparing"
  - "comparison operators"
  - "string comparison [Visual Basic], operators"
  - "objects [Visual Basic], comparing"
  - "numbers, comparing"
  - "Visual Basic code, operators"
  - "string comparison [Visual Basic]"
  - "numeric values, comparing"
  - "comparison operators, comparing numeric values"
  - "operators [Visual Basic], comparison"
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Comparison Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

비교 연산자는 두 식을 비교하여 값의 관계를 나타내는 `Boolean` 값을 반환합니다.  숫자 값을 비교하는 연산자, 문자열을 비교하는 연산자, 개체를 비교하는 연산자가 있으며  여기에서 이러한 세 가지 연산자에 대해 모두 설명합니다.  
  
## 숫자 값 비교  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 여섯 가지 숫자 비교 연산자를 사용하여 숫자 값을 비교합니다.  각 연산자는 숫자 값으로 계산되는 두 식을 피연산자로 가집니다.  다음 표에서는 연산자를 나열하고 해당 예제를 보여 줍니다.  
  
|Operator|테스트 조건|예제|  
|--------------|------------|--------|  
|`=`\(같음\)|첫째 식의 값이 둘째 식의 값과 같습니까?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`\(같지 않음\)|첫째 식의 값이 둘째 식의 값과 같지 않습니까?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`\(보다 작음\)|첫째 식의 값이 둘째 식의 값보다 작습니까?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`\(보다 큼\)|첫째 식의 값이 둘째 식의 값보다 큽니까?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`\(작거나 같음\)|첫째 식의 값이 둘째 식의 값보다 작거나 같습니까?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`\(크거나 같음\)|첫째 식의 값이 둘째 식의 값보다 크거나 같습니까?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## 문자열 비교  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 숫자 비교 연산자와 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)를 사용하여 문자열을 비교합니다.  `Like` 연산자를 사용하여 패턴을 지정할 수 있습니다.  그런 다음 패턴에 대해 문자열을 비교하여 일치하면 `True`를 반환하고  그렇지 않으면, 결과는 `False`가 됩니다.  다음 예제와 같이 숫자 연산자를 사용하여 연산자 정렬 순서를 기반으로 `String` 값을 비교할 수 있습니다.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 첫째 문자열의 첫째 문자가 둘째 문자열의 첫째 문자보다 앞에 정렬되므로 이전 예제의 결과는 `True`입니다.  첫째 문자가 같으면 두 문자열에서 다음 문자를 비교하는 식으로 계속됩니다.  다음 예제와 같이 같음 연산자를 사용하여 문자열의 같음 여부를 테스트할 수도 있습니다.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 "aa"와 "aaa" 같이 한 문자열이 다른 문자열의 접두사인 경우 더 긴 문자열이 짧은 문자열보다 큰 것으로 간주됩니다.  다음은 이에 대한 예입니다.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 정렬 순서는 `Option Compare` 설정에 따라 이진 비교 또는 텍스트 비교를 기준으로 합니다.  자세한 내용은 [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md)을 참조하십시오.  
  
## 개체 비교  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) 및 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)를 사용하여 두 개체 참조 변수를 비교합니다.  이러한 연산자 중 하나를 사용하여 두 참조 변수가 동일한 개체 인스턴스를 참조하는지를 확인할 수 있습니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_1.vb)]  
  
 앞의 예제에서 두 변수가 모두 동일한 인스턴스를 참조하므로 `x Is y`는 `True`로 계산됩니다.  이 결과를 다음 예제와 대조해 보십시오.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_2.vb)]  
  
 앞의 예제에서 두 변수가 동일한 형식 개체를 참조하지만 서로 다른 형식의 인스턴스를 참조하기 때문에 `x Is y`는 `False`로 계산됩니다.  
  
 동일한 인스턴스를 가리키지 않는 두 개체에 대해 테스트하려면 `IsNot` 연산자를 사용하여 `Not`과 `Is`가 문법적으로 어색하게 조합되지 않게 합니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_3.vb)]  
  
 앞의 예제에서 `If a IsNot b`는 `If Not a Is b`와 동일합니다.  
  
### 개체 형식 비교  
 `TypeOf`...`Is` 식을 사용하여 개체가 특정 형식의 개체인지 여부를 테스트할 수 있으며  구문은 다음과 같습니다.  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 `typename`이 인터페이스 형식을 지정하는 경우 개체가 인터페이스 형식을 구현하면 `TypeOf`...`Is` 식에서 `True`를 반환합니다.  `typename`이 클래스 형식인 경우 해당 개체가 지정된 클래스의 인스턴스이거나 지정된 클래스에서 파생되는 클래스의 인스턴스이면 식에서 `True`를 반환합니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_4.vb)]  
  
 앞의 예제에서 `x`의 형식이 `Button`이고 `Control`에서 상속되므로 `TypeOf x Is Control` 식은 `True`로 계산됩니다.  
  
 자세한 내용은 [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md)를 참조하십시오.  
  
## 참고 항목  
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operators](../../../../visual-basic/language-reference/operators/index.md)   
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)