---
title: "Visual Basic에서의 연산자 우선 순위"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a>Visual Basic에서의 연산자 우선 순위
각 부분 평가 되 고 호출 미리 결정 된 순서 대로 확인 식에서 여러 작업이 발생 하는 경우 *연산자 우선 순위*합니다.  
  
## <a name="precedence-rules"></a>선행 규칙  
 식에 포함 될 연산자는 둘 이상의 범주에서 다음 규칙에 따라 평가 됩니다.  
  
-   산술 연산, 연결 연산자의 다음 섹션에서 설명 하는 우선 순위 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자.  
  
-   같은 우선 순위와는 논리 및 비트 연산자 보다 높은 우선 순위 있지만 순위 연산자 보다 우선 순위가 있는 모든 포함 된 모든 비교 연산자.  
  
-   논리 및 비트 연산자의 다음 섹션에서 설명 하는 우선 순위 있고 모든 산술 연산, 연결 및 비교 연산자 보다 우선 순위가 낮습니다.  
  
-   우선 순위가 같은 연산자는 오른쪽으로 계산 왼쪽 식에 나타나는 순서.  
  
## <a name="precedence-order"></a>우선 순위  
 연산자 우선 순위는 다음 순서 대로 평가 됩니다.  
  
### <a name="await-operator"></a>Await 연산자  
 await  
  
### <a name="arithmetic-and-concatenation-operators"></a>산술 및 연결 연산자  
 지 수 (`^`)  
  
 단항 id 및 부정 (`+`, `–`)  
  
 곱하기와 나누기 부동 소수점 (`*`, `/`)  
  
 정수 나누기 (`\`)  
  
 모듈러스 산술 (`Mod`)  
  
 더하기와 빼기 (`+`, `–`)  
  
 문자열 연결 (`&`)  
  
 산술 비트 시프트 (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>비교 연산자  
 모든 비교 연산자 (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자  
 부정 (`Not`)  
  
 함께 (`And`, `AndAlso`)  
  
 포함 논리합 (`Or`, `OrElse`)  
  
 배타적 논리합 (`Xor`)  
  
### <a name="comments"></a>설명  
 `=` 연산자는만 같음 비교 연산자, 대입 연산자가 없습니다.  
  
 문자열 연결 연산자 (`&`)는 산술 연산자가 있지만 산술 연산자와 그룹화가 우선에서 합니다.  
  
 `Is` 및 `IsNot` 연산자는 개체 참조 비교 연산자. 두 개체;의 값을 비교 하지 않습니다. 이러한 두 개체 변수가 동일한 개체 인스턴스를 나타내는지 확인에 확인 합니다.  
  
## <a name="associativity"></a>결합성  
 동일한 우선 순위의 연산자를 식, 곱하기 및 나누기, 예를 들어에 함께 나타납니다. 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다. 다음은 이에 대한 예입니다.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 첫 번째 식이 96 나누기 / 8 (있음 결과 12) 및 나누기 12 / 결과 3 4입니다. 에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 계산 같습니다에 대 한 해당 순서를 명시적으로 지정 하는 경우 `n2`합니다. 둘 다 `n1` 및 `n2` 결과는 3입니다. 반면, `n3` 괄호는 컴파일러가 8 평가 때문에 48의 결과가 / 4 첫 번째입니다.  
  
 이러한 동작으로 인해 연산자에 있다고 *왼쪽 결합형* 에서 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.  
  
## <a name="overriding-precedence-and-associativity"></a>재정의 우선 순위 및 결합성  
 다른 대체 이전 평가할 식의 일부분에 괄호를 사용할 수 있습니다. 우선 순위와 왼쪽된 결합성을 재정의할 수 있습니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]항상 외부 보다 먼저 괄호로 묶여 있는 작업을 수행 합니다. 그러나 괄호 안에 유지 일반 우선 순위와 결합성 괄호 안에 괄호를 사용 하지 않는 한 됩니다. 다음은 이에 대한 예입니다.  
  
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
