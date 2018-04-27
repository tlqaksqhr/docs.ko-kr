---
title: Comparison Operators in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77c5520be63d6d05cc4b895b99b466cd8e486f6a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
두 식을 비교 하 고 반환 하는 비교 연산자는 `Boolean` 값의 관계를 나타내는 값입니다. 숫자 값, 문자열, 비교 연산자 및 개체를 비교 연산자를 비교 하는 데는 연산자입니다. 세 가지 유형의 연산자를 모두 여기에 설명 되어 있습니다.  
  
## <a name="comparing-numeric-values"></a>숫자 값 비교  
 Visual Basic 6 명의 숫자 비교 연산자를 사용 하 여 숫자 값을 비교 합니다. 각 연산자는 숫자 값으로 계산 되는 두 식 피연산자 변수로 사용 합니다. 다음 표에서 연산자를 나열 하 고 각각의 예를 보여 줍니다.  
  
|연산자|테스트 조건|예제|  
|--------------|----------------------|--------------|  
|`=` (같음)|두 번째 값으로 첫 번째 식이 같음의 값은?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (같지 않음)|첫 번째 식의 값과 같지 않은 값의 두 번째?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (보다 작음)|첫 번째 식의 값 보다 작지의 두 번째 값은?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (보다 큼)|첫 번째 식의 값이 두 번째 값 보다 크면?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (작거나 같음)|두 번째 값 보다 작거나 같은 첫 번째 식의 값은?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (보다 크거나 같음)|두 번째 값 보다 크거나 같은 경우 첫 번째 식의 값은?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>문자열 비교  
 Visual Basic을 사용 하 여 문자열 비교는 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md) 숫자 비교 연산자 뿐 아니라 합니다. `Like` 연산자를 사용 하면 패턴을 지정할 수 있습니다. 문자열을 다음 패턴에 대해 비교 하 고, 일치 하는 경우 결과 `True`합니다. 그렇지 않으면 결과 `False`합니다. 숫자 연산자를 사용 하 여 비교할 수 `String` 다음 예제와 같이 정렬 순서에 따라 값입니다.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 앞의 예제에서 결과 `True` 하므로 첫 번째 문자열의 첫 번째 문자는 두 번째 문자열의 첫 번째 문자 앞에 정렬 합니다. 첫 번째 문자가 같은 인 경우 비교는 두 문자열의 다음 문자가 계속 등에입니다. 다음 예제와 같이 같음 연산자를 사용 하 여 문자열의 일치 여부를 테스트할 수 있습니다.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 한 문자열 "aa" 및 "aaa"와 같은 다른 접두사의 형식이 더 긴 문자열 짧은 문자열 보다 큰 것으로 간주 됩니다. 다음은 이에 대한 예입니다.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 정렬 순서는 이진 비교 또는의 설정에 따라 텍스트 비교를 기반으로 하며 `Option Compare`합니다. 자세한 내용은 참조 [옵션 비교 문](../../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.  
  
## <a name="comparing-objects"></a>개체 비교  
 Visual Basic 비교 된 두 개체 참조 변수는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 및 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)합니다. 동일한 개체 인스턴스를 두 개의 참조 변수 참조를 확인 하려면 이러한 연산자 중 하나를 사용할 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 앞의 예제에서 `x Is y` 계산 `True`두 변수가 같은 인스턴스를 참조 하므로, 합니다. 다음 예제로이 결과 대조 됩니다.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 앞의 예제에서 `x Is y` 계산 `False`변수 동일한 유형의 개체를 참조 하지만 해당 형식의 다른 인스턴스를 참조 하기 때문에, 합니다.  
  
 동일한 인스턴스를 가리키지 않는 두 개체에 대 한 테스트 하려는 경우는 `IsNot` 연산자를 사용 하면 문법적으로 어 색 하 게 조합 하지 않아도 `Not` 및 `Is`합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 앞의 예제에서 `If a IsNot b` 같습니다 `If Not a Is b`합니다.  
  
### <a name="comparing-object-type"></a>개체 유형 비교  
 사용 하 여 특정 형식의 개체는 있는지 테스트할 수 있습니다는 `TypeOf`... `Is` 식입니다. 구문은 다음과 같습니다.  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 때 `typename` 인터페이스 형식을 지정 하면 `TypeOf`... `Is` 식 반환 `True` 개체 인터페이스 형식을 구현 하는 경우. 때 `typename` 다음 식은 반환 형식이 있는 클래스 형식인 `True` 개체가 지정된 된 클래스에서 파생 되는 클래스 또는 지정된 된 클래스의 인스턴스입니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 앞의 예제에는 `TypeOf x Is Control` 식이 `True` 때문에 유형의 `x` 은 `Button`에서 상속 되 `Control`합니다.  
  
 자세한 내용은 참조 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [비교 연산자](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [연산자](../../../../visual-basic/language-reference/operators/index.md)  
 [Visual Basic의 산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
