---
title: "Option Strict Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Strict"
  - "vb.OptionStrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Strict keyword"
  - "Option Strict statement"
  - "conversions, implicit"
  - "late binding"
  - "implicit conversions"
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Option Strict Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

암시적 데이터 형식 변환을 확대 변환으로만 제한하고 런타임에 바인딩을 허용하지 않으며 `Object` 형식에서 해당 결과를 암시적으로 입력할 수 없습니다.  
  
## 구문  
  
```  
Option Strict { On | Off }  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`On`|선택적 요소.  `Option Strict` 검사를 설정합니다.|  
|`Off`|선택적 요소.  `Option Strict` 검사를 해제합니다.|  
  
## 설명  
 `Option Strict On` 또는 `Option Strict`가 한 파일에 나타나면 다음 조건에서 컴파일 타임 오류가 발생합니다.  
  
-   암시적 축소 변환  
  
-   런타임에 바인딩  
  
-   `Object` 유형이 되는 암시적 입력  
  
> [!NOTE]
>  [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)에 설정할 수 있는 경고 구성에는 컴파일 타임 오류로 인해 발생하는 세 가지 조건에 해당하는 3개의 설정이 있습니다.  이러한 설정을 사용하는 방법에 대한 자세한 내용은 [IDE에서 경고 구성을 설정하려면](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions)를 참조하십시오.  
  
 `Option Strict Off` 문에서는 관련 IDE 설정이 이러한 오류 또는 경로를 설정하도록 지정하더라도 모든 3개 조건에 대한 오류 및 경로 확인을 해제합니다.  `Option Strict On`명세서을 설정오류와경고모두 세 개의 상태를 확인할 이러한 오류 또는 경고를 해제 하려면 연결 된 IDE 설정을 지정한 경우에.  
  
 이 요소를 사용하는 경우 `Option Strict` 문은 파일에서 원본 코드 문의 제일 앞에 와야 합니다.  
  
 설정 하면 `Option Strict` 에 `On`,Visual Basic검사 모든 프로그래밍 요소에 대해 데이터 형식을 지정 합니다.  데이터 형식은 명시적으로 지정 하거나 지역 형식유추를 사용 하 여 지정 된 수 있습니다.  모든 프로그래밍 요소의 데이터 형식을 지정 하는 다음과 같은 경우에 좋습니다.  
  
-   변수와 매개 변수에 대해 IntelliSense 지원을 사용할 수 있습니다.  이를 사용하면 코드를 입력할 때 변수의 속성과 다른 멤버를 볼 수 있습니다.  
  
-   컴파일러에서 형식 검사를 수행하여  형식을 확인하면 형식 변환 오류로 인해 런타임 시 실패할 수 있는 문을 찾을 수 있습니다.  또한 메서드를 지원하지 않는 개체에 대한 메서드 호출을 식별합니다.  
  
-   이코딩하다의 실행 속도가 빨라집니다.  이 대 한 이유 중 하나입니다Visual Basic컴파일러프로그래밍 요소에 대 한데이터 형식를 지정 하지 않으면이 할당은 `Object` 형식입니다.   컴파일된코딩하다사용할 수 있는변환하다을 앞뒤로 사이 `Object` 및성능저하 되는 다른 데이터 형식입니다.  
  
## 암시적 축소 변환 오류  
 암시적 축소 변환 오류는 축소 변환인 암시적 데이터 형식 변환이 있을 경우 발생합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 많은 데이터 형식을 다른 데이터 형식으로 변환할 수 있습니다.  특정 데이터 형식의 값을 정밀도가 낮거나 용량이 적은 데이터 형식으로 변환하면 데이터가 손실될 수 있습니다.  축소 변환이 실패하는 경우 런타임 오류가 발생합니다.  `Option Strict`는 축소 변환의 컴파일 타임 알림을 제공하여 이를 피할 수 있도록 합니다.  자세한 내용은 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) 및 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
 오류로 인해 식에서 발생 하는 암시적 변환이 포함될 수 있는 변환입니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [\+\= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [\/\= Operator](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)를 사용하여 문자열을 연결하면 문자열에 대한 모든 변환은 확대되는 것으로 간주됩니다.  `Option Strict`가 켜진 경우라도 이러한 변환으로 암시적 축소 변환 오류가 발생하지 않습니다.  
  
 해당 매개 변수와 다른 데이터 유형의 인수가 있는 메서드를 호출하면 축소 변환으로 인해 `Option Strict`가 설정된 경우 컴파일 시간 오류가 발생합니다.  확대 변환 또는 명시적 변환을 사용하여 컴파일 시간 오류를 피할 수 있습니다.  
  
 암시적 축소 변환 오류는 `For Each…Next` 컬렉션의 요소에서 루프 컨트롤 변수로의 변환을 위해 컴파일 타임 시 표시되지 않습니다.  이것은 `Option Strict`가 on인 경우에도 발생합니다.  자세한 내용은 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)의 "축소 변환" 단원을 참조하십시오.  
  
## 런타임에 바인딩 오류  
 개체가 `Object` 형식으로 선언된 변수의 속성 또는 메서드에 할당될 때 바인딩됩니다.  자세한 내용은 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)를 참조하십시오.  
  
## 암시적 개체 형식 오류  
 선언된 변수에 대해 적절한 형식을 유추할 수 없는 경우 암시적 개체 형식 오류가 발생하므로 `Object` 형식이 유추됩니다.  이는 주로 `Dim` 문을 통해 `As` 절을 사용하지 않고 변수를 선언할 때와 `Option Infer`가 해제되었을 경우 발생합니다.  자세한 내용은 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md)를 참조하십시오.  
  
 메서드 매개 변수의 경우 `Option Strict`가 해제되어 있으면 `As` 절은 선택적입니다.  그러나 특정 매개 변수에 `As` 절을 사용할 경우 모든 매개 변수에서 이 절을 사용해야 합니다.  `Option Strict`이 켜져 있으면 모든 매개 변수 정의에 `As` 절이 필요합니다.  
  
 `As` 절을 사용하지 않고 변수를 선언하고 해당 변수를 `Nothing`으로 설정하면 변수의 형식은 `Object`입니다.  이와 같이 `Option Strict` 및 `Option Infer`가 On인 경우 컴파일 타임 오류가 발생하지 않습니다.  이 예제는 `Dim something = Nothing`입니다.  
  
### 기본 데이터 유형 및 값  
 다음 표는 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)에 데이터 형식과 이니셜라이저를 다양한 방법으로 지정한 결과를 설명합니다.  
  
|||||  
|-|-|-|-|  
|데이터 형식이 지정되었습니까?|이니셜라이저가 지정되었습니까?|예제|결과|  
|아니요|아니요|`Dim qty`|`Option Strict`가 Off\(기본값\)이면 변수가 `Nothing`으로 설정됩니다.<br /><br /> `Option Strict`가 On이면 컴파일 타임 오류가 발생합니다.|  
|아니요|예|`Dim qty = 5`|`Option Infer`가 On\(기본값\)이면 변수의 데이터 형식은 이니셜라이저가 됩니다.  자세한 내용은 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조하십시오.<br /><br /> `Option Infer`가 off이고 `Option Strict`가 off이면 변수의 데이터 형식은 `Object`가 됩니다.<br /><br /> `Option Infer`가 Off이고 `Option Strict`가 On이면 컴파일 타임 오류가 발생합니다.|  
|예|아니요|`Dim qty As Integer`|변수가 데이터 형식에 대해 기본 값으로 초기화되었습니다.  자세한 내용은 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)를 참조하십시오.|  
|예|예|`Dim qty  As Integer = 5`|이니셜라이저의 데이터 형식이 지정된 데이터 형식으로 변환되지 않으면 컴파일 타임 오류가 발생합니다.|  
  
## Option Strict 문이 없는 경우  
 소스 코드에 `Option Strict` 문이 없으면 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)의 **Option strict** 설정이 사용됩니다.  **페이지 컴파일**에는 오류를 생성하는 조건에 대해 추가 제어를 제공하는 설정이 있습니다.  
  
 명령줄 컴파일러를 사용 중이면 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용하여 `Option Strict`에 대한 설정을 지정할 수 있습니다.  
  
### IDE에서 Option Strict를 설정하려면  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **컴파일** 탭에서 **Option Strict** 상자의 값을 설정합니다.  
  
###  <a name="conditions"></a> IDE에서 경고 구성을 설정하려면  
 `Option Strict` 문 대신 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)를 사용할 경우 오류가 발생한 조건에 대한 추가 제어 기능이 있습니다.  **컴파일 페이지**의 **경고 구성** 섹션에는 `Option Strict`이 설정되어 있는 경우 컴파일 타임 오류를 유발하는 세 가지 조건에 해당하는 설정이 있습니다.  이러한 설정은 다음과 같습니다.  
  
-   **암시적 변환**  
  
-   **런타임에 바인딩; 런타임에 호출이 실패할 수 있습니다.**  
  
-   **암시적 형식; 개체로 간주**  
  
 **Option Strict**를 **설정**으로 설정하면 이 경고 구성 설정 중 3개 항목이 모두 **오류**로 설정됩니다.  **Option Strict**를 **Off**로 설정하면 모든 설정이 **None**으로 설정됩니다.  
  
 각 경고 구성 설정을 **없음**, **경고** 또는 **오류**로 개별적으로 변경할 수 있습니다.  세 가지 경고 구성 설정 모두 **오류**로 설정된 경우 `Option strict` 상자에 `On`이 나타납니다.  세 개 모두 **없음**으로 설정된 경우 이 상자에 `Off`가 나타납니다.  이러한 설정의 다른 조합에 대해서는 **\(사용자 지정\)**이 나타납니다.  
  
### 새 프로젝트의 Option Strict 기본 설정을 설정하려면  
 프로젝트를 만들면 **컴파일** 탭의 **Option Strict** 설정이 **옵션** 대화 상자의 **Option Strict** 설정 값으로 설정됩니다.  
  
 이 대화 상자에서 `Option Strict`를 설정하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**의 최초 기본 설정은 `Off`입니다.  
  
### 명령줄에서 Option Strict를 설정하려면  
 **vbc** 명령에 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 포함합니다.  
  
## 예제  
 다음 예제는 축소 변환인 암시적 형식 변환에 의해 발생한 컴파일 타임 오류를 보여 줍니다.  이 오류 범주는 **컴파일 페이지**의 **암시적 변환**에 해당합니다.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 런타임에 바인딩하여 발생한 컴파일 타임 오류를 보여 줍니다.  이 오류 범주는 **컴파일 페이지**에서 **런타임 바인딩; 호출이 실패할 수 있음** 조건에 해당합니다.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## 예제  
 다음 예제는 `Object`의 암시적 형식으로 선언한 변수에 의해 발생한 오류를 보여 줍니다.  이 오류 범주는 **컴파일 페이지**의 **암시적 형식; 개체로 간주**에 해당합니다.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## 참고 항목  
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [How to: Access Members of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Office 솔루션에서 런타임에 바인딩](/office-dev/office-dev/late-binding-in-office-solutions)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)