---
title: "Common Tasks Performed with Visual Basic Operators | Microsoft Docs"
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
  - "operators [Visual Basic], logical"
  - "operators [Visual Basic], string concatenation"
  - "operators [Visual Basic], bitwise"
  - "operators [Visual Basic], bit-shift"
  - "operators [Visual Basic], arithmetic"
  - "operators [Visual Basic], string comparison"
  - "operators [Visual Basic], concatenation"
  - "Visual Basic code, operators"
  - "operators [Visual Basic], comparison"
  - "operators [Visual Basic], short-circuiting logical"
ms.assetid: d181afe5-fafa-460f-a13b-81203f6f4587
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Common Tasks Performed with Visual Basic Operators
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

연산자는 *피연산자*라는 하나 이상의 식과 관련된 여러 가지 일반적인 작업을 수행합니다.  
  
## 산술 또는 비트 시프트 연산 작업  
 다음 표에서는 사용 가능한 산술 및 비트 시프트 연산을 요약하여 설명합니다.  
  
|||  
|-|-|  
|To|참조|  
|한 숫자 값과 다른 숫자 값 더하기|[\+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md)|  
|한 숫자 값에서 다른 숫자 값 빼기|[\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md)|  
|숫자 값의 기호 바꾸기|[\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md)|  
|한 숫자 값을 다른 숫자 값과 곱하기|[\* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md)|  
|한 숫자 값을 다른 숫자 값으로 나누기|[\/ Operator](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)|  
|한 숫자 값을 다른 숫자 값으로 나눈 몫 구하기\(나머지 무시\)|[\\ Operator](../../../../visual-basic/language-reference/operators/integer-division-operator.md)|  
|한 숫자 값을 다른 숫자 값으로 나눈 나머지 구하기\(몫 무시\)|[Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)|  
|한 숫자 값을 다른 숫자 값의 승수로 거듭제곱|[^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)|  
|숫자 값의 비트 패턴을 왼쪽으로 시프트|[\<\< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md)|  
|숫자 값의 비트 패턴을 오른쪽으로 시프트|[\>\> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md)|  
  
## 비교 연산 작업  
 다음 표에서는 사용 가능한 비교 연산을 요약하여 설명합니다.  
  
|||  
|-|-|  
|To|참조|  
|두 값이 같은지 여부 확인|`=` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|두 값이 같지 않은지 여부 확인|`<>` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|한 값이 다른 값보다 작은지 여부 확인|`<` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|한 값이 다른 값보다 큰지 여부 확인|`>` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|한 값이 다른 값보다 작거나 같은지 여부 확인|`<=` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|한 값이 다른 값보다 크거나 같은지 여부 확인|`>=` 연산자\([Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)\)|  
|두 개체 변수가 동일한 개체 인스턴스를 참조하는지 여부 확인|[Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)|  
|두 개체 변수가 다른 개체 인스턴스를 참조하는지 여부 확인|[IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)|  
|개체가 특정 형식인지 여부 확인|[TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md)|  
  
## 연결 연산 작업  
 다음 표에서는 사용 가능한 연결 연산을 요약하여 설명합니다.  
  
|||  
|-|-|  
|To|참조|  
|여러 문자열을 단일 문자열로 조인|`&` 연산자\([Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)\)|  
|숫자 값을 문자열 값으로 조인|`+` 연산자\([Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)\)|  
  
## 논리 및 비트 연산 작업  
 다음 표에서는 사용 가능한 논리 및 비트 연산을 요약하여 설명합니다.  
  
|||  
|-|-|  
|To|참조|  
|부울 값의 논리 부정 연산 수행|[Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md)|  
|두 부울 값의 논리 연결 연산 수행|[And Operator](../../../../visual-basic/language-reference/operators/and-operator.md)|  
|두 부울 값의 포함 논리합 연산 수행|[Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md)|  
|두 부울 값의 배타적 논리합 연산 수행|[Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md)|  
|두 부울 값의 단락\(short circuit\) 논리곱 연산 수행|[AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md)|  
|두 부울 값의 단락\(short circuit\) 포함 논리합 연산 수행|[OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md)|  
|두 정수 계열 값의 비트별 논리곱 연산 수행|[And Operator](../../../../visual-basic/language-reference/operators/and-operator.md)|  
|두 정수 계열 값의 비트별 포함 논리합 연산 수행|[Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md)|  
|두 정수 계열 값의 비트별 배타적 논리합 연산 수행|[Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md)|  
|정수 계열 값의 비트별 논리 부정 연산 수행|[Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md)|  
  
## 참고 항목  
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Operators Listed by Functionality](../../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)