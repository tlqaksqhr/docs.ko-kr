---
title: "+ Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.+"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operators, addition"
  - "+ operator"
  - "concatenation operators, syntax"
  - "strings [Visual Basic], concatenating"
  - "sum operator"
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# + Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

숫자 식의 양수 값을 반환하거나 두 수를 더합니다.  두 문자열 식을 연결할 때도 사용할 수 있습니다.  
  
## 구문  
  
```  
  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`expression1`|필수 요소.  임의의 숫자 또는 문자열 식입니다.|  
|`expression2`|`+` 연산자가 음수 값을 계산하지 않는 경우 필수적 요소입니다.  임의의 숫자 또는 문자열 식입니다.|  
  
## 결과  
 `expression1`과 `expression2`가 모두 숫자인 경우 결과는 산술 합계입니다.  
  
 `expression2`가 없는 경우 `+` 연산자는 식의 변경되지 않은 값에 대한 *단항* 같음 연산자입니다.  이 경우 `expression1`을 해당 부호와 함께 연산하므로 `expression1`이 음수인 경우 결과는 음수입니다.  
  
 `expression1`과 `expression2`가 모두 문자열인 경우 결과는 해당 값을 연결한 것입니다.  
  
 `expression1`과 `expression2`가 숫자와 문자열의 조합인 경우 수행할 작업은 해당 형식과 내용 및 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) 설정에 따라 다릅니다.  자세한 내용은 "설명" 부분의 표를 참조하십시오.  
  
## 지원 형식  
 부호 없는 형식, 부동 소수점 형식, `Decimal`, `String`을 비롯한 모든 숫자 형식입니다.  
  
## 설명  
 일반적으로 `+`는 산술 더하기를 수행하고 두 식이 모두 문자열인 경우에만 식을 연결합니다.  
  
 두 식이 모두 `Object`가 아닌 경우 Visual Basic에서는 다음과 같은 작업을 수행합니다.  
  
|||  
|-|-|  
|식의 데이터 형식|컴파일러 작업|  
|두 식이 모두 숫자 데이터 형식\(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` 또는 `Double`\)인 경우|더합니다.  결과 데이터 형식은 `expression1`과 `expression2`의 데이터 형식에 적합한 숫자 형식입니다.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 연산" 표를 참조하십시오.|  
|두 식이 모두 `String` 형식인 경우|연결합니다.|  
|한 식은 숫자 데이터 형식이고 다른 식은 문자열인 경우|`Option Strict`가 `On`으로 설정된 경우 컴파일러 오류가 발생합니다.<br /><br /> `Option Strict`가 `Off`로 설정된 경우 `String`을 `Double`로 암시적으로 변환한 다음 더합니다.<br /><br /> `String`을 `Double`로 변환할 수 없으면 <xref:System.InvalidCastException> 예외가 throw됩니다.|  
|한 식은 숫자 데이터 형식이고 다른 식은 [Nothing](../../../visual-basic/language-reference/nothing.md)인 경우|`Nothing` 값은 0으로 하고 더합니다.|  
|한 식은 문자열이고 다른 식은 `Nothing`인 경우|`Nothing` 값은 ""로 하고 연결합니다.|  
  
 식 하나가 `Object` 식인 경우 Visual Basic에서는 다음과 같은 작업을 수행합니다.  
  
