---
title: "Mod 연산자(Visual Basic) | Microsoft Docs"
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
  - "vb.Mod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "나머지(Mod 연산자)"
  - "나누기 연산자, Mod 연산자"
  - "나머지 연산자, Visual Basic"
  - "Mod 연산자[Visual Basic]"
  - "연산자[Visual Basic], 나누기"
  - "산술 연산자, Mod"
  - "수학 연산자"
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Mod 연산자(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 숫자를 나눈 다음 나머지만 반환합니다.  
  
## 구문  
  
```  
  
number1 Mod number2  
```  
  
## 요소  
 `number1`  
 필수 요소.  임의의 숫자 식입니다.  
  
 `number2`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 지원 형식  
 모든 숫자 데이터 형식입니다.  여기에는 부호 없는 형식, 부동 소수점 형식 및 `Decimal`이 포함됩니다.  
  
## 결과  
 결과는 `number1`을 `number2`로 나눈 나머지입니다.  예를 들어 `14 Mod 4` 식의 계산 결과는 2입니다.  
  
## 설명  
 `number1` 또는 `number2`가 부동 소수점 값이면 나눗셈의 부동 소수점 나머지가 반환됩니다.  결과의 데이터 형식은 `number1` 및 `number2`의 데이터 형식으로 나눈 결과의 모든 가능한 값을 가질 수 있는 가장 작은 데이터 형식입니다.  
  
 `number1` 또는 `number2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 0으로 처리됩니다.  
  
 관련 연산자는 다음과 같습니다.  
  
-   [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)는 나눗셈의 정수 몫을 반환합니다.  예를 들어 `14 \ 4` 식의 계산 결과는 3입니다.  
  
-   [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)는 나머지를 부동 소수점 숫자로 포함한 전체 몫을 반환합니다.  예를 들어 `14 / 4` 식의 계산 결과는 3.5입니다.  
  
## 0으로 나누기 수행  
 `number2`가 0으로 계산되면 `Mod` 연산자의 동작은 피연산자의 데이터 형식에 따라 달라집니다.  정수 나누기는 <xref:System.DivideByZeroException> 예외를 throw합니다.  부동 소수점 나누기는 <xref:System.Double.NaN>을 반환합니다.  
  
## 동등 수식  
 `a Mod b` 식은 다음 수식과 동등합니다.  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## 부동 소수점 부정확성  
 부동 소수점 숫자에 대한 작업을 수행하는 경우 해당 숫자가 메모리에서 항상 정확하게 표현되지 않는다는 점에 주의합니다.  따라서 값 비교, `Mod` 연산자 등과 같은 특정 연산에서 예기치 않은 결과가 나타날 수 있습니다.  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조하십시오.  
  
## 오버로딩  
 `Mod` 연산자는 *오버로드*될 수 있습니다. 즉, 클래스나 구조체에서 해당 동작을 다시 정의할 수 있습니다.  코드에서 `Mod`를 이러한 오버로드가 포함된 클래스나 구조체의 인스턴스에 적용하는 경우 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Mod` 연산자를 사용하여 두 숫자를 나누고 나머지만 반환합니다.  두 숫자 중 어느 하나가 부동 소수점 숫자인 경우, 결과는 나머지를 나타내는 부동 소수점 숫자입니다.  
  
 [!CODE [VbVbalrOperators#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#31)]  
  
## 예제  
 다음 예제에서는 부동 소수점 피연산자의 잠재적인 부정확성에 대해 설명합니다.  첫 번째 문에서 피연산자는 `Double`이고 0.2는 저장된 값이 0.20000000000000001인 무한 반복되는 이진 소수입니다.  두 번째 문에서 리터럴 형식 문자 `D`는 두 피연산자를 모두 `Decimal`로 강제하며 0.2는 정확한 표시를 가집니다.  
  
 [!CODE [VbVbalrOperators#32](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#32)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)