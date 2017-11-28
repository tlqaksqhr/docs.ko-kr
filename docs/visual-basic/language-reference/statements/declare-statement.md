---
title: Declare Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2560f34a5130ef7453b50ffb4495b67bf1dfa4c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="declare-statement"></a>Declare Statement
외부 파일에 구현 된 프로시저에 대 한 참조를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attributelist`|선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.|  
|`accessmodifier`|선택 사항입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [공개](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.|  
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|  
|`charsetmodifier`|선택 사항입니다. 문자 집합 및 파일을 지정 정보를 검색 합니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (기본값)<br />-   [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [자동](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|선택적 `Sub` 또는 `Function` 나타나야 합니다. 외부 프로시저 값을 반환 하지 않는 것을 나타냅니다.|  
|`Function`|선택적 `Sub` 또는 `Function` 나타나야 합니다. 외부 프로시저에 값을 반환 했는지를 나타냅니다.|  
|`name`|필수 요소. 이 외부 참조의 이름입니다. 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`Lib`|필수 요소. 소개는 `Lib` 절 외부 프로시저를 포함 하는 외부 파일 (DLL 또는 코드 리소스)를 식별 합니다.|  
|`libname`|필수 요소. 선언된 된 프로시저를 포함 하는 파일의 이름입니다.|  
|`Alias`|선택 사항입니다. 에 지정 된 이름으로 선언 되는 프로시저 파일 내에서 식별할 수 없음을 나타냅니다 `name`합니다. 해당 id를 지정 `aliasname`합니다.|  
|`aliasname`|사용 하는 경우 필요는 `Alias` 키워드입니다. 두 가지 방법 중 하나에서 프로시저를 식별 하는 문자열:<br /><br /> 따옴표 안에 해당 파일 내에서 프로시저의 진입점 이름 (`""`)<br /><br /> 또는<br /><br /> 숫자 기호 (`#`) 뒤에 해당 파일 내에서 프로시저의 진입점의 서 수를 지정 하는 정수|  
|`parameterlist`|프로시저 매개 변수를 사용 하는 경우 필요 합니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|  
|`returntype`|필요한 경우 `Function` 지정 및 `Option Strict` 은 `On`합니다. 프로시저에서 반환 되는 값의 데이터 형식입니다.|  
  
## <a name="remarks"></a>설명  
 경우에 따라 프로젝트 외부 (예: DLL 또는 코드 리소스) 파일에 정의 된 프로시저를 호출 해야 합니다. 이 작업을 수행 하는 경우 Visual Basic 컴파일러 액세스 절차를 올바르게 호출 하는 데 필요한 정보를, 프로시저의 위치, 식별 되는 방법, 호출 시퀀스 및 반환 형식 및 문자열 문자 집합을 사용 하 여 같은 않아도 됩니다. `Declare` 문은 외부 프로시저에 대 한 참조를 만들고를 이와 같이 필요한 정보를 제공 합니다.  
  
 `Declare`는 모듈 수준에서만 사용할 수 있습니다. 즉,는 *선언 컨텍스트* 외부 참조 클래스, 구조체 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 인터페이스, 프로시저 또는 블록 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 외부 참조는 기본적으로 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다.  
  
## <a name="rules"></a>규칙  
  
-   **특성입니다.** 외부 참조에 특성을 적용할 수 있습니다. 적용 되는 특성은 외부 파일을 프로젝트에만 효과가 있습니다.  
  
