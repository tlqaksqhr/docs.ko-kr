---
title: "Declare Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Declare"
  - "vb.Lib"
  - "vb.Any"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Lib keyword"
  - "declaring procedures, Declare statement"
  - "functions [Visual Basic], function procedures"
  - "declarations, procedures"
  - "procedures, declaration"
  - "procedures, external"
  - "Alias keyword"
  - "external references, Visual Basic"
  - "DLLs, declaring procedures"
  - "Declare statement"
  - "declarations, external"
  - "Visual Basic code, Function procedures"
  - "As keyword, in Declare statement"
  - "resources [Visual Basic], declaring"
  - "Public keyword, Declare statement"
  - "platform invoke, Visual Basic external references"
  - "Sub procedures, declarations"
  - "APIs, declaring API functions"
  - "Visual Basic code, Sub procedures"
  - "Function procedures, declaring"
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Declare Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

외부 파일에 구현된 프로시저에 대한 참조를 선언합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attributelist`|선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.|  
|`accessmodifier`|선택적 요소.  다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.|  
|`Shadows`|선택적 요소.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.|  
|`charsetmodifier`|선택적 요소.  문자 집합과 파일 검색 정보를 지정합니다.  다음 중 하나일 수 있습니다.<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)\(기본값\)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|선택적 요소. `Sub`나 `Function` 중 하나가 반드시 있어야 합니다.  외부 프로시저가 값을 반환하지 않음을 나타냅니다.|  
|`Function`|선택적 요소. `Sub`나 `Function` 중 하나가 반드시 있어야 합니다.  외부 프로시저가 값을 반환함을 나타냅니다.|  
|`name`|필수 요소.  이 외부 참조의 이름입니다.  자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`Lib`|필수 요소.  외부 프로시저를 포함하는 외부 파일\(DLL 또는 코드 리소스\)을 식별하는 `Lib` 절을 지정합니다.|  
|`libname`|필수 요소.  선언된 프로시저가 포함되어 있는 파일의 이름입니다.|  
|`Alias`|선택적 요소.  선언할 프로시저를 `name`에 지정된 이름으로 해당 파일 내에서 식별할 수 없음을 나타냅니다.  해당 식별 사항을 `aliasname`에 지정합니다.|  
|`aliasname`|`Alias` 키워드를 사용하는 경우 필수적 요소입니다.  다음은 두 가지 방법 중 하나로 프로시저를 식별하는 문자열입니다.<br /><br /> 해당 파일 내에서 프로시저의 진입점 이름을 따옴표\(`""`\)로 묶은 것입니다.<br /><br /> 또는<br /><br /> 숫자 기호\(`#`\)와 해당 파일 내에서 프로시저의 진입점을 나타내는 서수 번호를 지정하는 정수입니다.|  
|`parameterlist`|프로시저에서 매개 변수를 사용하는 경우 필수적 요소입니다.  자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)를 참조하십시오.|  
|`returntype`|`Function`을 지정하고 `Option Strict`가 `On`인 경우 필수적 요소입니다.  프로시저에서 반환되는 값의 데이터 형식입니다.|  
  
## 설명  
 DLL 또는 코드 리소스와 같은 프로젝트 외부 파일에 정의된 프로시저를 호출해야 하는 경우도 있습니다.  이 경우 Visual Basic 컴파일러는 프로시저의 위치, 식별 방법, 호출 시퀀스와 반환 형식 및 사용되는 문자열 문자 집합 등 프로시저를 정확하게 호출하는 데 필요한 정보에 액세스할 수 없습니다.  `Declare` 문은 외부 프로시저에 대한 참조를 만들고 이와 같이 필요한 정보를 제공합니다.  
  
 `Declare` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, 외부 참조에 대한 *선언 컨텍스트*는 클래스, 구조체 또는 모듈이어야 하며 소스 파일, 네임스페이스, 인터페이스, 프로시저 또는 블록일 수는 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 외부 참조는 기본적으로 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스입니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  
  
## 규칙  
  
-   **특성** 특성을 외부 참조에 적용할 수 있습니다.  적용되는 특성은 프로젝트에만 영향을 미치고 외부 파일에는 영향을 미치지 않습니다.  
  
