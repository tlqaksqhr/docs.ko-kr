---
title: "Troubleshooting Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Char data type, converting"
  - "Decimal data type, conversions"
  - "data types [Visual Basic], troubleshooting"
  - "literals, default types"
  - "type characters, literal"
  - "Mod operator [Visual Basic], in floating-point operations"
  - "troubleshooting Visual Basic, data types"
  - "troubleshooting data types"
  - "floating-point numbers, precision"
  - "Boolean data type, converting"
  - "literal types"
  - "literal type characters"
  - "floating-point numbers, imprecision"
  - "String data type, converting"
  - "floating-point numbers, comparison"
  - "floating-point numbers"
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Troubleshooting Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 페이지에서는 내장 데이터 형식에 대한 작업을 수행할 때 발생할 수 있는 일반적인 문제를 보여 줍니다.  
  
## 동일한 것으로 간주되지 않는 부동 소수점 식  
 부동 소수점 숫자\([Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) 및 [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)\)로 작업하는 경우 숫자는 이진 소수로 저장됩니다.  즉, 부동 소수점 숫자는 이진 소수\(k \/ \(2 ^ n\) 형식, 여기서 k 및 n은 정수임\)가 아닌 정확한 수량으로 표시될 수 없습니다.  예를 들어, 0.5\(\= 1\/2\)와 0.3125\(\= 5\/16\)는 정밀한 값이지만 0.2\(\= 1\/5\)와 0.3\(\= 3\/10\)은 근사값입니다.  
  
 이러한 부정확성으로 인해 부동 소수점 값으로 작업할 때 정확한 결과를 사용할 수 없습니다.  특히, 이론적으로 동일한 두 값이 약간 다르게 표시될 수 있습니다.  
  
||  
|-|  
|부동 소수점 수량을 비교하려면|  
|1.  <xref:System> 네임스페이스에서 <xref:System.Math> 클래스의 <xref:System.Math.Abs%2A> 메서드를 사용하여 해당 차이의 절대 값을 계산합니다.<br />2.  두 수량의 차이가 해당 값보다 더 크지 않을 경우 두 수량이 같은 것으로 간주하도록 허용 가능한 최대 차이를 결정합니다.<br />3.  차이의 절대 값을 허용 가능한 차이와 비교합니다.|  
  
 다음 예제에서는 두 `Double` 값에 대한 올바르지 않은 비교와 올바른 비교를 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 앞의 예제에서는 <xref:System.Double> 구조체의 <xref:System.Double.ToString%2A> 메서드를 사용하므로 `CStr` 키워드를 사용할 때보다 더 정확하게 지정할 수 있습니다.  기본값은 15자리지만 "G17" 형식에서는 기본값이 17자리로 확대됩니다.  
  
## 정확한 결과를 반환하지 않는 Mod 연산자  
 부동 소수점 저장의 부정확성으로 인해 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)는 하나 이상의 피연산자가 부동 소수점인 경우 예기치 않은 결과를 반환할 수 있습니다.  
  
 [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)은 부동 소수점 표현을 사용하지 않습니다.  `Single` 및 `Double`에서는 정확하지 않는 숫자가 `Decimal`에서는 정확하게 표시되는 경우가 있습니다\(예: 0.2, 0.3\).  `Decimal`에서는 부동 소수점에서보다 산술 연산이 더 느리지만 더 정확한 결과가 나타나므로 성능 감소를 감내할 만한 가치가 있습니다.  
  
||  
|-|  
|부동 소수점 수량의 정수 나머지를 찾으려면|  
|1.  변수를 `Decimal`로 선언합니다.<br />2.  리터럴 값이 `Long` 데이터 형식에 비해 너무 큰 경우 `D` 리터럴 형식 문자를 사용하여 `Decimal`에 리터럴을 적용합니다.|  
  
 다음 예제에서는 부동 소수점 피연산자의 잠재적인 부정확성에 대해 설명합니다.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 앞의 예제에서는 <xref:System.Double> 구조체의 <xref:System.Double.ToString%2A> 메서드를 사용하므로 `CStr` 키워드를 사용할 때보다 더 정확하게 지정할 수 있습니다.  기본값은 15자리지만 "G17" 형식에서는 기본값이 17자리로 확대됩니다.  
  
 `zeroPointTwo`는 `Double`이므로 0.2에 대한 값은 무한 반복되는 이진 소수이며 저장된 값은 0.20000000000000001입니다.  2.0을 이 수로 나누면 몫이 9.9999999999999995이고 나머지는 0.19999999999999991입니다.  
  
 `decimalRemainder`에 대한 식에서 `D` 리터럴 형식 문자는 `Decimal`에 두 피연산자를 모두 적용하므로 0.2로 정확하게 표시됩니다.  따라서 `Mod` 연산자는 예상한 나머지 0.0을 반환합니다.  
  
 `decimalRemainder`를 `Decimal`로 선언하는 것만으로는 충분하지 않습니다.  리터럴을 `Decimal`에 적용하거나 `Double`을 기본값으로 사용하여 `decimalRemainder`가 `doubleRemainder`와 동일한 정확도의 값을 받아야 합니다.  
  