-   **한정자입니다.** 외부 프로시저는 암시적으로 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)합니다. 사용할 수 없습니다는 `Shared` 키워드를 외부 참조를 선언 공유 상태를 변경할 수 없습니다.  
  
     외부 프로시저 재정의에 참여, 인터페이스 멤버를 구현 하거나 이벤트를 처리할 수 없습니다. 적절 하 게 사용할 수 없습니다는 `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, 또는 `Handles` 키워드는 `Declare` 문.  
  
-   **외부 프로시저 이름입니다.** 이 외부 참조에 같은 이름을 제공할 필요가 없습니다 (에서 `name`) 외부 파일 내에서 프로시저의 진입점 이름으로 (`aliasname`). 사용할 수는 `Alias` 절 진입점 이름을 지정 합니다. 이 수는 외부 프로시저가 Visual Basic 예약된 한정자 또는 변수, 프로시저 또는 다른 프로그래밍 요소와 같은 이름을 같은 범위에 있는 경우에 유용 합니다.  
  
    > [!NOTE]
    >  대부분의 Dll의 진입점 이름은 대/소문자를 구분 하지 않습니다.  
  
-   **외부 프로시저 번호입니다.** 사용할 수 있습니다는 `Alias` 절을 외부 파일의 내보내기 테이블 내에서 진입점의 서 수를 지정 합니다. 이 작업을 수행 하려면 먼저 `aliasname` 숫자 기호 (`#`). 외부 파일 이름 없이 프로시저를 내보내는 경우 또는 Visual basic의 경우 외부 프로시저 이름에 있는 문자 허용 되지 않은 경우에 유용할 수 있습니다.  
  
## <a name="data-type-rules"></a>데이터 형식 규칙  
  
-   **매개 변수 데이터 형식입니다.** 경우 `Option Strict` 은 `On`에서 각 매개 변수의 데이터 형식을 지정 해야 `parameterlist`합니다. 이 열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 데이터 형식일 수 있습니다. 내에서 `parameterlist`를 사용 하면는 `As` 데이터 형식의 각 매개 변수에 전달 될 인수를 지정 하는 절.  
  
    > [!NOTE]
    >  .NET Framework에 대 한 외부 프로시저 작성 되지, 하는 경우 주의 해야 데이터 형식을 해당 하는 합니다. 예를 들어, Visual Basic 6.0 프로시저에 대 한 외부 참조를 선언 하는 경우는 `Integer` 매개 변수 (Visual Basic 6.0에서 16 비트)로 서의 해당 인수를 식별 해야 `Short` 에 `Declare` 문, 16-이기 때문에 Visual Basic의 비트 정수 형식입니다. 마찬가지로, `Long` Visual Basic 6.0에서 다른 데이터 너비가 및 `Date` 다르게 구현 됩니다.  
  
-   **데이터 형식을 반환 합니다.** 외부 프로시저가 `Function` 및 `Option Strict` 은 `On`, 호출 코드에 반환 되는 값의 데이터 형식을 지정 해야 합니다. 이 열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 데이터 형식일 수 있습니다.  
  
    > [!NOTE]
    >  Visual Basic 컴파일러는 데이터 형식이 외부 프로시저의 인수와 호환 되는지 확인 하지 않습니다. 불일치가 있을 경우 공용 언어 런타임에서 생성 된 <xref:System.Runtime.InteropServices.MarshalDirectiveException> 런타임 시 예외입니다.  
  
-   **기본 데이터 형식입니다.** 경우 `Option Strict` 은 `Off` 의 매개 변수 데이터 형식을 지정 하지 않으면 및 `parameterlist`, Visual Basic 컴파일러에서 해당 인수를 변환의 [Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)합니다. 마찬가지로, 지정 하지 않으면 `returntype`, 컴파일러는 반환 데이터 형식이 되도록 `Object`합니다.  
  
    > [!NOTE]
    >  다른 플랫폼에서 기록 된 외부 프로시저를 처리 하는 때문에 데이터 형식에 대 한 가정을 또는 기본값을 지정할 수 있도록 위험 합니다. 있는 경우 더 훨씬 안전의 모든 매개 변수 및 반환 값의 데이터 형식을 지정 합니다. 또한 코드의 가독성 향상 됩니다.  
  
## <a name="behavior"></a>동작  
  
-   **범위입니다.** 범위 전체에서 해당 클래스, 구조체 또는 모듈에에서 대 한 외부 참조가입니다.  
  
-   **수명입니다.** 외부 참조는 클래스, 구조체 또는 모듈 선언 된와 수명이 동일 합니다.  
  
