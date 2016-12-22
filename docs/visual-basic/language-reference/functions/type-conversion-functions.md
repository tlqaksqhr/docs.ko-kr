---
title: "Type Conversion Functions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.CUShort"
  - "vb.csng"
  - "vb.CDate"
  - "CByte"
  - "CSng"
  - "vb.CDec"
  - "CBool"
  - "CStr"
  - "vb.CULng"
  - "CDec"
  - "CVErr"
  - "CDbl"
  - "CShort"
  - "vb.CObj"
  - "vb.CVErr"
  - "CULng"
  - "vb.cdbl"
  - "vb.cbool"
  - "CObj"
  - "CDate"
  - "CLng"
  - "vb.cstr"
  - "vb.cbyte"
  - "vb.clng"
  - "vb.CChar"
  - "CUShort"
  - "vb.CUInt"
  - "vb.cint"
  - "vb.CShort"
  - "CInt"
  - "CUInt"
  - "CChar"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CDate function"
  - "CByte function"
  - "Integer data type, converting"
  - "string conversion, conversion functions"
  - "fractions"
  - "data types [Visual Basic], converting"
  - "text, converting"
  - "CDec function"
  - "Char data type, converting"
  - "type conversion, functions for"
  - "Single data type, converting"
  - "numbers, rounding"
  - "rounding numbers, type conversion"
  - "CUShort function"
  - "Long data type, converting"
  - "return values, data types"
  - "single-precision numbers, converting"
  - "data type conversion, functions for"
  - "CStr function"
  - "times, converting"
  - "CSng function"
  - "conversions, type conversion functions"
  - "CBool function"
  - "CDbl function"
  - "CUInt function"
  - "Currency data type, conversion functions"
  - "numbers, converting"
  - "Double data type, converting"
  - "CLng function"
  - "CSByte function"
  - "double-precision numbers"
  - "Decimal data type, converting"
  - "Boolean data type, converting"
  - "integers, type conversion functions"
  - "dates, converting"
  - "CULng function"
  - "CInt function"
  - "Date data type, converting"
  - "Byte data type, converting"
  - "String data type, converting"
  - "CChar function"
  - "banker's rounding"
  - "Short data type, converting"
  - "rounding numbers, banker's rounding"
  - "type conversion, Visual Basic vs. .NET Framework"
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Conversion Functions (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

형식 변환 함수는 인라인으로 컴파일됩니다. 이는 변환 코드가 식을 계산하는 코드의 일부임을 의미합니다.  경우에 따라 변환을 수행하기 위해 프로시저를 호출할 필요가 없으므로 실행 속도가 빨라집니다.  다음의 각 함수는 해당 식을 특정 데이터 형식으로 변환합니다.  
  
## 구문  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## 파트  
 `expression`  
 필수 요소.  소스 데이터 형식의 임의 식입니다.  
  
## 반환 값 데이터 형식  
 다음 표에서 볼 수 있듯이 함수가 반환하는 값의 데이터 형식은 함수 이름에 따라 결정됩니다.  
  
|함수 이름|반환 데이터 형식|`expression` 인수 범위|  
|-----------|---------------|------------------------|  
|`CBool`|[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|임의의 유효한 `Char` 또는 `String`이나 숫자 식입니다.|  
|`CByte`|[Byte Data Type](../../../visual-basic/language-reference/data-types/byte-data-type.md)|값의 범위는 0에서 255까지\(부호가 없으며 소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CChar`|[Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)|임의의 유효한 `Char` 또는 `String` 식입니다. `String`의 첫 문자만 변환되며 값의 범위는 0에서 65535까지\(부호 없음\)입니다.|  
|`CDate`|[Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)|임의의 유효한 날짜 및 시간 표시|  
|`CDbl`|[Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)|값의 범위는 \-1.79769313486231570E\+308에서 \-4.94065645841246544E\-324까지\(음수\) 또는 4.94065645841246544E\-324에서 1.79769313486231570E\+308까지\(양수\)입니다.|  
|`CDec`|[Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|소수 자릿수가 없는 숫자\(소수 부분이 없는 숫자\)의 경우 범위는 \+\/\-79,228,162,514,264,337,593,543,950,335 사이이고,  소수 자릿수가 28개인 숫자의 경우에 범위는 \+\/\-7.9228162514264337593543950335 사이이며,  0이 아닌 숫자 중 가장 작은 숫자는 0.0000000000000000000000000001\(\+\/\-1E\-28\)입니다.|  
|`CInt`|[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)|값의 범위는 \-2,147,483,648에서 2,147,483,647까지\(소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CLng`|[Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)|값의 범위는 \-9,223,372,036,854,775,808에서 9,223,372,036,854,775,807까지\(소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CObj`|[Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)|임의의 유효한 식입니다.|  
|`CSByte`|[SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|값의 범위는 \-128에서 127까지\(소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CShort`|[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)|값의 범위는 \-32,768에서 32,767까지\(소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CSng`|[Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)|\-3.402823E\+38 ~ \-1.401298E\-45\(음수\), 1.401298E\-45 ~ 3.402823E\+38\(양수\)|  
|`CStr`|[String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)|`CStr`에 대한 반환은 `expression` 인수에 따라 다릅니다\(  자세한 내용은 [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)를 참조하십시오.|  
|`CUInt`|[UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|값의 범위는 0에서 4,294,967,295까지\(부호가 없으며 소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CULng`|[ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|값의 범위는 0에서 18,446,744,073,709,551,615까지\(부호가 없으며 소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
|`CUShort`|[UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|값의 범위는 0에서 65,535까지\(부호가 없으며 소수 부분은 반올림됨<sup>1</sup>\)입니다.|  
  
 <sup>1</sup> 소수 부분에는 *은행원 반올림*이라고 하는 특수한 형식의 반올림 규칙이 적용될 수 있습니다.  자세한 내용은 "설명" 부분을 참조하십시오.  
  
## 설명  
 일반적으로 <xref:System.Convert> 클래스나 개별 형식 구조체 또는 클래스에서는 `ToString()` 같은 .NET Framework 메서드보다 Visual Basic 형식 변환 함수를 우선적으로 사용해야 합니다.  Visual Basic 함수는 Visual Basic 코드와 최적으로 상호 작용하도록 설계되었으며 소스 코드를 보다 간단하고 읽기 쉽게 만듭니다.  또한 .NET Framework 변환 메서드가 항상 Visual Basic 함수와 동일한 결과를 생성하는 것은 아닙니다\(예: `Boolean`을 `Integer`로 변환하는 경우\).  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조하십시오.  
  
## 동작  
  
-   **강제 변환.** 일반적으로 데이터 형식 변환 함수를 사용하여 연산의 결과를 기본 데이터 형식이 아닌 특정 데이터 형식으로 강제 변환할 수 있습니다.  예를 들어, 단정밀도, 배정밀도 또는 정수 연산이 발생할 경우 `CDec` 함수를 사용하여 10진수 연산을 계산합니다.  
  
-   **변환 실패.** 함수에 전달된 `expression`이 변환될 데이터 형식의 범위 밖에 있으면 <xref:System.OverflowException>이 발생합니다.  
  
-   **소수 부분.** 정수가 아닌 값을 정수 계열 형식으로 변환할 경우 정수 변환 함수\(`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng` 및 `CUShort`\)는 소수 부분을 제거하고 값을 가장 가까운 정수로 반올림합니다.  
  
     소수 부분이 정확하게 0.5이면 정수 변환 함수는 값을 가장 가까운 짝수 정수로 반올림합니다.  예를 들어, 0.5는 0으로 반올림하고 1.5 및 2.5는 모두 2로 반올림합니다.  이를 *은행원 반올림*이라고도 합니다. 이 반올림 규칙은 이러한 숫자를 여러 개 더할 경우에 누적될 수 있는 오차를 보정할 수 있습니다.  
  
     `CInt`와 `CLng`와 달리 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 함수는 소수 부분을 반올림하지 않고 버립니다.  또한 `Fix`와 `Int`는 항상 사용자가 전달한 값과 같은 데이터 형식 값을 반환합니다.  
  
-   **날짜\/시간 변환.** <xref:Microsoft.VisualBasic.Information.IsDate%2A> 함수를 사용하여 값을 날짜 및 시간으로 변환할 수 있는지 확인합니다.  `CDate`는 날짜 리터럴 및 시간 리터럴은 인식하지만 숫자 값은 인식하지 못합니다.  Visual Basic 6.0 `Date` 값을 Visual Basic 2005 이상 버전의 `Date` 값으로 변환하려면 <xref:System.DateTime.FromOADate%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
-   **기본 날짜\/시간 값.** [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)에는 항상 날짜 정보와 시간 정보가 모두 포함됩니다.  형식 변환을 목적으로, Visual Basic은 1\/1\/0001\(1년 1월 1일\)을 날짜의 *기본값*으로 간주하고 00:00:00\(자정\)을 시간의 기본값으로 간주합니다.  `Date` 값을 문자열로 변환할 경우 `CStr`의 결과 문자열에 기본값이 포함되지 않습니다.  예를 들어, `#January 1, 0001 9:30:00#`을 문자열로 변환한 결과는 "9:30:00 AM"이며 날짜 정보는 표시되지 않습니다.  그러나 날짜 정보는 원래 `Date` 값에 그대로 있으며 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 등의 함수를 사용하여 복구할 수 있습니다.  
  
-   **문화권 구분.** 문자열을 포함하는 형식 변환 함수는 응용 프로그램의 현재 문화권 설정에 기초하여 변환을 수행합니다.  예를 들어, `CDate`는 시스템의 로캘 설정에 따라 날짜 형식을 인식합니다.  사용자 로캘에 맞는 순서로 일, 월, 년을 지정해야 합니다. 그렇지 않으면 날짜가 올바르게 해석되지 않을 수 있습니다.  "Wednesday"와 같은 요일 문자열이 들어 있는 경우 long 날짜 형식은 인식되지 않습니다.  
  
     로캘에 지정된 것과 다른 형식의 값 문자열 표현으로 변환하거나 이러한 표현에서 변환해야 할 경우에는 Visual Basic 형식 변환 함수를 사용할 수 없습니다.  이렇게 하려면 해당 값 형식의 `ToString(IFormatProvider)` 및 `Parse(String, IFormatProvider)` 메서드를 사용합니다.  예를 들어, 문자열을 `Double`로 변환할 경우 <xref:System.Double.Parse%2A?displayProperty=fullName>를 사용하고 `Double` 형식의 값을 문자열로 변환할 경우 <xref:System.Double.ToString%2A?displayProperty=fullName>을 사용합니다.  
  
## CType 함수  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)는 두 번째 인수 `typename`을 가져와서 `expression`을 `typename`으로 강제 변환합니다. `typename`은 유효한 변환이 존재하는 임의의 데이터 형식, 구조체, 클래스 또는 인터페이스입니다.  
  
 `CType`과 다른 형식 변환 키워드를 비교하려면 [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)를 참조하십시오.  
  
## CBool 예제  
 다음 예제에서는 `CBool` 함수를 사용하여 식을 `Boolean` 값으로 변환합니다.  `CBool`은 식의 계산 결과가 0이 아니면 `True`를 반환하고, 0이면 `False`를 반환합니다.  
  
 [!CODE [VbVbalrFunctions#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#1)]  
  
## CByte 예제  
 다음 예제에서는 `CByte` 함수를 사용하여 식을 `Byte`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#2)]  
  
## CChar 예제  
 다음 예제에서는 `CChar` 함수를 사용하여 `String` 식의 첫 번째 문자를 `Char` 형식으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#3)]  
  
 `CChar`에 대한 입력 인수는 `Char` 또는 `String` 데이터 형식이어야 합니다.  `CChar`는 숫자 데이터 형식을 허용하지 않기 때문에 `CChar`를 사용하여 숫자를 문자로 변환할 수 없습니다.  다음 예제에서는 코드 포인트\(문자 코드\)를 나타내는 숫자를 구하여 해당 문자로 변환합니다.  <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 함수를 사용하여 숫자 문자열을 구하고 `CInt`를 사용하여 문자열을 `Integer` 형식으로 변환하고, `ChrW`를 사용하여 숫자를 `Char` 형식으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#4)]  
  
## CDate 예제  
 다음 예제에서는 `CDate` 함수를 사용하여 문자열을 `Date` 값으로 변환합니다.  일반적으로 다음 예제와 같이 날짜와 시간을 문자열로 하드 코딩하는 것은 좋지 않습니다.  대신 \#Feb 12, 1969\#, \#4:45:23 PM\# 등과 같은 날짜 리터럴과 시간 리터럴을 사용하십시오.  
  
 [!CODE [VbVbalrFunctions#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#5)]  
  
## CDbl 예제  
 [!CODE [VbVbalrFunctions#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#6)]  
  
## CDec 예제  
 다음 예제에서는 `CDec` 함수를 사용하여 숫자 값을 `Decimal`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#7)]  
  
## CInt 예제  
 다음 예제에서는 `CInt` 함수를 사용하여 값을 `Integer`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#8)]  
  
## CLng 예제  
 다음 예제에서는 `CLng` 함수를 사용하여 값을 `Long`으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#9)]  
  
## CObj 예제  
 다음 예제에서는 `CObj` 함수를 사용하여 숫자 값을 `Object`로 변환합니다.  `Object` 변수 자체에는 할당된 `Double` 값을 가리키는 4바이트 포인터만 들어 있습니다.  
  
 [!CODE [VbVbalrFunctions#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#10)]  
  
## CSByte 예제  
 다음 예제에서는 `CSByte` 함수를 사용하여 숫자 값을 `SByte`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#11)]  
  
## CShort 예제  
 다음 예제에서는 `CShort` 함수를 사용하여 숫자 값을 `Short`으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#12)]  
  
## CSng 예제  
 다음 예제에서는 `CSng` 함수를 사용하여 값을 `Single`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#13)]  
  
## CStr 예제  
 다음 예제에서는 `CStr` 함수를 사용하여 숫자 값을 `String`으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#14)]  
  
 다음 예제에서는 `CStr` 함수를 사용하여 `Date` 값을 `String` 값으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#15)]  
  
 `CStr`은 항상 현재 로캘에 대한 표준 short 형식으로 `Date` 값을 렌더링합니다\(예: "6\/15\/2003 4:35:47 PM"\).  그러나 `CStr`는 날짜와 시간에 대한 *기본값*인 1\/1\/0001 및 00:00:00을 표시하지 않습니다.  
  
 `CStr`에 의해 반환되는 값에 대한 자세한 내용은 [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)을 참조하십시오.  
  
## CUInt 예제  
 다음 예제에서는 `CUInt` 함수를 사용하여 숫자 값을 `UInteger`로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#16)]  
  
## CULng 예제  
 다음 예제에서는 `CULng` 함수를 사용하여 숫자 값을 `ULong`으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#17)]  
  
## CUShort 예제  
 다음 예제에서는 `CUShort` 함수를 사용하여 숫자 값을 `UShort`으로 변환합니다.  
  
 [!CODE [VbVbalrFunctions#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrFunctions#18)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 <xref:Microsoft.VisualBasic.Strings.Format%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [Conversion Functions](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)