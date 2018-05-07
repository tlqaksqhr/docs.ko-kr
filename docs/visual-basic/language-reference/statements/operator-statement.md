---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="operator-statement"></a>Operator Statement
연산자 기호, 피연산자의 경우 클래스 또는 구조체에서 연산자 프로시저를 정의 하는 코드를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>요소  
 `attrlist`  
 선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
 `Public`  
 필수. 이 연산자 프로시저에 있음을 나타냅니다 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다.  
  
 `Overloads`  
 선택 사항입니다. 참조 [오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)합니다.  
  
 `Shared`  
 필수. 이 연산자 프로시저 임을 나타냅니다는 [Shared](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저입니다.  
  
 `Shadows`  
 선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
 `Widening`  
 지정 하지 않으면 변환 연산자에 필요한 `Narrowing`합니다. 이 연산자 프로시저를 정의 함을 나타냅니다는 [Widening](../../../visual-basic/language-reference/modifiers/widening.md) 변환 합니다. 이 도움말 페이지에 "확대 변환과 축소 변환"를 참조 하십시오.  
  
 `Narrowing`  
 지정 하지 않으면 변환 연산자에 필요한 `Widening`합니다. 이 연산자 프로시저를 정의 함을 나타냅니다는 [문제의 범위 제한](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환 합니다. 이 도움말 페이지에 "확대 변환과 축소 변환"를 참조 하십시오.  
  
 `operatorsymbol`  
 필수. 기호 또는이 연산자 프로시저가 정의 하는 연산자의 식별자입니다.  
  
 `operand1`  
 필수. 이름 및 단항 연산자 (변환 연산자 포함)의 단일 피연산자 또는 이항 연산자의 왼쪽된 피연산자의 형식입니다.  
  
 `operand2`  
 이항 연산자에 필요합니다. 이름과 이항 연산자의 오른쪽 피연산자의 형식입니다.  
  
 `operand1` 및 `operand2` 다음과 같은 구문과 요소가 있어야 합니다.  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|파트|설명|  
|----------|-----------------|  
|`ByVal`|선택 사항 이지만 전달 메커니즘 해야 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.|  
|`operandname`|필수. 이 피연산자를 나타내는 변수의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`operandtype`|선택적 하지 않는 한 `Option Strict` 은 `On`합니다. 이 피연산자의 데이터 형식입니다.|  
  
 `type`  
 선택적 하지 않는 한 `Option Strict` 은 `On`합니다. 연산자 프로시저 값의 데이터 형식을 반환합니다.  
  
 `statements`  
 선택 사항입니다. 연산자 프로시저를 실행 하는 문 블록입니다.  
  
 `returnvalue`  
 필수. 연산자 프로시저 호출 코드에 반환 하는 값입니다.  
  
 `End` `Operator`  
 필수. 이 연산자 프로시저의 정의 종료합니다.  
  
## <a name="remarks"></a>설명  
 사용할 수 있습니다 `Operator` 클래스 또는 구조체에만 합니다. 즉,는 *선언 컨텍스트* 연산자 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 차단 될 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 모든 연산자는 반드시 `Public Shared`합니다. 지정할 수 없으며 `ByRef`, `Optional`, 또는 `ParamArray` 피연산자에 대 한 합니다.  
  
 연산자 기호 또는 식별자를 사용 하 여 반환 값을 보유할 수 없습니다. 사용 해야 합니다는 `Return` 문 및 해당 값을 지정 해야 합니다. 개수에 관계 없이 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있습니다.  
  
 이러한 방식으로 연산자 정의 라고 *연산자 오버 로드*사용 여부는 `Overloads` 키워드입니다. 다음 표에는 정의할 수 있는 연산자가 나와 있습니다.  
  
|형식|연산자|  
|----------|---------------|  
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|이항|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|변환(단항)|`CType`|  
  
 `=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.  
  
 정의 하는 경우 `CType`를 지정 해야 `Widening` 또는 `Narrowing`합니다.  
  
## <a name="matched-pairs"></a>일치 하는 쌍  
 일치 하는 쌍으로 특정 연산자를 정의 해야 합니다. 이러한 쌍의 연산자 중 하나를 정의 하는 경우 다른도 정의 해야 합니다. 일치 하는 쌍은 다음과 같습니다.  
  
-   `=` 및 `<>`  
  
-   `>` 및 `<`  
  
-   `>=` 및 `<=`  
  
-   `IsTrue` 및 `IsFalse`  
  
## <a name="data-type-restrictions"></a>데이터 형식 제한 사항  
 정의한 모든 연산자는 클래스 또는 구조체 정의에 참여 해야 합니다. 즉, 클래스 또는 구조체는 다음의 데이터 형식으로 나타나야 합니다.  
  
-   단항 연산자의 피연산자입니다.  
  
-   적어도 하나는 이항 연산자의 피연산자의입니다.  
  
-   피연산자 또는 변환 연산자의 반환 형식입니다.  
  
 특정 연산자는 제한 사항에 다음과 같이 입력 하는 추가 데이터:  
  
-   정의 하는 경우는 `IsTrue` 및 `IsFalse` 연산자를 반환 해야 하므로 둘 다는 `Boolean` 유형입니다.  
  
-   정의 하는 경우는 `<<` 및 `>>` 연산자를 둘 다 지정 해야는 `Integer` 에 대 한 입력은 `operandtype` 의 `operand2`합니다.  
  
 반환 형식은 피연산자 중 하나가 형식에 해당 필요가 없습니다. 예를 들어과 같은 비교 연산자 `=` 또는 `<>` 반환할 수 `Boolean` 두 피연산자 모두 경우에 `Boolean`합니다.  
  
## <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자  
 `And`, `Or`, `Not`, 및 `Xor` 연산자 Visual Basic의 논리적 또는 비트 작업을 수행할 수 있습니다. 그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우에 비트 연산만 정의할 수 있습니다.  
  
 정의할 수 없습니다는 `AndAlso` 와 직접 연산자는 `Operator` 문. 사용할 수 있습니다 `AndAlso` 다음 조건을 충족 하는 경우:  
  
-   정의한 `And` 동일한 피연산자 형식에 대 한 사용 하려는에 `AndAlso`합니다.  
  
-   정의 `And` 에 정의한 클래스 또는 구조체와 동일한 형식을 반환 합니다.  
  
-   정의한는 `IsFalse` 에 정의한 클래스 또는 구조체에서 연산자 `And`합니다.  
  
 마찬가지로, 사용할 수 있습니다 `OrElse` 정의한 경우 `Or` 동일한 피연산자에는 클래스 또는 구조체의 반환 형식을 갖는 정의한 `IsTrue` 클래스 또는 구조체에서 합니다.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 A *확대 변환* 런타임 시 항상 성공 하는 동안는 *축소 변환* 런타임 시 실패할 수 있습니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.  
  
 변환 프로시저를 선언 하는 경우 `Widening`, 프로시저 코드가 발생 한 모든 오류를 생성 하지 해야 합니다. 이것은 다음을 의미합니다.  
  
-   형식의 올바른 값을 항상 반환 해야 `type`합니다.  
  
-   모든 가능한 예외 및 기타 오류 조건 처리 해야 합니다.  
  
-   호출 하는 프로시저의 모든 오류 반환을 처리 해야 합니다.  
  
 으로 선언 해야에서 처리 되지 않은 예외가 발생 한다는 변환 프로시저 성공 하지 못할 수 있는 가능성이 있는 경우 `Narrowing`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Operator` 연산자 프로시저를 포함 하는 구조 윤곽선을 정의 하는 문에 `And`, `Or`, `IsFalse`, 및 `IsTrue` 연산자입니다. `And` 및 `Or` 형식의 두 개의 피연산자 `abc` 및 반환 형식을 `abc`합니다. `IsFalse` 및 `IsTrue` 형식의 단일 피연산자를 각각 사용 `abc` 다음 다시 돌아와 `Boolean`합니다. 이러한 정의 사용 하도록 호출 코드를 사용 합니다. `And`, `AndAlso`, `Or`, 및 `OrElse` 형식의 피연산자와 함께 `abc`합니다.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [확장](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [방법: 연산자 프로시저 호출](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [방법: 연산자를 정의하는 클래스 사용](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
