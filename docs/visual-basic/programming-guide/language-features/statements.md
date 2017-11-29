---
title: "Visual Basic의 문"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 210637105e54244ba829dabd73feab0b43ec7c6c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="statements-in-visual-basic"></a>Visual Basic의 문
문 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 은 전체 명령입니다. 키워드, 연산자, 변수, 상수, 및 식을 포함할 수 있습니다. 각 문에 다음 범주 중 하나에 속합니다.  
  
-   **선언문**, 변수, 상수 또는 프로시저 이름을 지정 하 고 또한 데이터 형식을 지정할 수는 있습니다.  
  
-   **실행 가능 문은**, 동작 시작입니다. 이러한 문에 메서드 또는 함수를 호출할 수 있으며 반복 하거나 코드 블록에서 분기할 수 있습니다. 실행 가능 문은 포함 **대입문**, 변수 또는 상수 값 이나 식을 할당입니다.  
  
 이 항목에서는 각 범주에 설명 합니다. 또한이 항목에서는 한 줄에 여러 개의 문을 결합 하는 방법 및 여러 줄에는 문을 계속 하는 방법을 설명 합니다.  
  
## <a name="declaration-statements"></a>선언문  
 프로시저, 변수, 속성, 배열 및 상수를 정의 하 고 이름을 선언 문을 사용 합니다. 프로그래밍 요소를 선언 하면 해당 데이터 형식, 액세스 수준 및 범위 정의할 수 있습니다. 자세한 내용은 참조 [선언 요소의 특징](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.  
  
 다음 예제에서는 세 가지 선언을 포함합니다.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 첫 번째 선언 되는 `Sub` 문. 일치 하는 해당 함께 `End Sub` 라는 프로시저를 선언 문에서 `applyFormat`합니다. 도 지정 하는 `applyFormat` 은 `Public`, 변수를 참조할 수 있는 모든 코드에서 호출할 수 있음을 의미 합니다.  
  
 두 번째 선언이 `Const` 상수를 선언 하는 문에 `limit`을 지정 하는 `Integer` 데이터 형식 및 값 33입니다.  
  
 세 번째 선언 되는 `Dim` 변수를 선언 하는 문에 `thisWidget`합니다. 데이터 형식이 특정 개체, 즉에서 생성 된 개체는 `Widget` 클래스입니다. 사용 하는 응용 프로그램에 노출 되는 모든 개체 유형일 또는 모든 기본 데이터 형식의 변수를 선언할 수 있습니다.  
  
### <a name="initial-values"></a>초기 값  
 선언문을 포함 하는 코드를 실행 하는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 선언된 된 요소에 필요한 메모리를 예약 합니다. 요소는 값이 있는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 해당 데이터 형식의 기본값으로 초기화 합니다. 자세한 내용은의 "동작" 참조 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
 다음 예제와 같이 해당 선언의 일부로 변수에 초기 값을 할당할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 변수는 개체 변수를 명시적으로 만들면 해당 클래스의 인스턴스를 사용 하 여 선언 하는 경우는 [New 연산자](../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 다음 예제와 같이 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 실행 선언 문 도달 하기 전까지 선언문에 사용자가 지정한 초기 값을 변수에 할당 되지은 note 합니다. 그 전 까지는 변수 데이터 형식에 대 한 기본값을 포함 합니다.  
  
## <a name="executable-statements"></a>실행문  
 실행 가능 문이 동작을 수행 합니다. 식을 계산 하거나 여러 문 순환 코드에서 다른 위치로 분기는 프로시저를 호출할 수 있습니다. 대입문은 실행 가능 문의 특별 한 경우.  
  
 다음 예제에서는 `If...Then...Else` 변수 값에 따라 코드의 서로 다른 블록을 실행 하는 구조를 제어 합니다. 코드의 각 블록 내에서 한 `For...Next` 루프는 지정 된 횟수 만큼 실행 합니다.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 `If` 매개 변수의 값을 확인 하는 문 앞의 예에서 `clockwise`합니다. 값이 `True`를 호출 하는 `spinClockwise` 방식의 `aWidget`합니다. 값이 `False`를 호출 하는 `spinCounterClockwise` 방식의 `aWidget`합니다. `If...Then...Else` 제어 구조로 끝나는 `End If`합니다.  
  
 `For...Next` 각 블록 내에서 루프 메서드를 호출 하는 적절 한 횟수 만큼의 값과 같은 `revolutions` 매개 변수입니다.  
  
## <a name="assignment-statements"></a>대입문  
 대입문의 할당 연산자의 오른쪽에 값으로 구성 된 할당 연산을 수행 (`=`) 다음 예제와 같이 왼쪽의 요소에 저장 합니다.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 할당 문은 앞의 예제에서 변수의 리터럴 값 42를 저장 `v`합니다.  
  
### <a name="eligible-programming-elements"></a>적용 가능한 프로그래밍 요소  
 할당 연산자의 왼쪽에 있는 프로그래밍 요소를 받아들이고 값을 저장할 수 있어야 합니다. 즉, 변수 또는 아닌 속성 이어야 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), 이거나 배열 요소 이어야 합니다. 대입문의 컨텍스트에서 이러한 요소 라고도 *lvalue*, "왼쪽 값입니다."  
  
 할당 연산자의 우변에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소, 다른 식 또는 함수 호출의 조합으로 구성 될 수 있는 식에 의해 생성 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 위의 예제에서는 변수에 저장 된 값 `y` 변수에 저장 된 값에 `z`, 다음 함수 호출에서 반환 된 값을 추가 하 고 `findResult`합니다. 이 식의 합계 값은 변수에 저장 된 다음 `x`합니다.  
  
### <a name="data-types-in-assignment-statements"></a>대입문의 데이터 형식  
 숫자 값 뿐만 아니라 대입 연산자 할당할 수도 `String` 다음 예제와 같이 값입니다.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 할당할 수도 있습니다 `Boolean` 중 하나를 사용 하 여 값을 `Boolean` 리터럴 또는 `Boolean` 식은 다음 예제와 같이 설명 합니다.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 마찬가지로, 프로그래밍 요소와의 적절 한 값을 할당할 수 있습니다는 `Char`, `Date`, 또는 `Object` 데이터 형식입니다. 또한 해당 인스턴스에서 생성 되는 클래스에 선언 된 요소를 개체 인스턴스를 할당할 수 있습니다.  
  
### <a name="compound-assignment-statements"></a>복합 대입문  
 *복합 대입문* 먼저 프로그래밍 요소에 할당 하기 전에 식에 대 한 작업을 수행 합니다. 다음 예제에서는 다음이 연산자 중 하나 `+=`, 오른쪽에 있는 식의 값으로 연산자의 좌 변에 있는 변수의 값이 증가입니다.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 위 예의 값에 1을 추가 `n`, 다음에 새 값을 저장 하 고 `n`합니다. 이것은 다음 문과 동일 합니다.  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 이러한 종류의 연산자를 사용 하 여 다양 한 복합 할당 작업을 수행할 수 있습니다. 목록과 이러한 연산자에 대 한 자세한 내용은 참조 하십시오. [대입 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)합니다.  
  
 연결 할당 연산자 (`&=`)은 이미 존재 하는의 끝에 문자열을 추가 하는 데 유용 다음 예제와 같이 문자열입니다.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>대입문의 형식 변환  
 해당 대상 요소에 적절 한 데이터 형식의 변수, 속성 또는 배열 요소에 할당 하는 값 이어야 합니다. 일반적으로 대상 요소의 것과 동일한 데이터 형식의 값을 생성 하려고 해야 합니다. 그러나 할당 하는 동안 일부 형식은 다른 형식으로 변환 수 있습니다.  
  
 데이터 형식 간의 변환에 대 한 참조 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)합니다. 간단히 말해서 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 자동으로 지정 된 형식의 값으로 확대 다른 형식으로 변환 합니다. A *확대 변환* 는 주는 하나 항상 런타임에 성공 하 고 데이터가 손실 되지 않습니다. 예를 들어 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 변환는 `Integer` 값을 `Double` 해당 되는 경우 때문에 `Integer` 로 확대 `Double`합니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.  
  
 *축소 변환* (확대 되지 것) 런타임 시 오류 또는 데이터 손실의 위험을 수행 합니다. 형식 변환 함수를 사용 하 여 명시적으로 축소 변환을 수행 하거나 변환을 수행 하기 위해 모든 암시적으로 설정 하 여 컴파일러에 지시할 수 있습니다 `Option Strict Off`합니다. 자세한 내용은 참조 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)합니다.  
  
