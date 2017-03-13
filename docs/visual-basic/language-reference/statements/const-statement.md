---
title: "Const Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Const statement [Visual Basic]"
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Const Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 상수를 선언하고 정의합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## 요소  
 `attributelist`  
 선택적 요소.  이 문에서 선언된 모든 상수에 적용되는 특성 목록입니다.  꺾쇠 괄호\("`<`" 및 "`>`"\)로 묶인 [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.  
  
 `accessmodifier`  
 선택적 요소.  이러한 상수에 액세스할 수 있는 코드를 지정합니다.  [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend` 또는 [Private](../../../visual-basic/language-reference/modifiers/private.md)이 될 수 있습니다.  
  
 `Shadows`  
 선택적 요소.  기본 클래스에서 프로그래밍 요소를 다시 선언하고 숨깁니다.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.  
  
 `constantlist`  
 필수 요소.  이 문에서 선언되는 상수 목록입니다.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 각 `constant`의 구문과 구성 요소는 다음과 같습니다.  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|파트|설명|  
|--------|--------|  
|`constantname`|필수 요소.  상수의 이름으로,  자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`datatype`|`Option Strict`가 `On`이면 필수적 요소입니다.  상수의 데이터 형식으로,|  
|`initializer`|필수 요소.  컴파일 타임에 계산되고 상수에 할당되는 식입니다.|  
  
## 설명  
 응용 프로그램에서 변경되지 않는 값이 있는 경우 명명된 상수를 정의하여 리터럴 값 대신 사용할 수 있습니다.  이름이 값보다 기억하기 쉽습니다.  상수를 한 번만 정의하여 코드의 여러 위치에서 사용할 수 있습니다.  이후 버전에서 해당 값을 다시 정의해야 할 경우에는 `Const` 문만 변경하면 됩니다.  
  
 모듈 또는 프로시저 수준에서만 `Const`를 사용할 수 있습니다.  즉, 변수에 대한 *선언 컨텍스트*는 클래스, 구조체, 모듈, 프로시저 또는 블록이어야 하며 소스 파일, 네임스페이스 또는 인터페이스일 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 프로시저 내의 지역 상수는 기본적으로 공용 액세스이며 이러한 지역 상수에 액세스 한정자를 사용할 수 없습니다.  모든 프로시저 외부의 클래스 및 모듈 멤버 상수는 기본적으로 전용 액세스이며 구조체 멤버 상수는 기본적으로 공용 액세스입니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** 모든 프로시저 외부의 모듈 수준에서 선언되는 상수는 *멤버 상수*입니다. 이 상수는 해당 상수를 선언하는 클래스, 구조체 또는 모듈의 멤버입니다.  
  
     프로시저 수준에서 선언되는 상수는 *지역 상수*입니다. 이 상수는 해당 상수를 선언하는 프로시저 또는 블록에 대해 지역적으로 설정됩니다.  
  
-   **특성** 지역 상수가 아닌 멤버 상수에만 특성을 적용할 수 있습니다.  특성은 정보를 어셈블리 메타데이터에 제공하므로 지역 상수와 같은 임시 저장소에는 의미가 없습니다.  
  
-   **한정자.** 기본적으로 모든 상수는 `Shared`, `Static` 및 `ReadOnly`입니다.  상수를 선언하는 경우 이러한 키워드를 사용할 수 없습니다.  
  
     프로시저 수준에서 `Shadows` 또는 액세스 한정자를 사용하여 로컬 상수를 선언할 수 없습니다.  
  
-   **여러 상수.** 동일한 선언문에서 여러 개의 상수를 선언하여 각각에 대해 `constantname` 구성 요소를 지정할 수 있습니다.  상수가 여러 개 있으면 쉼표로 구분됩니다.  
  
## 데이터 형식 규칙  
  
-   **데이터 형식.** `Const` 문은 변수의 데이터 형식을 선언할 수 있습니다.  열거형의 이름 또는 모든 데이터 형식을 지정할 수 있습니다.  
  
-   **기본 형식.** `datatype`을 지정하지 않는 경우 상수는 `initializer`의 데이터 형식을 사용합니다.  `datatype`과 `initializer`를 모두 지정하는 경우 `initializer`의 데이터 형식이 `datatype`으로 변환될 수 있어야 합니다.  `datatype`이나 `initializer`가 모두 없으면 데이터 형식의 기본값으로 `Object`가 사용됩니다.  
  
-   **다른 형식.** 선언하는 각 변수에 대해 개별 `As` 절을 사용하여 상수별로 서로 다른 데이터 형식을 지정할 수 있습니다.  그러나 공통 `As` 절을 사용하여 여러 상수를 같은 형식으로 선언할 수는 없습니다.  
  
-   **초기화.** `constantlist`에서 모든 상수 값을 초기화해야 합니다.  `initializer`를 사용하여 상수에 할당될 식을 제공할 수 있습니다.  이 식은 리터럴, 이미 정의된 다른 상수 및 이미 정의된 열거형 멤버의 조합으로 구성될 수 있습니다.  산술 연산자와 논리 연산자를 사용하여 이러한 요소를 조합할 수 있습니다.  
  
     `initializer`에는 변수나 함수를 사용할 수 없습니다.  그러나 `CByte`나 `CShort`와 같은 변환 키워드는 사용할 수 있습니다.  `String` 상수나 `Char` 인수를 사용하여 호출할 경우에는 컴파일 타임에 계산되므로 `AscW`도 사용할 수 있습니다.  
  
## 동작  
  
-   **범위.** 지역 상수는 해당 프로시저 또는 블록에서만 액세스할 수 있습니다.  멤버 상수는 클래스, 구조체 또는 모듈 모두에서 액세스할 수 있습니다.  
  
-   **한정자.** 클래스, 구조체 또는 모듈 외부에 있는 코드는 해당 클래스, 구조체 또는 모듈의 이름으로 멤버 상수의 이름을 한정해야 합니다.  프로시저 또는 블록 외부에 있는 코드는 해당 프로시저 또는 블록에 있는 로컬 상수를 참조할 수 없습니다.  
  
## 예제  
 다음 예제에서는 `Const` 문을 사용하여 리터럴 값 대신 사용할 상수를 선언합니다.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## 예제  
 `Object` 데이터 형식이 있는 상수를 정의하면 Visual Basic 컴파일러에서 `Object` 대신 `initializer`의 형식을 제공합니다.  이 예제에서 `naturalLogBase` 상수는 `Decimal` 런타임 형식을 가집니다.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 앞의 예제에서는 `CStr`를 사용하여 <xref:System.Type>을 `String`으로 변환할 수 없으므로 [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md)에서 반환된 <xref:System.Type> 개체에 <xref:System.Type.ToString%2A> 메서드를 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Constants and Enumerations](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)