---
title: 프로시저 문제 해결(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: f66e7f7444f2d3b1bb58bae6008f8896c81c2f76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-procedures-visual-basic"></a>프로시저 문제 해결(Visual Basic)
이 페이지는 프로시저를 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Function 프로시저에서 배열 형식 반환  
 경우는 `Function` 프로시저가 반환 배열 데이터 형식, 사용할 수 없습니다는 `Function` 이름 배열의 요소에 값을 저장 합니다. 이 작업을 수행 하려고 하면 컴파일러로 해석에 대 한 호출에서 `Function`합니다. 다음 예제에서는 컴파일러 오류가 생성 됩니다.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 문이 `allOnes(i) = 1` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 의 데이터 형식이 잘못 된 인수가 지정 된 (단일 `Integer` 대신는 `Integer` 배열)입니다. 문이 `Return allOnes()` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 인수가 없는 합니다.  
  
 **올바른 방법은:** 반환 되는 배열의 요소를 수정할 수 있으려면 내부 배열 지역 변수로 정의 합니다. 다음 예제에서는 오류 없이 컴파일합니다.  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>수정 되지 인수 프로시저 호출으로  
 호출 코드의 기반이 되는 프로그래밍 요소를 변경 하는 절차를 허용 하려는 경우 참조로 전달 해야 합니다. 하지만 값으로 전달 하는 경우에 프로시저 참조 형식 인수 요소에 액세스할 수 있습니다.  
  
-   **내부 변수**합니다. 프로시저는 내부 변수 요소의 값을 대체 하는 절차를 허용 하려면 매개 변수를 선언 해야 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다. 또한 호출 하는 코드 묶지 마십시오 인수에 있는 괄호 안에 재정의 되기 때문에 `ByRef` 전달 메커니즘입니다.  
  
-   **형식 요소 참조**합니다. 매개 변수를 선언 하는 경우 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), 프로시저는 내부 변수 요소를 수정할 수 없습니다. 그러나 인수 참조 형식인 경우 변수의 값을 바꿀 수 없습니다 없지만 프로시저 가리키는, 개체의 멤버를 수정할 수 있습니다. 예를 들어 인수는 배열 변수, 프로시저, 새 배열을 할당할 수 없습니다 하지만 해당 요소 중 하나 이상을 변경할 수는 있습니다. 변경 된 요소에서 호출 코드의 내부 배열 변수에 반영 됩니다.  
  
 다음 예제에서는 요소를 값으로 배열 변수를 받아을 작업을 수행 하는 두 가지 절차를 정의 합니다. 프로시저 `increase` 각 요소에 1을 더 합니다. 프로시저 `replace` 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 1을 추가 합니다. 그러나 캡처하기 영향을 주지 않습니다 호출 코드의 내부 배열 변수 이므로 `a()` 선언 `ByVal`합니다.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 다음 예제에 대 한 호출에서는 `increase` 및 `replace`합니다.  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다. 때문에 `n` 참조 형식인 `increase` 전달 되는 경우에 해당 멤버를 변경할 수 `ByVal`합니다.  
  
 두 번째 `MsgBox` 표시 호출 "replace(n) 후: 11, 21, 31, 41"입니다. 때문에 `n` 전달 `ByVal`, `replace` 변수를 수정할 수 없습니다 `n` 새 배열을 할당 하 여 합니다. 때 `replace` 배열의 새 인스턴스를 만듭니다. `k` 로컬 변수에 할당 하 고 `a`에 대 한 참조를 잃을 `n` 호출 코드에 의해 전달 된입니다. 멤버를 늘리면 `a`, 지역 배열만 `k` 영향을 받습니다.  
  
 **올바른 방법은:** 자체는 내부 변수 요소를 수정할 수 있으려면 참조로 전달 합니다. 다음 예제에서는 선언에 변화를 보여 줍니다. `replace` 배열로 ब द ल 호출 코드로 바꾸는 것을 허용 하 합니다.  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>오버 로드를 정의할 수 없습니다.  
 프로시저의 오버 로드 된 버전을 정의 하려는 경우에 같지만 시그니처를 다르게 동일한 이름을 사용 해야 합니다. 컴파일러는 동일한 서명으로 오버 로드에서 선언 구분할 수 없습니다, 하는 경우 오류가 생성 됩니다.  
  
 *서명* 프로시저의 프로시저 이름과 매개 변수 목록에 의해 결정 됩니다. 각 오버 로드는 다른 모든 오버 로드와 동일한 이름이 해야 하지만 서명의 다른 구성 요소 중 하나 이상 있는 모든 대상에서 달라 야 합니다. 자세한 내용은 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.  
  
 다음 항목을 매개 변수 목록에 포함 되어 있더라도 없는 프로시저의 서명의 구성 요소:  
  
-   프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및 `Static`  
  