-   **외부 프로시저를 호출 합니다.** 외부 프로시저를 호출 하면 동일한 방식으로 호출 된 `Function` 또는 `Sub` 프로시저-값을 반환 하는 경우 식에서 사용 하거나에서 지정 하 여는 [Call 문을](../../../visual-basic/language-reference/statements/call-statement.md) 값을 반환 하지 않는 경우.  
  
     에 의해 지정 된 대로 정확 하 게 외부 프로시저에 인수를 전달 `parameterlist` 에 `Declare` 문. 에 고려 되지 않습니다 계정 매개 변수는 외부 파일에서 원래 선언 된는 어떻게 합니다. 마찬가지로, 반환 값 이면 사용 하 여 지정 된 대로 정확 하 게 `returntype` 에 `Declare` 문.  
  
-   **문자 집합입니다.** 지정할 수 있습니다 `charsetmodifier` 어떻게 Visual Basic 문자열 마샬링하고 외부 프로시저를 호출할 때입니다. `Ansi` 한정자에는 모든 문자열을 ANSI 값을 마샬링합니다 Visual Basic 하도록 지시 및 `Unicode` 한정자 마샬링해야 하는 모든 문자열을 유니코드 값으로 보냅니다. `Auto` 한정자 Visual Basic.NET Framework에 따라 문자열을 마샬링 하 규칙 외부 참조를 기반 알려 `name`, 또는 `aliasname` 지정 합니다. 기본값은 `Ansi`입니다.  
  
     `charsetmodifier`또한 Visual Basic 외부 파일 내에서 외부 프로시저를 조회 방법을 지정 합니다. `Ansi`및 `Unicode` 둘 다 직접 Visual Basic로 검색 하는 동안 이름을 수정 하지 않고 조회 합니다. `Auto`Visual Basic 하는 런타임 플랫폼의 기본 문자 집합을 결정 하 고 다음과 같은 외부 프로시저 이름을 수정 하도록 지시 합니다.  
  
    -   Windows 95, Windows 98 또는 Windows Millennium Edition 등의 ANSI 플랫폼에서 먼저 외부 프로시저 이름 수정 하지 않을를 찾습니다. 실패할 경우 외부 프로시저 이름의 끝에 "A"를 추가 하 고 다시 조회 합니다.  
  
    -   Windows NT, Windows 2000 또는 Windows XP와 같은 유니코드 플랫폼에서 먼저 외부 프로시저 이름 수정 하지 않을를 찾습니다. 실패할 경우 추가 "W" 끝에는 외부 프로시저의 이름을 지정 하 고 다시 조회 합니다.  
  
-   **메커니즘입니다.** .NET Framework를 사용 하는 Visual Basic *플랫폼 호출* 확인 하 고 외부 프로시저 액세스할 (PInvoke) 메커니즘입니다. `Declare` 문 및 <xref:System.Runtime.InteropServices.DllImportAttribute> 클래스에는 모두 자동으로이 메커니즘을 사용 하 고 PInvoke에 대 한 지식이 필요 하지 않습니다. 자세한 내용은 참조 [연습: Windows Api 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)합니다.  
  
> [!IMPORTANT]
>  외부 프로시저가 실행 될 경우 공용 언어 런타임 (CLR) 외부, *비관리 코드*합니다. 이러한 프로시저, 예: Win32 API 함수 또는 COM 메서드를 호출 하는 경우 응용 프로그램 보안 위험을 노출할 수 있습니다. 자세한 내용은 참조 [보안 코딩 지침 비관리 코드에 대 한](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 선언에 대 한 외부 참조는 `Function` 현재 사용자 이름을 반환 하는 프로시저입니다. 그런 다음 호출 하는 외부 프로시저가 `GetUserNameA` 의 일부로 `getUser` 프로시저입니다.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>예제  
 <xref:System.Runtime.InteropServices.DllImportAttribute> 비관리 코드에서 함수를 사용 하는 대체 방법을 제공 합니다. 다음 예제에서는 가져온된 함수를 사용 하지 않고 선언는 `Declare` 문.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Call 문](../../../visual-basic/language-reference/statements/call-statement.md)  
 [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
