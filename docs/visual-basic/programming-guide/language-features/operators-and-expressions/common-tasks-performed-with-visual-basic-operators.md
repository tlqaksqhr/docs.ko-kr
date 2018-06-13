---
title: Visual Basic 연산자를 사용한 일반적인 작업
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], logical
- operators [Visual Basic], string concatenation
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- operators [Visual Basic], arithmetic
- operators [Visual Basic], string comparison
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- operators [Visual Basic], comparison
- operators [Visual Basic], short-circuiting logical
ms.assetid: d181afe5-fafa-460f-a13b-81203f6f4587
ms.openlocfilehash: ab0b7e7c35992908aeaac14053665ff84719f1fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654728"
---
# <a name="common-tasks-performed-with-visual-basic-operators"></a>Visual Basic 연산자를 사용한 일반적인 작업
연산자는 호출 하는 하나 이상의 식과 관련 된 여러 가지 일반적인 작업 수행 *피연산자*합니다.  
  
## <a name="arithmetic-and-bit-shift-tasks"></a>산술 및 비트 시프트 작업  
 다음 표에서 사용 가능한 산술 및 비트 시프트 연산을 요약 되어 있습니다.  
  
|대상|보기|  
|---|---|  
|다른 숫자 값 하나를 추가 합니다.|[+ 연산자](../../../../visual-basic/language-reference/operators/addition-operator.md)|  
|한 숫자 값에서 다른 값 빼기|[-연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)|  
|숫자 값의 부호 반전|[-연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)|  
|곱하기 숫자 값을 다른 값|[* 연산자](../../../../visual-basic/language-reference/operators/multiplication-operator.md)|  
|다른 파티션으로 하나의 숫자 값을 나눌|[/ 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)|  
|1 숫자 값 (나머지) 없이 다른으로 나눈 값의 몫을 찾기|[\ 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)|  
|하나의 숫자 값 (몫) 다른 나눈 나머지를 구하려는|[Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)|  
|발생 한 숫자 값의 다른 값|[^ 연산자](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)|  
|숫자 값의 비트 패턴을 왼쪽으로 이동|[<\< 연산자](../../../../visual-basic/language-reference/operators/left-shift-operator.md)|  
|숫자 값의 비트 패턴을 오른쪽으로 이동|[>> 연산자](../../../../visual-basic/language-reference/operators/right-shift-operator.md)|  
  
## <a name="comparison-tasks"></a>비교 작업  
 다음 표에서 사용 가능한 비교 연산을 요약 되어 있습니다.  
  
|대상|보기|  
|---|---|  
|두 값이 같은지 여부를 결정 합니다.|`=` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|두 값이 같은지 여부를 결정 합니다.|`<>` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|값이 두 개 다른 노드보다 작은지 여부를 결정 합니다.|`<` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|값이 두 개 다른 노드보다 큰지 여부를 결정 합니다.|`>` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|하나의 값이 다른 보다 작거나 같은지 여부 확인|`<=` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|하나의 값이 다른 보다 크거나 여부 확인|`>=` 연산자 ([Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md))|  
|두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 확인|[Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md)|  
|두 개체 변수가 서로 다른 개체 인스턴스를 참조 하는지 확인|[IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)|  
|개체를 특정 형식 인지 확인|[TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)|  
  
## <a name="concatenation-tasks"></a>연결 연산 작업  
 다음 표에서 사용 가능한 연결 작업을 요약 합니다.  
  
|대상|참조|  
|---|---|  
|여러 문자열을 단일 문자열로 조인|`&` 연산자 ([Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md))|  
|숫자 값을 문자열 값과 조인|`+` 연산자 ([Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md))|  
  
## <a name="logical-and-bitwise-tasks"></a>논리 및 비트 작업  
 다음 표에서 사용 가능한 논리 및 비트 연산을 요약 되어 있습니다.  
  
|대상|보기|  
|---|---|  
|부울 값에 논리 부정을 수행합니다|[Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md)|  
|두 부울 값에 논리 결합을 수행 합니다.|[And 연산자](../../../../visual-basic/language-reference/operators/and-operator.md)|  
|두 부울 값의 포함 논리합 연산을 수행합니다|[Or 연산자](../../../../visual-basic/language-reference/operators/or-operator.md)|  
|두 부울 값의 배타적 논리합 연산을 수행합니다|[Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md)|  
|두 부울 값의 short-circuited 논리 결합을 수행 합니다.|[AndAlso 연산자](../../../../visual-basic/language-reference/operators/andalso-operator.md)|  
|두 부울 값의 포함 논리합 short-circuited 수행|[OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md)|  
|두 정수 값에 비트 단위로 논리 결합을 수행 합니다.|[And 연산자](../../../../visual-basic/language-reference/operators/and-operator.md)|  
|두 정수 값의 비트 단위로 포함 논리합 수행|[Or 연산자](../../../../visual-basic/language-reference/operators/or-operator.md)|  
|두 정수 값에 비트 단위로 배타적 논리합 연산을 수행합니다|[Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md)|  
|정수 계열 값의 비트 단위로 논리 부정을 수행합니다|[Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md)|  
  
## <a name="see-also"></a>참고 항목  
 [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [기능별 연산자 목록](../../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