-   매개 변수 이름  
  
-   매개 변수 한정자 키워드와 같은 `ByRef` 및 `Optional`  
  
-   반환 값 (변환 연산자 제외)의 데이터 형식  
  
 하나 이상의 이전 항목만 변경 하 여 프로시저를 오버 로드할 수 없습니다.  
  
 **올바른 방법은:** 프로시저 오버 로드를 정의할 수 있으려면 시그니처를 다르게 지정 해야 합니다. 이름이 같은 사용 해야 하므로 번호, 순서 또는 데이터 유형의 매개 변수 달라 집니다. 제네릭 프로시저가 형식 매개 변수 수를 변경할 수 있습니다. 변환 연산자에서 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 반환 형식을 변경할 수 있습니다.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적으로 확인 및 ParamArray 인수 오버 로드  
 하나 이상의 프로시저 오버 로드 된 경우 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 중 하나를 중복을 피해 야 할는 *암시적 오버 로드*합니다. 자세한 내용은 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>잘못 된 버전의 오버 로드 된 프로시저를 호출합니다.  
 프로시저에 있는 여러 오버 로드 된 버전을 모든 매개 변수 목록은 잘 알고 있어야 하 고 Visual Basic에서 오버 로드 간의 호출을 확인 하는 방법을 이해 해야 합니다. 그렇지 않은 경우 원하지 않은 오버 로드를 호출할 수 있습니다.  
  
 호출 하려는 오버 로드를 확인 한 다음 규칙을 준수 해야:  
  
-   올바른 수의 인수를 올바른 순서로 제공 합니다.  
  
-   이상적으로 인수가 정확히 동일한 데이터 형식을 해당 매개 변수의 있어야 합니다. 어떤 경우 든, 각 인수의 데이터 형식을 해당 매개 변수를 확장 해야 합니다. 된 경우에 마찬가지입니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 로 설정 `Off`합니다. 오버 로드는 인수 목록에서의 축소 변환이 필요한 호출할 수는 있습니다.  
  
-   확대 변환에 필요한 인수를 제공 하는 경우 해당 데이터 형식이 해당 매개 변수 데이터 형식에 최대한 가까운를 확인 합니다. 두 개 이상의 오버 로드는 인수 데이터 형식과 수락 컴파일러가 확대 변환 부분이 가장 적은 호출 하는 오버 로드를 호출 하 여 해결 합니다.  
  
 사용 하 여 데이터 형식 불일치 가능성을 줄일 수는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 인수를 준비할 때 변환 키워드입니다.  
  
### <a name="overload-resolution-failure"></a>오버 로드 확인 실패  
 오버 로드 된 프로시저를 호출 하면 컴파일러에서 오버 로드 중 하나만 남기고 모두 제거 하려고 합니다. 성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다. 모든 오버 로드를 제거 하거나 단일 후보 오버 로드가 줄일 수 없을 경우 오류가 생성 됩니다.  
  
 다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 첫 번째 호출에서 컴파일러는 첫 번째 오버 로드를 제거 하기 때문에 첫 번째 인수의 형식 (`Short`) 해당 매개 변수의 형식으로 축소 (`Byte`). 두 번째 오버 로드에 각 인수를 입력 하기 때문에 다음 세 번째 오버 로드를 제거 (`Short` 및 `Single`) 세 번째 오버 로드에서 해당 형식으로 확장 되는지를 (`Integer` 및 `Single`). 두 번째 오버 로드 컴파일러 호출에 사용 되므로 적은 확대 필요 합니다.  
  
 두 번째 호출에서 컴파일러 축소 변환을 기반으로 오버 로드를 제거할 수 없습니다. 적은 확대 인수 형식의 두 번째 오버 로드를 호출할 수 있으므로 첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다. 그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 간의 확인할 수 없습니다. 각각 다른의 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식을 갖는 (`Byte` 를 `Short`, 하지만 `Single` 를 `Double`). 따라서 컴파일러는 오버 로드 확인 오류를 생성합니다.  
  
 **올바른 방법은:** 를 명확 하 게 오버 로드 된 프로시저 호출을 사용 하 여 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 매개 변수 형식과 인수 데이터 형식과 일치 하도록 합니다. 다음 예제에 대 한 호출에서는 `z` 두 번째 오버 로드를 확인 하 게 하는 합니다.  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적으로 확인 및 ParamArray 인수 오버 로드  
 마지막 매개 변수가 선언 된 점을 제외 하 고 프로시저의 두 개의 오버 로드 시그니처가 같은 경우 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 하나 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 컴파일러 해당 프로시저에 대 한 호출을 해결 하 고 다른 일치 하는 가장 가까운 항목을 기준으로 합니다. 자세한 내용은 참조 [오버 로드 확인](./overload-resolution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)  
 [오버로드 확인](./overload-resolution.md)
