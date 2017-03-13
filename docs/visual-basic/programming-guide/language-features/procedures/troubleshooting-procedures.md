---
title: "Troubleshooting Procedures (Visual Basic) | Microsoft Docs"
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
  - "troubleshooting Visual Basic, procedures"
  - "procedures, troubleshooting"
  - "Visual Basic code, procedures"
  - "troubleshooting procedures"
  - "procedures, about procedures"
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Troubleshooting Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 페이지에서는 프로시저 작업 중 발생할 수 있는 일반적인 문제를 보여 줍니다.  
  
## 함수 프로시저에서 배열 형식 반환  
 `Function` 프로시저가 배열 데이터 형식을 반환하는 경우 `Function` 이름을 사용하여 값을 배열 요소에 저장할 수 없습니다.  값을 배열 요소에 저장할 경우 컴파일러에서는 이 동작을 `Function` 호출로 해석합니다.  다음 예제에서는 컴파일러 오류가 생성됩니다.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 `allOnes(i) = 1` 문은 잘못된 데이터 형식 인수\(`Integer` 배열 대신 singleton `Integer`\)를 사용하여 `allOnes`를 호출하기 때문에 컴파일러 오류를 생성합니다.  `Return allOnes()` 문은 인수를 사용하지 않고 `allOnes`를 호출하기 때문에 컴파일러 오류를 생성합니다.  
  
 **해결 방법:** 반환될 배열 요소를 수정하려면 내부 배열을 지역 변수로 정의합니다.  다음 예제에서는 오류 없이 컴파일합니다.  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## 프로시저 호출에 의해 인수가 수정되지 않음  
 프로시저에서 호출 코드의 내부 인수로 사용하는 프로그래밍 요소를 변경하려면 해당 인수를 참조로 전달해야 합니다.  프로시저는 해당 인수를 값으로 전달하더라도 참조 형식 인수의 요소에 액세스할 수 있습니다.  
  
-   **내부 변수**.  프로시저에서 내부 변수 요소의 값을 바꾸려면 프로시저에서 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수를 선언해야 합니다.  또한, 호출 코드에서 인수를 괄호로 묶으면 `ByRef` 전달 메커니즘이 재정의되기 때문에 인수를 괄호로 묶지 마십시오.  
  
-   **참조 형식 요소**.  [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 매개 변수를 선언하면 프로시저가 내부 변수 요소를 수정할 수 없습니다.  그러나 인수가 참조 형식인 경우에는 프로시저가 변수 값은 바꿀 수 없지만 인수가 가리키는 개체의 멤버는 수정할 수 있습니다.  예를 들어, 인수가 배열 변수인 경우 프로시저가 여기에 새 배열을 할당할 수는 없지만 해당 요소를 하나 이상 변경할 수 있습니다.  변경된 요소는 호출 코드의 내부 배열 변수에 리플렉션됩니다.  
  
 다음 예제에서는 배열 변수를 값으로 받아 해당 요소를 변경하는 두 프로시저를 정의합니다.  `increase` 프로시저는 각 요소에 1을 더합니다.  `replace` 프로시저는 매개 변수 `a()`에 새 배열을 할당한 다음 각 요소에 1을 더합니다.  그러나 `a()`가 `ByVal`로 선언되기 때문에 다시 할당해도 호출 코드의 내부 배열 변수는 영향을 받지 않습니다.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 다음 예제에서는 `increase` 및 `replace`를 호출합니다.  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 첫 번째 `MsgBox` 호출에서는 "After increase\(n\): 11, 21, 31, 41"이 표시됩니다.  `n`이 참조 형식이기 때문에 `ByVal`로 전달되더라도`increase`가 해당 멤버를 변경할 수 있습니다.  
  
 두 번째 `MsgBox` 호출에서는 "After replace\(n\): 11, 21, 31, 41"이 표시됩니다.  `n`이 `ByVal`로 전달되기 때문에 `replace`가 새 배열을 할당하여 변수 `n`을 수정할 수 없습니다.  `replace`가 새 배열 인스턴스 `k`를 만들어 지역 변수 `a`에 할당하면 호출 코드가 전달한 `n`에 대한 참조가 제거됩니다.  `a`의 멤버 수를 늘리면 지역 배열 `k`만 영향을 받습니다.  
  
 **해결 방법:** 내부 변수 요소를 자동으로 수정하려면 해당 요소를 참조로 전달해야 합니다.  다음 예제에서는 `replace` 선언을 변경하여 배열을 호출 코드의 다른 배열로 바꾸는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## 오버로드를 정의할 수 없음  
 프로시저의 오버로드된 버전을 정의하려면 이름은 같지만 시그니처를 다르게 사용해야 합니다.  컴파일러에서 시그니처가 동일한 선언과 오버로드를 구별할 수 없는 경우 오류가 생성됩니다.  
  
 프로시저의 *시그니처*는 프로시저 이름과 매개 변수 목록에 의해 결정됩니다.  각 오버로드는 다른 모든 오버로드와 이름이 같아야 하지만 하나 이상의 시그니처 구성 요소가 다른 모든 오버로드와 달라야 합니다.  자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하십시오.  
  
 다음 항목은 매개 변수 목록에 포함되어 있더라도 프로시저 시그니처의 구성 요소가 아닙니다.  
  
-   `Public`, `Shared`, `Static`과 같은 프로시저 한정자 키워드  
  
-   매개 변수 이름  
  
-   `ByRef`, `Optional`과 같은 매개 변수 한정자 키워드  
  
-   반환 값의 데이터 형식\(변환 연산자는 제외\)  
  
 위 항목 중 하나 이상이 다르더라도 프로시저를 오버로드할 수 없습니다.  
  
 **해결 방법:** 프로시저 오버로드를 정의하려면 시그니처를 다르게 지정해야 합니다.  이름은 같아야 하므로 매개 변수의 수, 순서 또는 데이터 형식을 다르게 지정합니다.  제네릭 프로시저에서는 형식 매개 변수의 수를 다르게 지정할 수 있습니다.  변환 연산자\([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)\)에서는 반환 형식을 다르게 지정할 수 있습니다.  
  
### Optional 및 ParamArray 인수를 사용하여 오버로드 확인  
 하나 이상의 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를 사용하여 프로시저를 오버로딩하려면 *암시적 오버로드*가 중복되지 않도록 해야 합니다.  자세한 내용은 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)을 참조하십시오.  
  
