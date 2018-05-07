---
title: '방법: 프로시저의 매개 변수 정의(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: b058f593b8672da449dac250947563c75c8386bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>방법: 프로시저의 매개 변수 정의(Visual Basic)
A *매개 변수* 호출 코드를 호출할 때 프로시저에 값을 전달할 수 있습니다. 동일한 방식으로 변수를 선언 이름 및 데이터 형식을 지정 하는 프로시저에 대 한 각 매개 변수를 선언 합니다. 전달 메커니즘을 지정할 수도 및 매개 변수는 선택 사항입니다.  
  
 자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.  
  
### <a name="to-define-a-procedure-parameter"></a>프로시저 매개 변수를 정의 하려면  
  
1.  프로시저 선언에서 매개 변수 이름을 다른 매개 변수에서 쉼표로 구분 되는 프로시저의 매개 변수 목록에 추가 합니다.  
  
2.  매개 변수의 데이터 형식을 결정 합니다.  
  
3.  매개 변수 이름 뒤에 `As` 절 데이터 형식을 지정 합니다.  
  
4.  매개 변수에 대해 사용할 전달 메커니즘을 결정 합니다. 일반적으로 프로시저에서 호출 코드의 해당 값을 변경할 수를 사용 하려는 경우가 아니면 값 매개 변수 전달.  
  
5.  매개 변수 이름 앞 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 전달 메커니즘을 지정 합니다. 자세한 내용은 참조 [차이점 사이의 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.  
  
6.  매개 변수가 선택적 이면 앞 전달 메커니즘 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 등호로 매개 변수 데이터 형식에 따라 (`=`) 및 기본 값입니다.  
  
     다음 예제에서는 정의의 개요는 `Sub` 세 개의 매개 변수가 있는 프로시저입니다. 처음 두 필요 하며 세 번째는 선택 사항입니다. 매개 변수 선언 매개 변수 목록에 쉼표로 구분 됩니다.  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     첫 번째 매개 변수가 허용는 `customer` 개체 및 `updateCustomer` 에 전달 된 변수를 직접 업데이트할 수 `c` 인수 전달 되기 때문에 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다. 프로시저 전달 되기 때문에 마지막 두 인수 값을 변경할 수 없습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.  
  
     호출 코드에 대 한 값을 제공 하지 않는 경우는 `level` 매개 변수, Visual Basic 설정 기본값인 0입니다.  
  
     형식 검사 스위치 하는 경우 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `Off`, `As` 매개 변수를 정의할 때 절은 선택 사항입니다. 그러나 하나의 매개 변수를 사용 하는 경우는 `As` 절을 모두 사용 해야 합니다. 형식 검사 스위치 이면 `On`, `As` 절은 모든 매개 변수 정의에 필요 합니다.  
  
     모든 프로그래밍 요소에 대 한 데이터 형식 지정 이라고 *강력한 형식 지정*합니다. 설정 하는 경우 `Option Strict On`, Visual Basic에서 강력한 형식 지정을 적용 합니다. 이 것이 좋습니다 이유는 다음과 같습니다.  
  
    -   변수 및 매개 변수에 대 한 IntelliSense 지원도를 수 있습니다. 그러면 코드에서 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.  
  
    -   컴파일러를 형식 검사를 수행할 수 있습니다. 이렇게 하면 catch 문을 오버플로와 같은 오류로 인해 런타임에 실패할 수 있습니다. 또한 지원 하지 않는 개체에 메서드 호출을 catch 합니다.  
  
    -   코드의 더 빠른 실행에서 발생합니다. 이 대 한 한 가지 이유는 경우 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않으면, Visual Basic 컴파일러 할당은 `Object` 유형입니다. 컴파일된 코드 사이 변환 해야 할 수 `Object` 및 다른 데이터 형식의 경우 성능이 떨어집니다.  
  
## <a name="see-also"></a>참고자료

 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [재귀 프로시저](./recursive-procedures.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)  
