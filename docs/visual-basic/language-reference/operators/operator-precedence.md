---
title: "Visual Basic의 연산자 우선 순위 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6532fc0c26db3b736c863be075571570a3d25eef
ms.lasthandoff: 03/13/2017

---
# <a name="operator-precedence-in-visual-basic"></a>Visual Basic에서의 연산자 우선 순위
각 부분 평가 되 고 호출 하는 미리 결정 된 순서로 해결 식에서 몇 가지 작업이 발생할 때 *연산자 우선 순위*합니다.  
  
## <a name="precedence-rules"></a>우선 순위 규칙  
 식 연산자에서 둘 이상의 범주를 포함 하는 경우 다음 규칙에 따라 계산 됩니다.  
  
-   산술 및 연결 연산자는 다음 섹션에서 설명 하는 우선 순위를 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자입니다.  
  
-   모든 비교 연산자 있고 우선 순위가 동일한 연산자는 논리 및 비트 연산자 보다 우선 순위가 높은 있으며 산술 및 연결 연산자 보다 우선 순위가 모두 있습니다.  
  
-   논리 및 비트 연산자는 다음 섹션에서 설명 하는 우선 순위를 있고 모든 산술, 연결 및 비교 연산자 보다 우선 순위가 있습니다.  
  
-   우선 순위가 같은 연산자는 왼쪽에서 오른쪽 계산 식에 나타나는 순서입니다.  
  
## <a name="precedence-order"></a>우선 순위  
 연산자의 우선 순위는 다음과 같은 순서로 평가 됩니다.  
  
### <a name="await-operator"></a>Await 연산자  
 대기  
  
### <a name="arithmetic-and-concatenation-operators"></a>산술 및 연결 연산자  
 지 수 (`^`)  
  
 단항 같음 및 부정 (`+`, `–`)  
  
 곱하기 및 부동 소수점 나누기 (`*`, `/`)  
  
 정수 나누기 (`\`)  
  
 산술 나머지 (`Mod`)  
  
 더하기와 빼기 (`+`, `–`)  
  
 문자열 연결 (`&`)  
  
 산술 비트 시프트 (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>비교 연산자  
 All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자  
 부정 (`Not`)  
  
 함께 (`And`, `AndAlso`)  
  
 포함 논리합 (`Or`, `OrElse`)  
  
 배타적 논리합 (`Xor`)  
  
### <a name="comments"></a>설명  
 `=` 연산자는 같음 비교 연산자만, 대입 연산자가 없습니다.  
  
 문자열 연결 연산자 (`&`)는 산술 연산자가 산술 연산자와 그룹화는 우선 순위에 따라 하지만 발생 합니다.  
  
 `Is` 및 `IsNot` 연산자는 개체 참조 비교 연산자입니다. 두 개체의 값을 비교 하지 않습니다. 이러한 두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 여부 확인에 확인 합니다.  
  
## <a name="associativity"></a>결합성  
 동일한 우선 순위의 연산자는 식, 곱하기 및 나누기, 예를 들어에 함께 표시 하는 경우 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다. 다음은 이에 대한 예입니다.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 첫 번째 식이 96 나누기 / 8 (함 결과 12) 및 나누기 12 / 4 결과 3입니다. 에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 평가 동일한에 대 한이 순서를 명시적으로 지정 하는 경우 `n2`합니다. 둘 다 `n1` 및 `n2` 결과는&3;입니다. 반면, `n3` 48의 결과 괄호 8을 평가 하는 컴파일러가 / 4 첫 번째입니다.  
  
 이 동작으로 인해 연산자에 있다고 *왼쪽 결합형* 에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
## <a name="overriding-precedence-and-associativity"></a>우선 순위 및 결합성 재정의  
 다른 사용자 보다 먼저 계산 하는 식의 일부분에 괄호를 사용할 수 있습니다. 이 우선 순위와 왼쪽된 결합성 재정의할 수 있습니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]항상 외부 보다 먼저 괄호로 묶여 있는 작업을 수행 합니다. 그러나 괄호 안에 유지 일반 우선 순위와 결합성 괄호 안에서 괄호를 사용 하지 않으면 됩니다. 다음은 이에 대한 예입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await 연산자](../../../visual-basic/language-reference/operators/await-operator.md)   
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