## 오버로드된 프로시저의 잘못된 버전 호출  
 프로시저에 여러 개의 오버로드된 버전이 있는 경우 모든 해당 버전의 모든 매개 변수 목록과 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 오버로드 간의 호출을 확인하는 방법을 잘 알고 있어야 합니다.  그렇지 않으면 원하지 않은 오버로드를 호출하게 될 수 있습니다.  
  
 호출할 오버로드를 결정한 경우 다음 규칙을 주의해서 확인하십시오.  
  
-   정확한 수의 인수를 올바른 순서로 제공합니다.  
  
-   인수의 데이터 형식이 해당 매개 변수의 데이터 형식과 정확히 일치하는 것이 가장 좋습니다.  어떤 경우이든 각 인수의 데이터 형식이 해당 매개 변수의 데이터 형식으로 확대 변환되어야 합니다.  [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)이 `Off`로 설정되어 있는 경우에도 마찬가지입니다.  인수 목록에서의 축소 변환이 필요한 오버로드는 호출할 수 없습니다.  
  
-   확대 변환이 필요한 인수를 호출하는 경우 데이터 형식을 해당 매개 변수의 데이터 형식과 최대한 유사한 형식으로 지정해야 합니다.  두 개 이상의 오버로드가 인수 데이터 형식을 받아들이는 경우 컴파일러는 가장 적게 확대 변환하여 호출할 수 있는 오버로드에 대한 호출을 확인합니다.  
  
 인수를 준비할 때 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 키워드를 사용하면 데이터 형식 불일치 가능성을 줄일 수 있습니다.  
  
### 오버로드 확인 실패  
 오버로드된 프로시저를 호출할 때 컴파일러는 오버로드를 하나만 제외하고 모두 제거하려고 합니다.  제거에 성공하면 해당 오버로드에 대한 호출을 확인합니다.  컴파일러는 오버로드가 모두 제거되었거나 오버로드가 하나만 남지 않은 경우 오류를 생성합니다.  
  
 다음 예제는 오버로드 확인 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 첫 번째 호출에서는 첫 번째 인수\(`Short`\)가 해당 매개 변수의 형식\(`Byte`\)으로 축소되므로 컴파일러에서 첫 번째 오버로드를 제거합니다.  그런 다음 두 번째 오버로드의 각 인수 형식\(`Short`와 `Single`\)이 세 번째 오버로드의 해당 형식\(`Integer`와 `Single`\)으로 확대되므로 세 번째 오버로드를 제거합니다.  두 번째 오버로드는 덜 확대해도 되므로 컴파일러에서 이 오버로드를 호출에 사용합니다.  
  
 두 번째 호출에서는 컴파일러가 축소를 기준으로 오버로드를 제거할 수 없습니다.  인수 형식을 덜 확대해도 두 번째 오버로드를 호출할 수 있으므로 첫 번째 호출의 경우와 같은 이유로 세 번째 오버로드를 제거합니다.  그러나 컴파일러에서 첫 번째와 두 번째 오버로드 사이를 확인할 수 없습니다.  각 오버로드에는 다른 오버로드의 해당 형식으로 확대되도록 정의된 매개 변수 형식\(`Byte`에서 `Short`로, `Single`에서 `Double`로\)이 하나씩 있습니다.  따라서 컴파일러에서 오버로드 확인 오류를 생성합니다.  
  
 **해결 방법:** 오버로드된 프로시저를 명확하게 호출하려면 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)를 사용하여 인수 데이터 형식을 매개 변수 형식에 일치시킵니다.  다음 예제에서는 두 번째 오버로드를 확인하게 하는 `z` 호출을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### Optional 및 ParamArray 인수를 사용하여 오버로드 확인  
 마지막 매개 변수가 각각 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)로 선언된다는 점만 제외하고 프로시저에서 두 오버로드의 시그니처가 같은 경우 컴파일러는 가장 유사한 경우를 기준으로 프로시저에 대한 호출을 확인합니다.  자세한 내용은 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)을 참조하십시오.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)