---
title: "프로시저 문제 해결 (Visual Basic) | Microsoft 문서"
ms.custom: 
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
- troubleshooting Visual Basic, procedures
- procedures, troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures, about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
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
ms.openlocfilehash: a5445d6da982e4eea5b1047505e4bee3380ed472
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-procedures-visual-basic"></a>프로시저 문제 해결(Visual Basic)
이 페이지는 프로시저를 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Function 프로시저에서 배열 형식 반환  
 하는 경우는 `Function` 프로시저가 배열 데이터 형식 반환, 사용할 수 없습니다는 `Function` 이름 배열 요소에 값을 저장 합니다. 이 작업을 수행 하려고 하면 컴파일러로 해석에 대 한 호출에서 `Function`합니다. 다음 예제에서는 컴파일러 오류가 생성 됩니다.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 문이 `allOnes(i) = 1` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 의 데이터 형식이 잘못 된 인수가 지정 된 (단일 `Integer` 대신는 `Integer` 배열)입니다. 문이 `Return allOnes()` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 인수가 있습니다.  
  
 **올바른 방법:** 반환 되는 배열의 요소를 수정할 수 있게 되기를 내부 배열을 지역 변수로 정의 합니다. 다음 예제에서는 오류 없이 컴파일합니다.  
  
 [!code-vb[VbVbcnProcedures #&66;](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>인수를 수정 하지 못하도록 프로시저 호출에서  
 호출 코드에서 인수를 기본 프로그래밍 요소를 변경 하는 절차를 허용 하려는 경우 참조로 전달 해야 합니다. 하지만 값으로 전달 하는 경우에 프로시저의 인수는 참조 형식 요소에 액세스할 수 있습니다.  
  
-   **내부 변수**합니다. 프로시저는 내부 변수 요소의 값을 대체 하는 절차를 허용 하려면 매개 변수를 선언 해야 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다. 또한 호출 코드 묶지 마십시오 인수를 괄호로 재정의 되기 때문에 `ByRef` 전달 메커니즘입니다.  
  
-   **참조 형식 요소**합니다. 매개 변수를 선언 하는 경우 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), 프로시저 자체 내부 변수 요소를 수정할 수 없습니다. 그러나 인수가 참조 형식, 변수 값을 바꿀 수 없습니다 없지만 프로시저 가리키는, 개체의 멤버를 수정할 수 있습니다. 예를 들어 인수가 배열 변수, 프로시저, 새 배열을 할당할 수 없지만 해당 요소 중 하나 이상을 변경할 수 있습니다. 변경 된 요소는 호출 코드의 내부 배열 변수에 반영 됩니다.  
  
 다음 예제에서는 요소를 값으로는 배열 변수를 받아 및 작동 하는 두 가지 절차를 정의 합니다. 프로시저 `increase` 각 요소에&1;을 더 합니다. 프로시저 `replace` 매개 변수에 새 배열을 할당 `a()` 다음 각 요소에&1;을 추가 합니다. 그러나 다시 할당 영향을 주지 않습니다 호출 코드의 내부 배열 변수 때문에 `a()` 선언 `ByVal`합니다.  
  
 [!code-vb[VbVbcnProcedures #&35;](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures #&38;](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 다음 예제에서는에 대 한 호출 `increase` 및 `replace`합니다.  
  
 [!code-vb[VbVbcnProcedures #&37;](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다. 때문에 `n` 참조 형식인 `increase` 전달 되는 경우에 해당 멤버를 변경할 수 `ByVal`합니다.  
  
 두 번째 `MsgBox` 표시 호출 "replace(n) 후: 11, 21, 31, 41"입니다. 때문에 `n` 전달 `ByVal`, `replace` 변수를 수정할 수 없습니다 `n` 새 배열에 할당 하 여 합니다. 때 `replace` 새 배열 인스턴스를 만듭니다 `k` 로컬 변수에 할당 하 고 `a`에 대 한 참조를 잃을 `n` 는 호출 코드에 의해 전달 된 합니다. 멤버를 늘리면 `a`, 지역 배열만 `k` 영향을 받습니다.  
  
 **올바른 방법:** 자체 내부 변수 요소를 수정할 수, 참조로 전달 합니다. 다음 예제에서는 선언에 변경 내용을 보여 줍니다. `replace` 호출 코드에서 다른 한 배열을 교체할 수 있도록 합니다.  
  
 [!code-vb[VbVbcnProcedures #&64;](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>오버 로드를 정의할 수 없습니다.  
 프로시저의 오버 로드 된 버전을 정의 하려는 경우 다른 서명 하지만 같은 이름을 사용 해야 합니다. 컴파일러는 동일한 시그니처를 가진 오버 로드에서 선언을 구분할 수 없습니다, 경우에 오류가 발생 합니다.  
  
 *서명* 프로시저는 프로시저 이름 및 매개 변수 목록에 의해 결정 됩니다. 각 오버 로드는 다른 모든 오버 로드와 같은 이름을 하지만 모든 서명의 다른 구성 요소 중 하나 이상이 달라 야 합니다. 자세한 내용은 참조 [프로시저 오버 로딩](./procedure-overloading.md)합니다.  
  
 다음 항목을 매개 변수 목록에 포함 되어 있더라도 없는 프로시저의 서명의 구성 요소:  
  
-   프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및`Static`  
  
-   매개 변수 이름  
  
-   매개 변수 한정자 키워드와 같은 `ByRef` 및`Optional`  
  
-   반환 값 (변환 연산자 제외)의 데이터 형식  
  
 위의 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.  
  
 **올바른 방법:** 프로시저 오버 로드를 정의할 수, 시그니처를 다르게 지정 해야 합니다. 이름이 같은 사용 해야 하므로 번호, 주문 또는 매개 변수 데이터 형식이 달라 집니다. 제네릭 프로시저에서 형식 매개 변수의 수를 변경할 수 있습니다. 변환 연산자에서 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 반환 형식을 변경할 수 있습니다.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적 확인과 ParamArray 인수 오버 로드  
 하나 이상의와 프로시저를 오버 로드 된 경우 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 중 하나를 중복을 피해 야 할는 *암시적 오버 로드*합니다. 내용은 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>잘못 된 버전의 오버 로드 된 프로시저를 호출합니다.  
 모든 매개 변수 목록은 잘 알고 있어야 하 고 이해 해야는 프로시저 오버 로드 된 버전을 여러 개 있으면 어떻게 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 오버 로드 간의 호출을 확인 합니다. 그렇지 않으면 의도 한 다른 오버 로드를 호출할 수 있습니다.  
  
 오버 로드를 호출 하려는 결정 하는 경우 주의 다음 규칙을 준수 하십시오.  
  
-   인수를 올바른 순서로 정확한 수를 제공 합니다.  
  
-   이상적으로 인수에 해당 매개 변수는 정확히 동일한 데이터 형식이 있어야 합니다. 어떤 경우 든 각 인수의 데이터 형식을 해당 매개 변수의으로 확대 변환 되어야 합니다. 있는 경우에 그렇습니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 로 설정 `Off`합니다. 오버 로드를 오버 로드 하면 인수 목록에서 축소 변환이 필요한 경우 호출할 수는 있습니다.  
  
-   확대 변환이 필요한 인수를 제공 하는 경우 해당 매개 변수 데이터 형식에 최대한 가깝게 데이터 형식으로 확인 합니다. 인수 데이터 형식을 허용 하는 두 개 이상의 오버 로드를 컴파일러에 최소한의 확장에 대 한 호출 하는 오버 로드를 호출 하 여 해결 합니다.  
  
 사용 하 여 데이터 형식 불일치의 가능성을 줄일 수는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 인수를 준비할 때 변환 키워드입니다.  
  
### <a name="overload-resolution-failure"></a>오버 로드 확인 실패  
 오버 로드 된 프로시저를 호출 하면 컴파일러는 오버 로드 중 하나만 남기고 모두 제거 하려고 합니다. 성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다. 오버 로드를 모두 제거 하거나 단일 후보 오버 로드가 줄일 수 없을 경우 오류가 발생 합니다.  
  
 다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures #&62;](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures #&63;](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 첫 번째 호출에서는 컴파일러가 첫 번째 오버 로드를 제거 하기 때문에 첫 번째 인수의 형식 (`Short`) 해당 매개 변수 형식으로 축소 변환 (`Byte`). 두 번째 오버 로드의 각 인수 형식 때문에 다음 세 번째 오버 로드를 제거 (`Short` 및 `Single`) 세 번째 오버 로드에서 해당 형식으로 확장 되는지를 (`Integer` 및 `Single`). 두 번째 오버 로드는 덜 확대 해도 컴파일러 호출에 대 한 사용.  
  
 두 번째 호출에서 컴파일러 축소 변환을 기반으로 오버 로드를 제거할 수 없습니다. 인수 형식의 덜 확대 해도와 두 번째 오버 로드를 호출할 수 있으므로 첫 번째 호출에서와 같은 이유 때문에 세 번째 오버 로드를 제거 합니다. 그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 간의 확인할 수 없습니다. 각에 해당 하는 형식에서 다른 확장 되는 하나의 정의 된 매개 변수 형식의 (`Byte` 를 `Short`, 하지만 `Single` 를 `Double`). 따라서 컴파일러는 오버 로드 확인 오류를 생성합니다.  
  
 **올바른 방법:** 를 명확 하 게 오버 로드 된 프로시저 호출을 사용 하 여 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 인수 데이터 형식 매개 변수 형식에 일치 하도록 합니다. 다음 예제에서는에 대 한 호출 `z` 하는 두 번째 오버 로드를 확인 하 게 합니다.  
  
 [!code-vb[VbVbcnProcedures #&65;](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적 확인과 ParamArray 인수 오버 로드  
 마지막 매개 변수가 선언 된 점을 제외 하 고 프로시저의 두 개의 오버 로드가 시그니처가 같은 경우 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 하나 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 컴파일러는 다른 가장 일치에 따라 해당 프로시저에 대 한 호출을 확인 합니다. 자세한 내용은 참조 [오버 로드 확인](./overload-resolution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [Function 프로시저](./function-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)   
 [오버로드 확인](./overload-resolution.md)
