---
title: Option Strict 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: ac8f6fa2ebd2f8d846c3662184c83a83477e2311
ms.sourcegitcommit: 875ecc3ab2437e299b1d50076bd9b878fa8c64de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43238552"
---
# <a name="option-strict-statement"></a>Long
암시적 데이터 형식 변환을 확대 변환 으로만 제한 하 고 런타임에 바인딩을 허용 하지 않습니다.에 이어지는 암시적 형식 지정을 허용 하지 않습니다는 `Object` 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`On`|선택 사항입니다. 사용 하도록 설정 `Option Strict` 확인 합니다.|  
|`Off`|선택 사항입니다. 사용 하지 않도록 설정 `Option Strict` 확인 합니다.|  
  
## <a name="remarks"></a>설명  
 때 `Option Strict On` 또는 `Option Strict` 나타납니다 파일에서 다음과 같은 컴파일 타임 오류가 발생 합니다.  
  
-   암시적 축소 변환  
  
-   런타임에 바인딩  
  
-   `Object` 유형으로 이어지는 암시적 형식 지정  
  
> [!NOTE]
>  에 설정할 수 있는 경고 구성에는 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 컴파일 시간 오류가 발생 하는 세 가지 조건에 해당 하는 세 가지 설정이 있습니다. 이러한 설정을 사용 하는 방법에 대 한 정보를 참조 하세요 [IDE에 경고 구성을 설정 하려면](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) 이 항목의 뒷부분에 나오는.  
  
 `Option Strict Off` 문을 해제 오류 및 경고 확인 세 조건을 모두 연결 된 IDE 설정 오류 또는 경고를 설정 하도록 지정 하는 경우에 합니다. `Option Strict On` 이러한 오류나 경고를 해제 하 여 연결 된 IDE 설정 지정 하는 경우에 오류 및 경고 확인 세 조건을 모두 문을 설정 합니다.  
  
 를 사용 하는 경우는 `Option Strict` 문을 파일에 다른 코드 문 앞에 나타나야 합니다.  
  
 설정한 경우 `Option Strict` 에 `On`, Visual Basic에서는 모든 프로그래밍 요소에 대해 지정 되어 있는지 확인 합니다. 데이터 형식은 명시적으로 지정 된 또는 로컬 형식 유추를 사용 하 여 지정할 수 있습니다. 모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것이 좋습니다, 다음과 같은 이유로:  
  
-   프로그램 변수 및 매개 변수에 대 한 IntelliSense 지원도를 수 있습니다. 이 옵션을 사용 하면 코드를 입력할 때 해당 속성 및 다른 구성원을 볼 수 있습니다.  
  
-   컴파일러를에 형식 검사를 수행할 수 있습니다. 형식 검사 형식 변환 오류로 인해 런타임에 실패할 수 있는 문을 찾는 데 도움이 됩니다. 또한 이러한 메서드를 지원 하지 않는 개체에서 메서드 호출을 식별 합니다.  
  
-   이 코드의 실행 속도 높입니다. 그 이유 중 하나는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않으면, Visual Basic 컴파일러를 할당 하는 `Object` 형식입니다. 컴파일된 코드 사이 변환 해야 할 수 `Object` 및 다른 데이터 형식을 사용 하면 성능이 저하 됩니다.  
  
## <a name="implicit-narrowing-conversion-errors"></a>암시적 축소 변환 오류  
 암시적 축소 변환 오류는 축소 변환인 암시적 데이터 형식 변환이 있을 경우 발생합니다.  
  
 Visual Basic 다른 데이터 형식으로 다양 한 데이터 형식을 변환할 수 있습니다. 데이터 형식의 값을 정밀도 나 용량이 있는 데이터 형식으로 변환 되 면 데이터 손실이 발생할 수 있습니다. 축소 변환이 실패 하면 런타임 오류가 발생 합니다. `Option Strict` 사용 하면 컴파일 시간 알림이 이러한 축소 변환을 방지 하는 합니다. 자세한 내용은 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) 하 고 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)합니다.  
  
 변환 오류를 일으킬 수 있는 식에서 발생 하는 암시적 변환이 포함 됩니다. 자세한 내용은 다음 항목을 참조하세요.  
  
