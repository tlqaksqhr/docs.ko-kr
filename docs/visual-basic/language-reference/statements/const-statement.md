---
title: Const 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: bb4c524fa5c29efbcbe485fb5e86c8cf0fa432e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="const-statement-visual-basic"></a>Const 문(Visual Basic)
선언 하 고 하나 이상의 상수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택 사항입니다. 이 문에서 선언 된 모든 상수에 적용 되는 특성의 목록입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
 `accessmodifier`  
 선택 사항입니다. 이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 사용 합니다. 수 [공용](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, 또는 [개인](../../../visual-basic/language-reference/modifiers/private.md)합니다.  
  
 `Shadows`  
 선택 사항입니다. 이 사용 하 여 다시 선언 하 고 기본 클래스에는 프로그래밍 요소를 숨길 수 있습니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
 `constantlist`  
 필수. 이 문에서 선언 되는 상수 목록입니다.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 각 `constant`에는 다음과 같은 구문과 요소가 있습니다.  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|파트|설명|  
|----------|-----------------|  
|`constantname`|필수. 상수의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`datatype`|필요한 경우 `Option Strict` 은 `On`합니다. 상수 데이터 형식입니다.|  
|`initializer`|필수. 컴파일 타임에 계산 되 고 상수에 할당 되는 식입니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에서 변경 되지 않는 값을 설정한 경우에 명명 된 상수를 정의 하 고 리터럴 값 대신 사용할 수 있습니다. 이름은 지정 된 값 보다 기억 하기 더 쉽습니다. 한 번만 상수를 정의 하 고 코드에서이 한 곳에 사용할 수 있습니다. 최신 버전에서 값을 다시 정의 해야 하는 경우는 `Const` 문을 변경 하려면 필요한 유일한 위치입니다.  
  
 사용할 수 있습니다 `Const` 모듈 또는 프로시저 수준 에서만. 즉,는 *선언 컨텍스트* 변수 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 소스 파일, 네임 스페이스 또는 인터페이스 일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 지역 상수 (내부의 프로시저의 경우) 기본적으로 공용 액세스에 액세스 한정자를 사용할 수 없습니다. 클래스 및 모듈 멤버 (프로시저) 외부 상수 기본적으로 개인 액세스 및 구조 멤버 상수 기본적으로 공용 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 모든 프로시저 외부의 모듈 수준에서 선언 된 상수는 *멤버 상수*; 클래스, 구조체의 멤버인 또는 선언 하는 모듈입니다.  
  
     프로시저 수준에서 선언 된 상수는 *지역 상수*; 지역적으로 선언 하는 블록 또는 프로시저일 설정 됩니다.  
  
-   **특성입니다.** 지역 상수 아니라 멤버 상수에만 특성을 적용할 수 있습니다. 특성은 지역 상수와 같은 임시 저장소에 의미가 없습니다 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.  
  
-   **한정자입니다.** 기본적으로 모든 상수는 `Shared`, `Static`, 및 `ReadOnly`합니다. 상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.  
  
     프로시저 수준에서 사용할 수 없습니다 `Shadows` 또는 액세스 한정자를 지역 상수 선언 합니다.  
  
-   **여러 상수입니다.** 동일한 선언문에서 여러 상수를 선언할 수를 지정 하는 `constantname` 각각에 대 한 부분입니다. 여러 상수는 쉼표로 구분 합니다.  
  
## <a name="data-type-rules"></a>데이터 형식 규칙  
  
-   **데이터 형식입니다.** `Const` 문은 변수의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식 또는 열거형의 이름을 지정할 수 있습니다.  
  
-   **기본 형식입니다.** 지정 하지 않으면 `datatype`, 상수의 데이터 형식은 `initializer`합니다. 모두 지정 하면 `datatype` 및 `initializer`의 데이터 형식이 `initializer` 변환할 수 있어야 `datatype`합니다. 모두 `datatype` 나 `initializer` 가 있는 경우 데이터 형식의 기본값으로 `Object`합니다.  
  
-   **다른 형식입니다.** 별도 사용 하 여 서로 다른 데이터 형식이 서로 다른 상수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대해 절. 그러나 공통을 사용 하 여 동일한 형식으로 여러 상수를 선언할 수 없습니다 `As` 절.  
  
-   **초기화 합니다.** 모든 상수 값을 초기화 해야 `constantlist`합니다. 사용 하면 `initializer` 상수에 할당 하는 식을 제공 합니다. 식은은 리터럴, 이미 정의 되어 있는 다른 상수 이미 정의 된 열거형 멤버의 조합 될 수 있습니다. 이러한 요소를 결합 하 산술 및 논리 연산자를 사용할 수 있습니다.  
  
     변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다. 그러나와 같은 변환 키워드를 사용할 수는 `CByte` 및 `CShort`합니다. 사용할 수도 있습니다 `AscW` 상수와 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 계산 될 수 있으므로 합니다.  
  
## <a name="behavior"></a>동작  
  
-   **범위입니다.** 지역 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다. 멤버 상수는 해당 클래스, 구조체 또는 모듈 내의 모든 위치에서 액세스할 수 있습니다.  
  
-   **검증 합니다.** 코드는 클래스 외부 또는 모듈 정해야 멤버 상수 이름을 해당 클래스, 구조체 또는 모듈의 이름입니다. 코드 바깥쪽 블록 또는 프로시저일 해당 프로시저 또는 블록에 있는 로컬 상수를 참조할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Const` 문을 리터럴 값 대신 사용할 상수를 선언 합니다.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>예제  
 데이터 형식 상수를 정의 하는 경우 `Object`, Visual Basic 컴파일러의 형식을 제공 `initializer`, 대신 `Object`합니다. 다음 예제에서는 상수 `naturalLogBase` 런타임 형식이 `Decimal`합니다.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 앞의 예제를 사용 하 여는 <xref:System.Type.ToString%2A> 메서드를는 <xref:System.Type> 에서 반환 된 개체는 [GetType 연산자](../../../visual-basic/language-reference/operators/gettype-operator.md)때문에, <xref:System.Type> 변환할 수 없습니다 `String` 를 사용 하 여 `CStr`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [상수 및 열거형](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
