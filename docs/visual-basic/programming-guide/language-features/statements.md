---
title: "Statements in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], declaring"
  - "colons (:)"
  - "constants, defining"
  - "underlines"
  - "constants, statements"
  - "blue underline"
  - "procedures, statements"
  - "variables [Visual Basic], assigning"
  - "line breaks, in code"
  - "executable statements"
  - "variables [Visual Basic], defining"
  - "statements [Visual Basic], about statements"
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Statements in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 문은 완전한 명령이며  키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다.  각 문은 다음 범주 중 하나에 속합니다.  
  
-   **선언문**. 변수, 상수 또는 프로시저의 이름을 지정하고 데이터 형식도 지정할 수 있습니다.  
  
-   **실행문**. 작업을 시작합니다.  이러한 문은 메서드나 함수를 호출할 수 있으며 코드 블록에서 반복하거나 분기할 수 있습니다.  실행문은 값 또는 식을 변수나 상수에 할당하는 **할당문**을 포함합니다.  
  
 이 항목에서는 각 범주에 대해 설명합니다.  또한 한 줄에 여러 문을 결합하는 방법과 하나의 문을 여러 줄에 표시하는 방법에 대해 설명합니다.  
  
## 선언문  
 선언문을 사용하여 프로시저, 변수, 속성, 배열 및 상수를 정의하고 이름을 지정할 수 있습니다.  프로그래밍 요소를 선언할 때는 해당 데이터 형식, 액세스 수준 및 범위도 정의할 수 있습니다.  자세한 내용은 [Declared Element Characteristics](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)을 참조하십시오.  
  
 다음 예제에는 세 가지 선언이 포함되어 있습니다.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 첫 번째 선언은 `Sub` 문입니다.  짝이 되는 `End Sub` 문과 함께 해당 문은 `applyFormat`이라는 프로시저를 선언합니다.  또한 `applyFormat`을 `Public`으로 지정하며 이는 해당 프로시저를 참조할 수 있는 모든 코드에서 이 프로시저를 호출할 수 있음을 의미합니다.  
  
 두 번째 선언은 `Const` 문이며 `limit` 상수를 선언하여 `Integer` 데이터 형식과 값 33을 지정합니다.  
  
 세 번째 선언은 `Dim` 문이며 `thisWidget` 변수를 선언합니다.  데이터 형식은 특정 개체 즉, `Widget` 클래스에서 생성된 개체입니다.  현재 사용 중인 응용 프로그램에 노출된 모든 기본 데이터 형식이나 개체 형식으로 변수를 선언할 수 있습니다.  
  
### 초기 값  
 선언문을 포함하는 코드를 실행하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 선언된 요소에 필요한 메모리를 예약합니다.  요소에 값이 있는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 해당 값을 해당 데이터 형식의 기본값으로 초기화합니다.  자세한 내용은 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)의 "동작"을 참조하십시오.  
  
 다음 예제와 같이 선언의 일부로 초기 값을 변수에 할당할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 변수가 개체 변수인 경우 다음 예제와 같이 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 사용하여 선언하면 해당 클래스의 인스턴스를 명시적으로 만들 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 선언문에서 지정한 초기 값은 실행이 해당 선언문에 도달하기 전에는 변수에 할당되지 않으며  변수는 값을 할당 받기 전까지 해당 데이터 형식에 대한 기본값을 포함합니다.  
  
## 실행문  
 실행문은 작업을 실행합니다.  프로시저 호출, 코드에서 다른 위치로 분기, 여러 문 순환, 식 계산 등을 수행할 수 있습니다.  할당문은 실행문의 특수한 경우입니다.  
  
 다음 예제에서는 `If...Then...Else` 제어 구조를 사용하여 변수 값을 기반으로 다른 코드 블록을 실행합니다.  코드의 각 블록 내에서 `For...Next` 루프는 지정된 횟수만큼 실행됩니다.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 위의 예제에서 `If` 문은 `clockwise` 매개 변수의 값을 확인합니다.  값이 `True`이면 `aWidget`의 `spinClockwise` 메서드를 호출하고  값이 `False`이면 `aWidget`의 `spinCounterClockwise` 메서드를 호출합니다.  `If...Then...Else` 제어 구조는 `End If`로 끝납니다.  
  
 각 블록 내의 `For...Next` 루프는 `revolutions` 매개 변수 값과 같은 횟수만큼 해당 메서드를 호출합니다.  
  
## 할당문  
 할당문은 할당 연산을 수행합니다. 다음 예제에서와 같이 할당 연산은 할당 연산자\(`=`\)의 오른쪽에 있는 값을 왼쪽에 있는 요소에 저장합니다.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 위의 예제에서 할당문은 리터럴 값 42를 변수 `v`에 저장합니다.  
  
