---
title: "비교 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a>비교 연산자(Visual Basic)
Visual Basic에서 정의 하는 비교 연산자는 다음과 같습니다.  
  
 `<`연산자  
  
 `<=`연산자  
  
 `>`연산자  
  
 `>=`연산자  
  
 `=`연산자  
  
 `<>`연산자  
  
 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 이러한 연산자는 두 식이 같은지 하 고 그렇지 않은 경우 이러한 어떻게 다른 지 여부를 확인 하려면 비교 합니다. `Is``IsNot`, 및 `Like` 별도 도움말 페이지에 자세하게에서 설명 합니다. 관계 비교 연산자는이 페이지에 자세히 설명 되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. A `Boolean` 비교 결과 나타내는 값입니다.  
  
 `expression`  
 필수 요소. 임의의 식입니다.  
  
 `comparisonoperator`  
 필수 요소. 모든 관계형 비교 연산자입니다.  
  
 `object1`, `object2`  
 필수 요소. 모든 개체 이름을 참조 합니다.  
  
 `string`  
 필수 요소. 임의의 `String` 식입니다.  
  
 `pattern`  
 필수 요소. 모든 `String` 식 또는 문자 범위입니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 관계형 비교 연산자와 결정 하는 조건 목록을 여부 `result` 은 `True` 또는 `False`합니다.  
  
|연산자|`True`if|`False`if|  
|--------------|---------------|----------------|  
|`<`(보다 작음)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=`(작거나 같음)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>`(보다 큼)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=`(보다 크거나 같음)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=`(같음)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>`(같지 않음)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  [연산자 =](../../../visual-basic/language-reference/operators/assignment-operator.md) 할당 연산자로도 사용 됩니다.  
  
 `Is` 연산자는 `IsNot` 연산자 및 `Like` 연산자 앞의 표에 연산자와 다른 특정 비교 기능을 포함 합니다.  
  
## <a name="comparing-numbers"></a>숫자를 비교합니다.  
 형식의 식은 비교할 때 `Single` 형식 중 하나로 `Double`, `Single` 식이 변환 되 `Double`합니다. 이 동작은 Visual Basic 6 동작 반대입니다.  
  
 마찬가지로, 형식의 식은 비교할 때 `Decimal` 형식의 식에 `Single` 또는 `Double`, `Decimal` 식이 변환 되 `Single` 또는 `Double`합니다. 에 대 한 `Decimal` 식 소수 값 보다 작은 1E 28 손실 될 수 있습니다. 이러한 소수 자릿수 값 손실 되지 않은 것으로 비교 하려면 두 값을 발생할 수 있습니다. 이러한 이유로 주의 해야 같음을 사용 하는 경우 (`=`) 부동 소수점 변수 두 개를 비교 합니다. 더 안전의 차이 두 숫자의 절대값 허용 오차 보다 작은지 여부를 테스트 합니다.  
  
### <a name="floating-point-imprecision"></a>부동 소수점 연산이  
 부동 소수점 숫자를 작업할 때는 항상 없는 정확한 표시 메모리에 염두에 둬야 합니다. 값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 [Mod 연산자](../../../visual-basic/language-reference/operators/mod-operator.md)합니다. 자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
## <a name="comparing-strings"></a>문자열 비교  
 문자열을 비교할 때 문자열 식이에 따라 달라 지는 사전순 정렬 순서에 따라 평가 되는 `Option Compare` 설정 합니다.  
  
 `Option Compare Binary`문자열을 비교 문자의 내부 이진 표현에서 파생 된 정렬 순서입니다. 정렬 순서는 코드 페이지에 의해 결정 됩니다. 다음 예제에서는 일반적인 이진 정렬 순서를 보여 줍니다.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text`응용 프로그램의 로캘에 따라 결정 되는 대/소문자 구분 텍스트 정렬 순서에 대 한 비교 문자열 합니다. 설정 하는 경우 `Option Compare Text` 앞의 예에서 문자를 정렬 하 고, 다음 텍스트 정렬 순서가 적용 됩니다.  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>로캘 종속성  
 설정 하는 경우 `Option Compare Text`, 문자열 비교 작업의 결과 응용 프로그램이 실행 되 고 있는 로캘에 따라 달라질 수 있습니다. 두 개의 문자 1 개 로캘만에 동일한 것으로 비교 될 수 있습니다. 로그온 시도를 허용할지 여부와 같은 중요 한 결정을 내릴 수 문자열 비교를 사용 하는 경우에 로캘 구분에 주의 해야 합니다. 설정 하거나 `Option Compare Binary` 호출 또는 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, 하는 로캘의 고려 합니다.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>관대 한 형식의 프로그래밍 관계 비교 연산자  
 관계 비교 연산자를 사용 하 여 `Object` 식에서 허용 되지 않습니다 `Option Strict On`합니다. 때 `Option Strict` 은 `Off`, 고 `expression1` 또는 `expression2` 는 `Object` 식, 런타임 형식의 비교 방법을 결정 합니다. 다음 표에서 식의 비교 방법 및 적용 한 결과 피연산자의 런타임 형식에 따라 비교를 보여 줍니다.  
  
|피연산자가|비교는|  
|---------------------|-------------------|  
|둘 다`String`|문자열 정렬 특성에 따라 비교를 정렬 합니다.|  
|두 숫자|개체 변환 `Double`, 숫자 비교 합니다.|  
|한 숫자가 고 하나`String`|`String` 변환 되는 `Double` 숫자 비교가 수행 됩니다. 경우는 `String` 변환할 수 없습니다 `Double`, <xref:System.InvalidCastException> throw 됩니다.|  
|하나 또는 둘 다가 아닌 다른 참조 형식`String`|<xref:System.InvalidCastException>이 throw됩니다.|  
  
 숫자 비교 처리 `Nothing` 0으로 합니다. 문자열 비교 처리 `Nothing` 으로 `""` (빈 문자열)입니다.  
  
## <a name="overloading"></a>오버로딩  
 관계 비교 연산자 (`<`합니다. `<=``>`, `>=`, `=`, `<>`) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 코드를 사용 하는 이러한 클래스 또는 구조체에서 이러한 연산자를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
 에 [연산자 =](../../../visual-basic/language-reference/operators/assignment-operator.md) 할당 연산자가 아닌 비교 관계형 연산자로 오버 로드 될 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 식을 비교 하는 데 사용할 수 있는 관계 비교 연산자의 다양 한 용도 보여 줍니다. 관계 비교 연산자는 반환 된 `Boolean` 명시 식이 있는지 여부를 나타내는 결과입니다 `True`합니다. 적용 하는 경우는 `>` 및 `<` 연산자를 문자열 면 비교가 수행 되는 문자열의 일반 사전순 정렬 순서를 사용 하 여 합니다. 이 순서는 로캘 설정에 종속 될 수 있습니다. 정렬은 대/소문자 구분 여부에 따라 결정 된 [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) 설정 합니다.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 앞의 예제에서 첫 번째 비교 반환 `False` 나머지 비교 다음 다시 돌아와 `True`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.InvalidCastException>  
 [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