## <a name="putting-multiple-statements-on-one-line"></a>여러 개의 문을 한 줄에 배치 하는  
 콜론으로 구분 된 한 줄에 여러 개의 문을 포함할 수 있습니다 (`:`) 문자. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 편리할 때도 있지만이 형식의 구문 사용 하면 코드 읽고 유지 관리 하기가 어렵습니다. 따라서 하나의 문으로 한 줄으로 유지 하는 것이 좋습니다.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>여러 줄에 하나의 문 계속  
 문을 한 줄에 일반적으로 적합 하지만 너무 길면 공백, 밑줄 문자 순으로 구성 되는 줄 연속 시퀀스를 사용 하 여 다음 줄으로 계속 수 (`_`) 뒤에 캐리지 리턴입니다. 다음 예제에서는 `MsgBox` 실행 문은 두 줄에 걸쳐 계속 됩니다.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>암시적 줄 연속  
 대부분의 경우에서 밑줄 문자 (_)을 사용 하지 않고 연속 된 다음 줄을 문을 계속할 수 있습니다. 다음 표에서 코드의 다음 줄에서 문을 암시적으로 계속 하는 구문 요소를 나열 합니다.  
  
|구문 요소|예제|  
|---|---|  
|쉼표 뒤 (`,`).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|여는 괄호 뒤 (`(`) 또는 닫는 괄호 앞 (`)`).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|중괄호 뒤 (`{`) 또는 닫는 중괄호 앞 (`}`).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> 자세한 내용은 참조 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)합니다.|  
|열린 후 포함 식 (`<%=`) 또는 그 포함된 식 닫기 전에 (`%>`) XML 리터럴 내에서.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> 자세한 내용은 참조 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.|  
|연결 연산자 후 (`&`).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> 자세한 내용은 참조 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.|  
|대입 연산자 후 (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> 자세한 내용은 참조 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.|  
|이항 연산자 한 후 (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) 식입니다.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> 자세한 내용은 참조 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.|  
|이후에 `Is` 및 `IsNot` 연산자입니다.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> 자세한 내용은 참조 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.|  
|멤버 한정자 문자 후 (`.`) 및 멤버 이름 앞입니다. 하지만 사용 하는 경우 멤버 한정자 문자 뒤에 줄 연속 문자 (_)을 포함 해야는 `With` 문 또는 유형에 대 한 초기화 목록에서 값을 제공 합니다. 대입 연산자 뒤에서 줄 바꿈 하는 것이 좋습니다. (예를 들어 `=`) 사용 하는 `With` 문 또는 개체 초기화 목록입니다.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> 자세한 내용은 참조 [와... 문을 사용 하 여 종료](../../../visual-basic/language-reference/statements/with-end-with-statement.md) 또는 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.|  
|XML 축 속성 한정자 후 (`.` 또는 `.@` 또는 `...`). 하지만 사용 하는 경우 멤버 한정자를 지정 하면 줄 연속 문자 (_)을 포함 해야는 `With` 키워드입니다.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> 자세한 내용은 참조 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)합니다.|  
|작음-보다 작다 (<) 또는 이전 큼-보다 작다 (`>`) 특성을 지정 하는 경우. 뒤에 큼-보다 작다 (`>`) 특성을 지정 하는 경우. 그러나 어셈블리 수준 또는 모듈 수준 특성을 지정 하면 줄 연속 문자 (_)을 포함 해야 합니다.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> 자세한 내용은 참조 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다.|  
|쿼리 연산자 앞뒤 (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, 및 `Descending`). 여러 키워드 이루어진 하는 쿼리 연산자 키워드 사이 선을 중단 될 수 없습니다 (`Order By`, `Group Join`, `Take While`, 및 `Skip While`).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> 자세한 내용은 참조 [쿼리](../../../visual-basic/language-reference/queries/queries.md)합니다.|  
|후의 `In` 키워드는 `For Each` 문.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> 자세한 내용은 참조 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.|  
|후의 `From` 컬렉션 이니셜라이저에는 키워드입니다.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> 자세한 내용은 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하세요.|  
  