-   **한정자.** 외부 프로시저는 암시적으로 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)됩니다.  외부 참조를 선언할 때는 `Shared` 키워드를 사용할 수 없으며, 해당 공유 상태를 변경할 수 없습니다.  
  
     외부 프로시저는 재정의에 참여하거나, 인터페이스 멤버를 구현하거나, 이벤트를 처리할 수 없습니다.  따라서 `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements` 또는 `Declare` 문의 `Handles` 키워드를 사용할 수 없습니다.  
  
-   **외부 프로시저 이름.** 이 외부 참조에 해당 외부 파일 내에서 프로시저의 진입점 이름\(`aliasname`\)과 동일한 이름\(`name`\)을 부여할 필요가 없습니다.  진입점 이름을 지정하는 데는 `Alias` 절을 사용할 수 있습니다.  이 방법은 외부 프로시저가 Visual Basic의 예약된 한정자나 변수, 프로시저 또는 해당 범위 내 기타 프로그래밍 요소와 동일한 이름을 갖는 경우에 유용할 수 있습니다.  
  
    > [!NOTE]
    >  대부분의 DLL에서 진입점 이름은 대\/소문자를 구분합니다.  
  
-   **외부 프로시저 번호.** `Alias` 절을 사용하여 외부 파일의 내보내기 테이블 내에 있는 진입점에 대해 서수를 지정할 수도 있습니다.  이렇게 하려면 `aliasname`을 숫자 기호\(`#`\)로 시작합니다.  이 방법은 외부 프로시저 이름에 포함된 문자가 Visual Basic에서 허용되지 않는 경우나 외부 파일에서 프로시저를 이름이 없는 상태로 내보낼 경우에 유용합니다.  
  
## 데이터 형식 규칙  
  
-   **매개 변수 데이터 형식.** `Option Strict`가 `On`인 경우 각 매개 변수의 데이터 형식을 `parameterlist`에 지정해야 합니다.  열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 모든 데이터 형식을 지정할 수 있습니다.  `parameterlist` 내에서는 `As` 절을 사용하여 각 매개 변수에 전달할 인수의 데이터 형식을 지정합니다.  
  
    > [!NOTE]
    >  외부 프로시저가 .NET Framework용으로 작성되지 않은 경우에는 데이터 형식이 일치하는지 주의해야 합니다.  예를 들어, `Integer` 매개 변수\(Visual Basic 6.0에서는 16비트\)를 사용하는 Visual Basic 6.0 프로시저에 대한 외부 참조를 선언하는 경우 Visual Basic에서는 `Short`가 16비트 정수 형식이므로 `Declare` 문에서 해당 인수를 Short로 나타내야 합니다.  마찬가지로 Visual Basic 6.0에서는 `Long`의 데이터 너비가 다르므로 `Date`를 다르게 구현해야 합니다.  
  
-   **반환 데이터 형식.** 외부 프로시저가 `Function`이고 `Option Strict`가 `On`인 경우 호출 코드로 반환되는 값의 데이터 형식을 지정해야 합니다.  열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 모든 데이터 형식을 지정할 수 있습니다.  
  
    > [!NOTE]
    >  Visual Basic 컴파일러에서는 데이터 형식이 외부 프로시저의 데이터 형식과 호환되는지 확인하지 않습니다.  일치하지 않는 데이터 형식이 있는 경우 공용 언어 런타임에서는 런타임에 <xref:System.Runtime.InteropServices.MarshalDirectiveException> 예외를 생성합니다.  
  
-   **기본 데이터 형식.** `Option Strict`가 `Off`이고 `parameterlist`에 매개 변수의 데이터 형식을 지정하지 않은 경우에는 Visual Basic 컴파일러에서 해당 인수를 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)으로 변환합니다.  마찬가지로 `returntype`을 지정하지 않으면 컴파일러에서 반환 데이터 형식을 `Object`로 변환합니다.  
  
    > [!NOTE]
    >  다른 플랫폼에서 작성되었을 수도 있는 외부 프로시저를 처리하게 되므로 데이터 형식을 가정하거나 데이터 형식의 기본값을 허용하는 것은 위험할 수 있습니다.  모든 매개 변수와 반환 값\(있는 경우\)의 데이터 형식을 반드시 지정하는 것이 훨씬 안전합니다.  이렇게 하면 가독성도 향상되어 코드를 쉽게 읽을 수 있습니다.  
  