## 숫자 형식으로 정확하게 변환되지 않는 부울 형식  
 [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값은 숫자로 저장되지 않고 저장된 값은 숫자가 아닙니다.  이전 버전과의 호환성을 위해 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `Boolean` 형식과 숫자 형식 간에 변환할 수 있도록 변환 키워드\([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt` 등\)를 제공합니다.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 메서드를 수행할 때처럼 이러한 변환은 언어마다 다르게 수행될 수 있습니다.  
  
 `True`와 `False`를 숫자 값으로 나타내도록 코드를 작성하지 마십시오.  `Boolean` 변수에는 가능하면 원래 용도에 맞는 논리 값이 사용되도록 제한해야 합니다.  `Boolean`과 숫자 값을 혼합해야 하는 경우에는 선택한 변환 메서드를 알고 있어야 합니다.  
  
### 변환\(Visual Basic\)  
 `CType` 또는 `CBool` 변환 키워드를 사용하여 숫자 데이터 형식을 `Boolean`으로 변환하는 경우 0은 `False`가 되고 다른 모든 값은 `True`가 됩니다.  변환 키워드를 사용하여 `Boolean` 값을 숫자 형식으로 변환하는 경우 `False`는 0이 되고 `True`는 \-1이 됩니다.  
  
### 변환\(Framework\)  
 <xref:System> 네임스페이스에서 <xref:System.Convert> 클래스의 <xref:System.Convert.ToInt32%2A> 메서드는 `True`를 \+1로 변환합니다.  
  
 `Boolean` 값을 숫자 데이터 형식으로 변환해야 하는 경우 변환 메서드를 주의하여 사용하십시오.  
  
## 컴파일러 오류를 생성하는 문자 리터럴  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 형식 문자가 없는 경우 리터럴에 대한 기본 데이터 형식을 사용합니다.  큰따옴표\(`" "`\)로 묶인 문자 리터럴의 기본 형식은 `String`입니다.  
  
 `String` 데이터 형식은 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)으로 확대 변환되지 않습니다.  즉, 리터럴을 `Char` 변수에 할당하려면 축소 변환을 사용하거나 리터럴을 `Char` 형식에 적용해야 합니다.  
  
||  
|-|  
|문자 리터럴을 만들어 변수 또는 상수에 할당하려면|  
|1.  변수 또는 상수를 `Char`로 선언합니다.<br />2.  문자 값을 큰따옴표\(`" "`\)로 묶습니다.<br />3.  닫는 큰따옴표 뒤에 `C` 리터럴 형식 문자를 입력하여 리터럴을 `Char`에 적용합니다.  이는 형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 `On`인 경우에 필수적이며 모든 경우에 이렇게 하는 것이 좋습니다.|  
  
 다음 예제에서는 리터럴을 `Char` 변수에 할당한 경우와 할당하지 못한 경우를 보여 줍니다.  
  
 [!CODE [VbVbalrStatements#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#49)]  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/troubleshooting-data-types_4.vb)]  
  
 축소 변환은 런타임에서 실패할 수 있기 때문에 항상 위험이 따릅니다.  예를 들어, `String` 값에 두 개 이상의 문자가 포함되어 있는 경우 `String`을 `Char`로 변환할 수 없습니다.  따라서 `C` 형식 문자를 사용하도록 프로그래밍하는 것이 더 좋습니다.  
  
## 런타임에 문자열 변환 실패  
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)은 확대 변환에 거의 사용되지 않습니다.  `String`은 문자열 자체와 `Object`로만 확대 변환되고 `Char` 및 `Char()`\(`Char` 배열\)만 `String`으로 확대 변환됩니다.  이는 `String` 변수와 상수에 다른 데이터 형식에서 사용할 수 없는 값이 포함될 수 있기 때문입니다.  
  
 형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 `On`인 경우 컴파일러에서는 모든 암시적 축소 변환을 허용하지 않습니다.  여기에는 `String`을 포함하는 변환도 포함됩니다.  이 경우에도 코드에서는 `CStr` 및 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)와 같은 변환 키워드를 사용하여 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]에게 변환 시도를 지시할 수 있습니다.  
  
> [!NOTE]
>  `For Each…Next` 컬렉션의 요소에서 루프 제어 변수로의 변환에 대한 축소 변환 오류는 표시되지 않습니다.  자세한 내용 및 예제는 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)의 "축소 변환" 단원을 참조하십시오.  
  
### 축소 변환 보호  
 축소 변환 시 런타임에 실패할 수 있습니다.  예를 들어, "True" 또는 "False" 이외의 값을 포함하는 `String` 변수는 `Boolean`으로 변환될 수 없으며  구두점 문자를 포함하는 String 변수는 숫자 형식으로 변환되지 않습니다.  `String` 변수가 대상 형식에 사용할 수 있는 값만 포함하는지 확실히 알 수 없다면 변환을 시도하지 마십시오.  
  
 `String`에서 다른 데이터 형식으로 변환해야 하는 경우에는 시도된 변환을 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)으로 묶는 것이 가장 안전합니다.  이렇게 하면 런타임 실패를 직접 처리할 수 있습니다.  
  
### 문자 배열  
 단일 `Char`와 `Char` 요소 배열은 모두 `String`으로 확대 변환되지만  `String`은 `Char()`로 확대 변환되지 않습니다.  `String` 값을 `Char` 배열로 변환하려면 <xref:System.String?displayProperty=fullName> 클래스의 <xref:System.String.ToCharArray%2A> 메서드를 사용합니다.  
  
### 의미 없는 값  
 일반적으로 `String` 값은 다른 데이터 형식에서는 의미가 없으므로 이를 변환하는 것은 매우 부적절하며 위험합니다.  가능하면 `String` 변수는 이 변수를 사용하도록 디자인된 문자 시퀀스에서만 사용하도록 합니다.  해당 값을 다른 형식으로 사용하는 코드를 작성하지 마십시오.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)