## <a name="adding-comments"></a>주석 추가  
 소스 코드는 항상 자체 것은 프로그래머에 게도 설명 합니다. 따라서 코드를 문서화할를 하기 위해 대부분의 프로그래머가 쉽게가 포함 되어 있는 설명 자유롭게 사용 하 여를 확인 합니다. 코드의 주석 프로시저 또는 특정 명령을 읽거나 작업을 나중에 모든 사용자에 게 설명할 수 있습니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]컴파일하는 동안 주석을 무시는 컴파일된 코드가 영향을 주지 않습니다.  
  
 아포스트로피로 주석 줄 시작 (`'`) 또는 `REM` 뒤에 공백이 있습니다. 추가할 수 있습니다 아무 곳 이나 코드에서 제외 하 고 문자열 내에서. 문에 주석을 추가할 아포스트로피 삽입 또는 `REM` 주석 뒤 문 다음 합니다. 별도 줄에 주석을 수행할 수도 있습니다. 다음 예제에서는 이러한 가능성을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>컴파일 오류를 확인 하는 중  
 코드 줄을 입력 한 후 줄 됩니다 (오류 메시지가 나타날 수 있음) 파란색 물결 무늬 밑줄로 표시 되 면, 문에 구문 오류가 있습니다. 무엇 인지 확인 문을 사용 하 여 잘못 된 (하 여 작업 목록에서 또는 마우스 포인터를 오류를 마우스로 가리킬 기록 된 오류 메시지)를 수정 하십시오. 코드에서 모든 구문 오류를 수정 하기 전에 올바르게 컴파일하기 위해 프로그램 실패 합니다.  
  
## <a name="related-sections"></a>관련 단원  
  
|용어|정의|  
|---|---|  
|[할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)|언어 참조 페이지와 같은 할당 연산자를 다루는 링크를 제공 `=`, `*=`, 및 `&=`합니다.|  
|[연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|새 값을 산출 하는 연산자가 있는 요소를 결합 하는 방법을 보여 줍니다.|  
|[방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|단일 문에 여러 선으로 분할 하는 방법과 같은 줄에 여러 개의 문을 배치 하는 방법을 보여 줍니다.|  
|[방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|코드의 줄에 레이블을 지정 하는 방법을 보여 줍니다.|