### 적합한 프로그래밍 요소  
 할당 연산자의 왼쪽에 있는 프로그래밍 요소는 값을 받아 저장할 수 있어야 합니다.  즉, [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 아닌 변수나 속성 또는 배열 요소여야 합니다.  할당문의 컨텍스트에서 이러한 요소의 "왼쪽 값"을 *lvalue*라고도 합니다.  
  
 할당 연산자의 오른쪽에 있는 값은 식에 의해 생성되며 이러한 값은 리터럴, 상수, 변수, 속성, 배열 요소, 기타 식 또는 함수 호출의 조합이 될 수 있습니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 위의 예제에서는 `y` 변수에 저장된 값을 `z` 변수에 저장된 값에 추가한 다음 호출에서 반환된 값을 `findResult` 함수에 추가합니다.  그런 다음 이 식의 전체 값을 `x` 변수에 저장합니다.  
  
### 할당문의 데이터 형식  
 다음 예제에서와 같이 할당 연산자는 숫자 값 외에 `String` 값도 할당할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 또한 다음 예제에서와 같이 `Boolean` 리터럴 또는 `Boolean` 식을 사용하여 `Boolean` 값을 할당할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 마찬가지로 `Char`, `Date` 또는 `Object` 데이터 형식의 프로그래밍 요소에 적절한 값을 할당할 수 있습니다.  또한 인스턴스가 만들어진 클래스로 선언된 요소에 개체 인스턴스를 할당할 수 있습니다.  
  
### 복합 할당문  
 *복합 할당문*은 식을 프로그래밍 요소에 할당하기 전에 먼저 해당 식에 대해 연산을 수행합니다.  다음 예제에서는 이러한 연산자 중 하나인 `+=` 연산자를 보여 줍니다. 이 연산자는 오른쪽에 있는 식의 값을 기준으로 연산자의 왼쪽에 있는 변수의 값을 증가시킵니다.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 위의 예제에서는 `n` 값에 1을 더한 다음 새 값을 `n`에 저장합니다.  이것은 다음 문과 동일합니다.  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 이 형식의 연산자를 사용하여 다양한 복합 할당 연산을 수행할 수 있습니다.  이러한 연산자에 대한 자세한 내용 및 목록은 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)를 참조하십시오.  
  
 다음 예제에서와 같이 기존에 이미 있는 문자열의 끝에 문자열을 추가하는 경우 연결 할당 연산자\(`&=`\)가 유용합니다.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### 할당문의 형식 변환  
 변수, 속성 또는 배열 요소에 할당하는 값은 해당 대상 요소에 적합한 데이터 형식이어야 합니다.  일반적으로 대상 요소의 데이터 형식과 동일한 데이터 형식의 값을 생성하는 것이 좋습니다.  그러나 일부 형식은 할당을 수행하는 동안 다른 형식으로 변환될 수 있습니다.  
  
 데이터 형식 변환에 대한 자세한 내용은 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)을 참조하십시오.  간단히 요약하면, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 지정된 형식의 값을 해당 형식이 확대 변환되는 다른 형식으로 변환합니다.  *확대 변환*은 런타임에 항상 성공하며 이로 인해 데이터가 손실되지 않습니다.  예를 들어, `Integer`가 `Double`로 확대 변환되므로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 해당되는 경우 `Integer` 값을 `Double`로 확대 변환합니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
 *축소 변환*\(확대 변환되지 않는 변환\)은 런타임에 실패할 수 있으며 이로 인해 데이터가 손실될 수 있습니다.  형식 변환 함수를 사용하여 명시적으로 축소 변환을 수행하거나 `Option Strict Off`를 설정하여 컴파일러가 모든 변환을 암시적으로 수행하도록 할 수 있습니다.  자세한 내용은 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)을 참조하십시오.  
  
## 한 줄에 여러 개의 문 삽입  
 콜론\(`:`\) 문자로 구분하여 한 줄에 여러 개의 문을 포함할 수 있습니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 이런 형식의 구문을 사용하면 편리할 때도 있지만 코드를 읽고 유지 관리하기가 어려워집니다.  따라서 한 줄에 한 개의 문을 두는 것이 좋습니다.  
  
## 여러 줄에 하나의 문 계속  
 일반적으로 문은 한 줄에 맞지만 문이 너무 긴 경우에는 줄 연속 시퀀스를 사용하여 다음 줄에서 문을 계속 작성할 수 있습니다. 줄 연속 시퀀스는 공백, 밑줄\(`_`\), 캐리지 리턴 순으로 구성되어 있습니다.  다음 예제에서 `MsgBox` 실행문은 두 줄에 걸쳐 계속됩니다.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### 암시적 줄 연속  
 대부분의 경우 밑줄 문자\(\_\)를 사용하지 않아도 연속된 다음 줄에서 문을 계속할 수 있습니다.  다음 표에서는 암시적으로 다음 코드 줄에서 문을 계속하는 구문 요소를 나열합니다.  
  