-   [+ 연산자](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [+= 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char 데이터 형식](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 사용 하 여 문자열을 연결 하는 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md), 모든 문자열 변환을 확대 될 것으로 간주 됩니다. 암시적 축소 변환 오류를 경우에도 이러한 변환이 생성 되지 않습니다 있도록 `Option Strict` 켜져 있습니다.  
  
 해당 매개 변수에서 다른 데이터 형식을 갖는 인수를 사용 하는 메서드를 호출 하면 축소 변환 하면 컴파일 타임 오류 `Option Strict` 켜져 있습니다. 확대 변환 또는 변환 하는 명시적 변환을 사용 하 여 컴파일 타임 오류를 방지할 수 있습니다.  
  
 암시적 축소 변환 오류 요소에서 변환에 대 한 컴파일 타임에 표시 되지 않습니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다. 이런 경우에 `Option Strict` 켜져 있습니다. 자세한 내용은 "Narrowing Conversions" 섹션을 참조 하세요. [각각에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
## <a name="late-binding-errors"></a>런타임에 바인딩 오류  
 개체에 `Object` 형식으로 선언된 변수의 속성 또는 메서드에 할당되면 런타임에 바인딩됩니다. 자세한 내용은 [초기 바인딩 및 런타임에 바인딩](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)합니다.  
  
## <a name="implicit-object-type-errors"></a>암시적 개체 형식 오류  
 암시적 개체 형식 오류는 선언된 변수에 대해 적절한 형식이 유추될 수 없어 `Object`의 형식이 유추될 때 발생합니다. 주로 `As` 절을 사용하지 않고 `Dim` 문을 사용하여 변수를 선언하고, `Option Infer`가 꺼져 있는 경우 발생합니다. 자세한 내용은 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 하며 [Visual Basic 언어 사양](../../../visual-basic/reference/language-specification/index.md)합니다.  
  
 메서드 매개 변수에 대 한 합니다 `As` 절은 선택 사항 경우 `Option Strict` 꺼져 있습니다. 그러나 하나의 매개 변수를 사용 하는 경우는 `As` 절을 모두 사용 해야 합니다. 경우 `Option Strict` 가 on으로 설정 된 `As` 절은 모든 매개 변수 정의 대 한 필수입니다.  
  
 사용 하지 않고 변수를 선언 하는 경우는 `As` 절으로 설정 하 고 `Nothing`, 변수의 형식이 `Object`합니다. 컴파일 타임 오류가 발생 하지 않는 경우에 경우 `Option Strict` 켜져 및 `Option Infer` 켜져 있습니다. 이러한 예로 `Dim something = Nothing`합니다.  
  
### <a name="default-data-types-and-values"></a>기본 데이터 형식 및 값  
 다음 표에서 데이터 형식과 이니셜라이저를 지정 하는 다양 한 조합의 결과 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
|데이터 형식 지정 여부|이니셜라이저 지정 여부|예제|결과|  
|---|---|---|---|  
|아니요|아니요|`Dim qty`|`Option Strict`가 off(기본값)이면 변수는 `Nothing`으로 설정됩니다.<br /><br /> `Option Strict`가 on이면 컴파일 타임 오류가 발생합니다.|  
|아니요|예|`Dim qty = 5`|`Option Infer`가 on(기본값)이면 변수가 이니셜라이저의 데이터 형식을 사용합니다. 참조 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 타임 오류가 발생합니다.|  
|예|아니요|`Dim qty As Integer`|변수는 데이터 형식의 기본값으로 초기화됩니다. 자세한 내용은 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.|  
|예|예|`Dim qty  As Integer = 5`|이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Option Strict 문은 현재 없는 경우  
 소스 코드에 없는 경우는 `Option Strict` 문을 **Option strict** 에 설정 합니다 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다. 합니다 **컴파일 페이지** 오류를 생성 하는 조건에 대 한 추가 제어를 제공 하는 설정이 있습니다.  
  
 명령줄 컴파일러를 사용 하는 경우 사용할 수 있습니다 합니다 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션에 대 한 설정을 지정 하려면 `Option Strict`합니다.  
  
### <a name="to-set-option-strict-in-the-ide"></a>IDE에서 Option Strict를 설정 하려면  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  에 **컴파일** 탭의 값을 설정 합니다 **Option Strict** 상자입니다.  
  
###  <a name="conditions"></a> IDE에서 경고 구성을 설정 하려면  
 사용 하는 경우는 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 대신는 `Option Strict` 문을 제어할 수 추가 오류를 생성 하는 조건입니다. **경고 구성** 섹션을 **컴파일 페이지** 컴파일 타임 오류가 발생 하는 세 가지 조건에 해당 하는 설정이 때 `Option Strict` 켜져 합니다. 이러한 설정은 다음과 같습니다.  
  
-   **암시적 변환**  
  
-   **런타임에 바인딩; 호출이 실패할 수 있음**  
  
-   **암시적 형식; 개체로 간주**  
  
 **Option Strict**를 **On**으로 설정하는 경우 이러한 세 가지 경고 구성 설정은 모두 **Error**로 설정됩니다. **Option Strict**를 **Off**로 설정하는 경우 세 가지 설정은 모두 **None**으로 설정됩니다.  
  
 각 경고 구성 설정은 **None**, **Warning** 또는 **Error**로 개별적으로 변경할 수 있습니다. 세 가지 경고 구성 설정이 모두 **Error**로 설정된 경우 `On`이 `Option strict` 상자에 표시됩니다. 세 가지 모두 **None**으로 설정된 경우 `Off`가 이 상자에 표시됩니다. 이러한 설정의 다른 조합의 경우 **(사용자 지정)** 이 나타납니다.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>새 프로젝트의 Option Strict 기본 설정을 설정 하려면  
 프로젝트를 만들 때를 **Option Strict** 에 설정 합니다 **컴파일** 탭으로 설정 됩니다는 **Option Strict** 에서 설정를 **옵션** 대화 상자입니다.  
  
 설정할 `Option Strict` 이 대화 상자에서에 **도구** 메뉴에서 클릭 **옵션**합니다. **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다. 초기 기본 설정은 **VB 기본값** 는 `Off`합니다.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>명령줄에서 Option Strict를 설정 하려면  
 포함 된 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 **vbc** 명령.  
  
## <a name="example"></a>예제  
 다음 예제에서는 암시적 형식 변환 하는 축소 변환에 의해 발생 한 컴파일 시간 오류를 보여 줍니다. 이 범주의 오류에 해당 하는 **암시적으로 변환** 조건에 **컴파일 페이지**합니다.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 런타임에 바인딩 인해 컴파일 시간 오류를 보여 줍니다. 이 범주의 오류에 해당 하는 **늦게 바인딩; 호출이 런타임에 실패할 수 있음** 조건에 **컴파일 페이지**합니다.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 암시적 유형으로 선언 된 변수에 의해 발생 한 오류를 보여 줍니다. `Object`합니다. 이 범주의 오류에 해당 하는 **암시적 형식; 개체로 간주** 조건에 **컴파일 페이지**합니다.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [방법: 개체의 멤버에 액세스](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Office 솔루션에서 런타임에 바인딩](https://msdn.microsoft.com/library/3xxe951d)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
