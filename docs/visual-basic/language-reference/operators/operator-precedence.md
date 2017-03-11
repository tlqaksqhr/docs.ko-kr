---
title: "Operator Precedence in Visual Basic | Microsoft Docs"
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
  - "arithmetic operators, precedence"
  - "operator precedence"
  - "logical operators, precedence"
  - "operators [Visual Basic], associativity"
  - "operators [Visual Basic], resolution"
  - "associativity of operators"
  - "operators [Visual Basic], precedence"
  - "precedence, of operators"
  - "comparison operators, precedence"
  - "math operators"
  - "order of precedence"
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Operator Precedence in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식에서 여러 연산이 수행되는 경우 *연산자 우선 순위*라는 미리 지정된 순서에 따라 각 부분이 계산되고 결정됩니다.  
  
## 우선 순위 규칙  
 식에 두 개 이상의 범주에 속한 연산자가 있으면 해당 식은 다음 규칙에 따라 계산됩니다.  
  
-   산술 연산자와 연결 연산자는 다음 단원에서 설명하는 우선 순위를 가지며, 모두 비교, 논리 및 비트 연산자보다 높은 우선 순위를 가집니다.  
  
-   모든 비교 연산자의 우선 순위는 같습니다. 또한 모든 비교 연산자는 논리 연산자 및 비트 연산자보다 우선 순위가 높지만 산술 연산자 및 연결 연산자보다는 낮습니다.  
  
-   논리 및 비트 연산자는 다음 단원에서 설명하는 우선 순위를 가지며 모두 산술, 연결 및 비교 연산자보다 우선 순위가 낮습니다.  
  
-   우선 순위가 같은 연산자들은 식에 나타나는 순서에 따라 왼쪽에서 오른쪽으로 계산됩니다.  
  
## 우선 순위  
 연산자는 다음 우선 순위에 따라 계산됩니다.  
  
### 운영자를 기다립니다  
 대기  
  
### 산술 및 연결 연산자  
 지수 연산자\(`^`\)  
  
 단항 같음 및 부정\(`+`, `–`\)  
  
 곱하기 및 부동 소수점 나누기\(`*`, `/`\)  
  
 정수 나누기\(`\`\)  
  
 나머지 연산자\(`Mod`\)  
  
 더하기와 빼기 \(`+`, `–`\)  
  
 문자열 연결\(`&`\)  
  
 산술 비트 시프트 연산\(`<<`, `>>`\)  
  
### 비교 연산자  
 모든 비교 연산자\(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`\)  
  
### 논리 및 비트 연산자  
 부정 연산자\(`Not`\)  
  
 논리곱 연산자\(`And`, `AndAlso`\)  
  
 포함적 논리합\(`Or`, `OrElse`\)  
  
 배타적 논리합\(`Xor`\)  
  
### 설명  
 `=` 연산자는 할당 연산자가 아니라 같음 비교 연산자입니다.  
  
 문자열 연결 연산자\(`&`\)는 산술 연산자가 아니지만 우선 순위 면에서 산술 연산자와 같은 그룹에 포함됩니다.  
  
 `Is` 및 `IsNot` 연산자는 개체 참조 비교 연산자입니다.  두 개체의 값은 비교하지 않고 두 개체 변수가 같은 개체 인스턴스를 참조하는지 여부만 확인합니다.  
  
## 결합성  
 승제 연산처럼 우선 순위가 같은 연산자가 식에 함께 나타나는 경우에는 컴파일러가 왼쪽에서 오른쪽의 순으로 계산합니다.  다음은 이에 대한 예입니다.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 첫 번째 식은 나누기 96 \/ 8\(결과 12\)을 계산한 다음 나누기 12 \/ 4\(결과 3\)를 계산합니다.  컴퓨터는 `n1`에 대한 연산을 왼쪽에서 오른쪽으로 계산하므로 계산은 `n2`에 대한 순서를 명시적으로 지정했을 때와 동일합니다.  `n1`과 `n2`의 결과는 3입니다.  이와 반대로 `n3`의 경우에는 괄호 때문에 컴파일러에서 8 \/ 4가 먼저 계산되므로 결과는 48입니다.  
  
 이러한 동작 때문에 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산자가 *왼쪽으로부터 결합*된다고 합니다.  
  
## 우선 순위 및 결합성 재정의  
 괄호를 사용하여 식의 일부분을 다른 부분보다 먼저 계산할 수 있습니다.  이렇게 하면 우선 순위와 왼쪽으로부터의 결합성이 재정의됩니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]전에 외부 괄호로 묶인 작업을 항상 수행 합니다. 그러나 괄호 안에서 괄호를 사용 하지 않는 괄호 안에 일반적인 우선 순위와 결합성을 유지.  다음은 이에 대한 예입니다.  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## 참고 항목  
 [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)