|||  
|-|-|  
|식의 데이터 형식|컴파일러 작업|  
|`Object` 식이 숫자 값을 사용하고 다른 식이 숫자 데이터 형식인 경우|`Option Strict`가 `On`으로 설정된 경우 컴파일러 오류가 발생합니다.<br /><br /> `Option Strict`가 `Off`로 설정된 경우 더합니다.|  
|`Object` 식이 숫자 값을 사용하고 다른 식이 `String` 형식인 경우|`Option Strict`가 `On`으로 설정된 경우 컴파일러 오류가 발생합니다.<br /><br /> `Option Strict`가 `Off`로 설정된 경우 `String`을 `Double`로 암시적으로 변환한 다음 더합니다.<br /><br /> `String`을 `Double`로 변환할 수 없으면 <xref:System.InvalidCastException> 예외가 throw됩니다.|  
|`Object` 식이 문자열을 사용하고 다른 식이 숫자 데이터 형식인 경우|`Option Strict`가 `On`으로 설정된 경우 컴파일러 오류가 발생합니다.<br /><br /> `Option Strict`가 `Off`로 설정된 경우 문자열 `Object`를 `Double`로 암시적으로 변환한 다음 더합니다.<br /><br /> 문자열 `Object`를 `Double`로 변환할 수 없으면 <xref:System.InvalidCastException> 예외가 throw됩니다.|  
|`Object`식이 문자열을 사용하고 다른 식이 `String` 형식인 경우|`Option Strict`가 `On`으로 설정된 경우 컴파일러 오류가 발생합니다.<br /><br /> `Option Strict`가 `Off`로 설정된 경우 `Object`를 `String`으로 암시적으로 변환한 다음 연결합니다.|  
  
 두 식이 모두 `Object` 식인 경우 Visual Basic에서는 다음과 같은 작업을 수행합니다\(`Option Strict Off`에만 해당\).  
  
|||  
|-|-|  
|식의 데이터 형식|컴파일러 작업|  
|두 `Object` 식이 모두 숫자 값을 사용하는 경우|더합니다.|  
|두 `Object` 식이 모두 `String` 형식인 경우|연결합니다.|  
|한 `Object` 식이 숫자 값을 사용하고 다른 식이 문자열을 사용하는 경우|문자열 `Object`를 `Double`로 암시적으로 변환한 다음 더합니다.<br /><br /> 문자열 `Object`를 숫자 값으로 변환할 수 없는 경우 <xref:System.InvalidCastException> 예외가 throw됩니다.|  
  
 `Object` 식이 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 <xref:System.DBNull>로 계산되는 경우 `+` 연산자는 해당 식을 값이 ""인 `String`으로 간주합니다.  
  
> [!NOTE]
>  `+` 연산자를 사용하는 경우 더하기 또는 문자열 연결 연산의 발생 여부를 확인할 수 없습니다.  그러나 `&` 연산자를 사용하여 연결하면 이러한 모호성을 제거할 수 있고 자체 문서 작성 코드를 사용할 수 있습니다.  
  
## 오버로딩  
 `+` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `+` 연산자를 사용하여 숫자를 더합니다.  피연산자가 모두 숫자인 경우 Visual Basic에서는 산술 결과를 계산합니다.  산술 결과는 두 피연산자의 합계로 표시됩니다.  
  
 [!CODE [VbVbalrOperators#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#6)]  
  
 또한 `+` 연산자를 사용하여 문자열을 연결할 수도 있습니다.  피연산자가 모두 문자열인 경우 Visual Basic에서는 두 문자열을 연결합니다.  연결 결과는 두 피연산자의 내용을 서로 연결한 단일 문자열로 표시됩니다.  
  
 피연산자가 혼합 형식인 경우 결과는 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)의 설정에 따라 다릅니다.  다음 예제에서는 `Option Strict`가 `On`으로 설정된 경우의 결과를 보여 줍니다.  
  
 [!CODE [VbVbalrOperators#53](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#53)]  
  
 [!CODE [VbVbalrOperators#50](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#50)]  
[!CODE [VbVbalrOperators#51](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#51)]  
  
 다음 예제에서는 `Option Strict`가 `Off`로 설정된 경우의 결과를 보여 줍니다.  
  
 [!CODE [VbVbalrOperators#54](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#54)]  
  
 [!CODE [VbVbalrOperators#50](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#50)]  
[!CODE [VbVbalrOperators#52](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#52)]  
  
 모호성을 제거하려면 연결에 `+` 대신 `&` 연산자를 사용해야 합니다.  
  
## 참고 항목  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [Concatenation Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)