## 동작  
  
-   **범위.** 외부 참조는 해당 클래스, 구조체 또는 모듈 전체의 범위에 있습니다.  
  
-   **수명.** 외부 참조의 수명은 외부 참조가 선언된 클래스, 구조체 또는 모듈의 수명과 동일합니다.  
  
-   **외부 프로시저 호출.** `Function` 또는 `Sub` 프로시저 호출과 동일한 방법으로 외부 프로시저를 호출합니다. 즉, 값을 반환하는 경우 식에서 외부 프로시저를 사용하고, 값을 반환하지 않는 경우에는 [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md)에서 외부 프로시저를 지정합니다.  
  
     `Declare` 문의 `parameterlist`에 지정된 대로 외부 프로시저에 인수를 전달합니다.  매개 변수가 외부 파일에서 원래 선언된 방식은 고려할 필요가 없습니다.  마찬가지로 반환 값이 있는 경우에도 `Declare` 문의 `returntype`에 지정된 대로 반환 값을 사용합니다.  
  
-   **문자 집합.** Visual Basic에서 외부 프로시저를 호출할 때 문자열을 마샬링하는 방법을 `charsetmodifier`에 지정할 수 있습니다.  `Ansi` 한정자는 Visual Basic에서 모든 문자열을 ANSI 값으로 마샬링하도록 지시하며 `Unicode` 한정자는 Visual Basic에서 모든 문자열을 유니코드 값으로 마샬링하도록 지시합니다.  `Auto` 한정자는 Visual Basic에서 `name` 외부 참조 또는 `aliasname` 외부 참조\(지정된 경우\)를 기반으로 하는 .NET Framework 규칙에 따라 문자열을 마샬링하도록 지시합니다.  기본값은 `Ansi`입니다.  
  
     `charsetmodifier`는 Visual Basic이 외부 파일 내에서 외부 프로시저 이름을 검색하는 방법도 지정합니다.  `Ansi` 및 `Unicode` 모두 Visual Basic에서 검색 중에 해당 이름을 수정하지 않고 직접 조회합니다.  `Auto`는 Visual Basic이 런타임 플랫폼의 기본 문자 집합을 결정하고 가능하면 외부 프로시저 이름을 다음과 같이 수정하도록 지시합니다.  
  
    -   Windows 95, Windows 98 또는 Windows Millennium Edition 같은 ANSI 플랫폼에서는 이름 수정 없이 외부 프로시저를 먼저 조회합니다.  찾지 못한 경우 외부 프로시저 이름 끝에 "A"를 추가하고 다시 조회합니다.  
  
    -   Windows NT, Windows 2000 또는 Windows XP 같은 유니코드 플랫폼에서는 이름 수정 없이 외부 프로시저를 먼저 조회합니다.  찾지 못한 경우 외부 프로시저 이름 끝에 "W"를 추가하고 다시 조회합니다.  
  
-   **메커니즘.** Visual Basic에서는 .NET Framework PInvoke\(*플랫폼 호출*\) 메커니즘을 사용하여 외부 프로시저를 확인하고 액세스합니다.  `Declare` 문과 <xref:System.Runtime.InteropServices.DllImportAttribute> 클래스에는 모두 이 메커니즘이 자동으로 사용되므로 사용자가 PInvoke를 몰라도 상관없습니다.  자세한 내용은 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  외부 프로시저가 CLR\(공용 언어 런타임\) 외부에서 실행되는 경우 외부 프로시저는 *비관리 코드*입니다.  그러한 프로시저\(예: Win32 API 함수 또는 COM 메서드\)를 호출하는 경우 응용 프로그램이 보안 위험에 노출될 수 있습니다.  자세한 내용은 [비관리 코드에 대한 보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines%20for%20Unmanaged%20Code.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 현재 사용자 이름을 반환하는 `Function` 프로시저에 대한 외부 참조를 선언합니다.  그런 다음 `GetUserNameA` 외부 프로시저를 `getUser` 프로시저의 일부로 호출합니다.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_1.vb)]  
  
## 예제  
 <xref:System.Runtime.InteropServices.DllImportAttribute>를 통해 비관리 코드에서 함수를 사용할 수도 있습니다.  다음 예제에서는 `Declare` 문을 사용하지 않고 가져온 함수를 선언합니다.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_3.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)