|||  
|-|-|  
|구문 요소|예제|  
|쉼표\(`,`\) 뒤|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|여는 괄호\(`(`\) 뒤 또는 닫는 괄호\(`)`\) 앞|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|여는 중괄호\(`{`\) 뒤 또는 닫는 중괄호\(`}`\) 앞|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> 자세한 내용은 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하십시오.|  
|XML 리터럴 내에서 포함 식 열기\(`<%=`\) 뒤 또는 포함 식 닫기\(`%>`\) 앞|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> 자세한 내용은 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조하십시오.|  
|연결 연산자\(`&`\) 뒤|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> 자세한 내용은 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)을 참조하십시오.|  
|할당 연산자\(`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`\) 뒤|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> 자세한 내용은 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)을 참조하십시오.|  
|식 내에서 이항 연산자\(`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`\) 뒤|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> 자세한 내용은 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)을 참조하십시오.|  
|`Is` 및 `IsNot` 연산자 뒤|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> 자세한 내용은 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)을 참조하십시오.|  
|멤버 한정자 문자\(`.`\) 뒤와 멤버 이름 앞.  그러나 `With` 문을 사용하거나 형식에 대해 초기화 목록의 값을 제공하는 경우에는 멤버 한정자 문자 뒤에 줄 연속 문자\(\_\)를 포함해야 합니다.  `With` 문이나 개체 초기화 목록을 사용하는 경우 할당 연산자\(예: `=`\) 뒤에서 줄 바꿈하는 것이 좋습니다.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> 자세한 내용은 [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) 또는 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조하십시오.|  
|XML 축 속성 한정자\(`.`, `.@` 또는 `...`\) 뒤.  그러나 `With` 키워드를 사용하는 경우에는 멤버 한정자를 지정할 때 줄 연속 문자\(\_\)를 포함해야 합니다.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> 자세한 내용은 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)을 참조하십시오.|  
|특성을 지정하는 경우 보다 작음 기호\(\<\) 뒤 또는 보다 큼 기호\(`>`\) 앞.  특성을 지정하는 경우 보다 큼 기호\(`>`\) 뒤에도 적용됩니다.  그러나 어셈블리 수준 특성이나 모듈 수준 특성을 지정하는 경우에는 줄 연속 문자\(\_\)를 포함해야 합니다.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> 자세한 내용은 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.|  
|쿼리 연산자\(`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending` 및 `Descending`\) 앞과 뒤.  여러 키워드로 구성된 쿼리 연산자\(`Order By`, `Group Join`, `Take While` 및 `Skip While`\)의 키워드 사이에서는 줄 바꿈할 수 없습니다.|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> 자세한 내용은 [Queries](../../../visual-basic/language-reference/queries/queries.md)를 참조하십시오.|  
|`For Each` 문의 `In` 키워드 뒤|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> 자세한 내용은 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)을 참조하십시오.|  
|컬렉션 이니셜라이저의 `From` 키워드 뒤|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> 자세한 내용은 [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하십시오.|  
  
## 주석 추가  
 소스 코드가 항상 코드 자체만으로 충분한 설명이 되는 것은 아닙니다. 이는 코드를 작성한 프로그래머에게도 마찬가지입니다.  따라서 코드를 좀 더 상세히 설명하기 위해 대부분의 프로그래머들은 주석을 삽입합니다.  코드 내에 주석을 포함하면 나중에 해당 코드에서 읽기 및 기타 작업을 수행하는 모든 사용자가 프로시저 또는 특정 명령을 이해할 수 있습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 컴파일하는 동안 주석이 무시되어 컴파일된 코드에 영향을 주지 않습니다.  
  
 주석 줄은 아포스트로피\(`'`\) 또는 `REM`으로 시작하며 바로 뒤에 공백이 옵니다.  주석 줄은 문자열 내를 제외하고 코드 내 임의의 위치에 추가할 수 있습니다.  문에 주석을 추가하려면 문 뒤에 아포스트로피나 `REM`을 삽입한 다음 주석을 삽입합니다.  또한 주석을 별도의 줄에 둘 수도 있습니다.  다음 예제에서는 이러한 예를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## 컴파일 오류 검사  
 코드 줄을 입력한 다음 이 줄이 파란색 물결선으로 표시되면\(오류 메시지도 나타날 수 있음\) 해당 문에 구문 오류가 있는 것입니다.  이 경우 작업 목록을 검토하거나 마우스 포인터로 오류를 가리켜 나타나는 오류 메시지를 읽는 방법으로 문에 어떤 문제가 있는지 찾은 다음 이를 해결해야 합니다.  코드의 모든 구문 오류를 수정하기 전에는 프로그램이 제대로 컴파일되지 않습니다.  
  
## 관련 단원  
  
|||  
|-|-|  
|용어|정의|  
|[Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)|`=`, `*=`, `&=` 등의 할당 연산자를 다루는 언어 참조 페이지에 대한 링크를 제공합니다.|  
|[Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|여러 요소를 연산자와 결합하여 새 값을 산출하는 방법을 보여 줍니다.|  
|[방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|하나의 문을 여러 줄로 나누는 방법과 한 줄에 여러 문을 배치하는 방법을 보여 줍니다.|  
|[How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|코드 줄에 레이블을 지정하는 방법을 보여 줍니다.|