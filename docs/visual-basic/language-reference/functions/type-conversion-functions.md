---
title: 형식 변환 함수(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605084"
---
# <a name="type-conversion-functions-visual-basic"></a>형식 변환 함수(Visual Basic)
이러한 함수는 인라인으로 컴파일됩니다 변환 코드는 식을 계산 하는 코드의 일부입니다. 경우에 따라 성능이 향상 되는 변환을 수행 하는 프로시저에 대 한 호출이 있습니다. 각 함수는 식을 특정 데이터 형식으로 강제 변환합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="part"></a>파트  
 `expression`  
 필수. 원본 데이터 형식의 모든 식입니다.  
  
## <a name="return-value-data-type"></a>반환 값 데이터 형식  
 다음 표에 나와 있는 것 처럼 반환 하는 값의 데이터 형식을 결정 하는 함수 이름입니다.  
  
|함수 이름|반환 데이터 형식|에 대 한 범위 `expression` 인수|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|모든 유효한 `Char` 또는 `String` 또는 숫자 식입니다.|  
|`CByte`|[Byte 데이터 형식](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0부터 255 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CChar`|[Char 데이터 형식](../../../visual-basic/language-reference/data-types/char-data-type.md)|모든 유효한 `Char` 또는 `String` 식;의 첫 번째 문자만 `String` 변환 됩니다; 값 0 ~ 65535 (부호 없음) 될 수 있습니다.|  
|`CDate`|[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)|날짜 및 시간의 유효한 표현을 합니다.|  
|`CDbl`|[Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 e + 308에서-4.94065645841246544E-소수점; 4.94065645841246544E-324 1.79769313486231570 e + 308 양수 값에 대 한 합니다.|  
|`CDec`|[Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ /-79228162514264337593543950335-즉, 소수 자릿수가 없는 숫자입니다. 소수 자릿수가 28 숫자에 대 한 범위는 + /-7.9228162514264337593543950335 사이입니다. 0이 아닌 수를 최소로 0.0000000000000000000000000001 (+ 1E-28)입니다.|  
|`CInt`|[Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)|-2147483648 ~ 2147483647; 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CLng`|[Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9223372036854775808에서 9223372036854775807; 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CObj`|[Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)|모든 유효한 식입니다.|  
|`CSByte`|[SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|-128에서 127; 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CShort`|[Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)|-32, 768 32, 767; 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CSng`|[Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3.402823E + 38에서-1.401298 e-45 음수 값이 있습니다. 1.401298 e-45 3.402823E + 38 양수 값에 대 한 합니다.|  
|`CStr`|[String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)|에 대 한 반환 `CStr` 에 종속 된 `expression` 인수입니다. 참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.|  
|`CUInt`|[UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|0 ~ 4294967295 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CULng`|[ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|0에서 18446744073709551615 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup>|  
|`CUShort`|[UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|0-65535 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup>|  
  
 <sup>1</sup> 소수 부분이 호출 반올림 하는 특수 한 유형의 영향을 받을 수 *banker rounding*합니다. 자세한 내용은 "주의"를 참조 하십시오.  
  
## <a name="remarks"></a>설명  
 일반적으로.NET Framework 메서드 대신 Visual Basic 형식 변환 함수를와 같은 사용 해야 `ToString()`, 중 하나에 <xref:System.Convert> 클래스 또는 개별 형식 구조체 또는 클래스에 있습니다. Visual Basic 함수는 Visual Basic 코드와의 최적의 상호 작용을 위한 하 고 더 짧게 만들어 더 쉽게 읽을 수 소스 코드 할 수도 있습니다. 또한.NET Framework의 변환 메서드는이 Visual Basic 함수 예를 들어 변환할 때와 동일한 결과 항상 생성 하지 않는 `Boolean` 를 `Integer`합니다. 자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
## <a name="behavior"></a>동작  
  
-   **강제 변환 합니다.** 일반적으로 기본 데이터 형식을 보다는 특정 데이터 형식에 대 한 작업의 결과 강제 변환할 데이터 형식 변환 함수를 사용할 수 있습니다. 예를 들어 사용 `CDec` 여기서 단 정밀도, 두 자리 또는 정수 산술이 정상적으로 수행 하는 경우에는 10 진수 연산을 합니다.  
  
-   **변환 실패입니다.** 경우는 `expression` 함수에 전달 된 범위를 벗어났습니다 데이터 형식의 변환 될 수 있는는 <xref:System.OverflowException> 발생 합니다.  
  
-   **소수 부분입니다.** 정수 계열에 정수가 아닌 값을 변환 하는 경우 입력, 정수 변환 함수 (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, 및 `CUShort`) 제거는 소수 부분 및 값을 가장 가까운 정수로 반올림 합니다.  
  
     소수 부분이 정확 하 게 하는 경우 0.5 정수 변환 함수 반올림 하는 가장 근사한 짝수 정수로 합니다. 예를 들어 0.5 0 및 1.5와 2.5는 2로 반올림을 반올림 합니다. 이 라고도 *banker rounding*와 함께 이러한 많은 숫자를 추가 하는 경우 누적 될 수 있는 편차에 대 한 보정 하기 위한 것입니다.  
  
     `CInt` 및 `CLng` 에서 다는 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 숫자의 소수 부분을 반올림 하지 않고, truncate는 함수입니다. 또한 `Fix` 및 `Int` 에서 전달 항상 동일한 데이터 형식의 값을 반환 합니다.  
  
-   **날짜/시간 변환 합니다.** 사용 된 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 을 날짜 및 시간 값을 변환할 수 있는지 확인 하는 함수입니다. `CDate` 리터럴 날짜 및 시간 리터럴 하지만 숫자 값이 아니라 인식합니다. Visual Basic 6.0 변환할 `Date` 값을 한 `Date` Visual Basic 2005에서에서 값 또는 이상 버전을 사용할 수 있습니다는 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> 메서드.  
  
-   **중립 날짜/시간 값입니다.** [Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md) 항상 날짜와 시간 정보를 포함 합니다. 형식 변환을 위해 Visual Basic 간주 1/1/0001 (1 1 년 1 월)는 *기본값으로* 시간에 대 한 기본값으로 간주 00시: 00 (자정) 및 날짜,입니다. 변환 하는 경우는 `Date` 값을 문자열로, `CStr` 기본값이 결과 문자열에 포함 되지 않습니다. 예를 들어, 변환 하면 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00" 하 고 날짜 정보는 표시 되지 않습니다. 그러나 날짜 정보에에서는 아직 있는 원래 `Date` 값 및와 같은 함수를 사용 하 여 복구할 수 수 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 함수입니다.  
  
-   **문화권 구분 합니다.** 응용 프로그램에 대 한 현재 문화권 설정에 따라 변환을 수행 하는 문자열을 포함 하는 형식 변환 함수입니다. 예를 들어 `CDate` 시스템의 로캘 설정에 따라 날짜 형식을 인식 합니다. 일, 월 및 연도 사용자 로캘에 대 한 올바른 순서로 제공 해야 하거나 날짜 올바르게 해석 될 수 있습니다. 자세한 날짜 형식에는 "수요일" 등의 주 일 문자열을 포함 하는 경우 인식 되지 않습니다.  
  
     사용자의 로캘에 따라 지정 되어 있지 않은 형식에 있는 값의 문자열 표현으로 변환 하는 경우 Visual Basic 형식 변환 함수를 사용할 수 없습니다. 이 위해 사용 하 여는 `ToString(IFormatProvider)` 및 `Parse(String, IFormatProvider)` 해당 값 형식의 메서드. 사용 예를 들어 <xref:System.Double.Parse%2A?displayProperty=nameWithType> 문자열을 변환 하는 경우는 `Double`를 사용 하 여 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때 `Double` 문자열로 합니다.  
  
## <a name="ctype-function"></a>CType Function  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 두 번째 인수를 받으며 `typename`, 강제 `expression` 를 `typename`여기서 `typename` 데이터 형식, 구조체, 클래스 또는 인터페이스에 있는 유효한 변환 될 수 있습니다.  
  
 에 대 한 비교 `CType` 참조와 다른 형식 변환 키워드, [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.  
  
## <a name="cbool-example"></a>CBool 예제  
 다음 예제에서는 `CBool` 식을 변환 하는 함수 `Boolean` 값입니다. 식이 0이 아닌 값으로 계산 될 경우 `CBool` 반환 `True`, 그렇지 않으면 반환 `False`합니다.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>CByte 예제  
 다음 예제에서는 `CByte` 식으로 변환 하는 함수는 `Byte`합니다.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>CChar 예제  
 사용 하 여 다음 예제는 `CChar` 의 첫 번째 문자를 변환 하는 함수는 `String` 식을 `Char` 유형입니다.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 입력된 인수 `CChar` 데이터 형식 이어야 합니다 `Char` 또는 `String`합니다. 사용할 수 없는 `CChar` 때문에 숫자를 문자로 변환할 `CChar` 숫자 데이터 형식을 사용할 수 없습니다. 다음 예제에서는 코드 포인트 (문자 코드)를 나타내는 숫자를 구하여 해당 문자로 변환 합니다. 사용 하 여는 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 함수는 숫자, 문자열입니다. `CInt` 문자열 입력을 변환할 `Integer`, 및 `ChrW` 숫자 형식으로 변환 `Char`합니다.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>CDate 예제  
 다음 예제에서는 `CDate` 문자열을 변환 하는 함수 `Date` 값입니다. 일반적으로 하드 코딩 된 날짜 및 시간 문자열 (이 예제 에서처럼)로 권장 되지 않습니다. 날짜 리터럴과 1969 # #Feb 12, 같은 시간 리터럴을 사용 하 여 및 # 4시 45분: 23 PM #를 대신 합니다.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>CDbl 예제  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>CDec 예제  
 다음 예제에서는 `CDec` 숫자 값을 변환 하려면 함수 `Decimal`합니다.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>CInt 예제  
 다음 예제에서는 `CInt` 함수에 값을 변환할 `Integer`합니다.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>CLng 예제  
 다음 예제에서는 `CLng` 값을 변환 하는 함수 `Long`합니다.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>CObj 예제  
 다음 예제에서는 `CObj` 숫자 값을 변환 하려면 함수 `Object`합니다. `Object` 변수 자체에 가리키는 4 바이트 포인터만 포함 된 `Double` 할당 한 값입니다.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>CSByte 예제  
 다음 예제에서는 `CSByte` 숫자 값을 변환 하려면 함수 `SByte`합니다.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>CShort 예제  
 다음 예제에서는 `CShort` 숫자 값을 변환 하려면 함수 `Short`합니다.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>CSng 예제  
 다음 예제에서는 `CSng` 값을 변환 하는 함수 `Single`합니다.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>CStr 예제  
 다음 예제에서는 `CStr` 숫자 값을 변환 하려면 함수 `String`합니다.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 다음 예제에서는 `CStr` 변환 하려면 함수를 `Date` 값을 `String` 값입니다.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` 항상를 렌더링 한 `Date` 예를 들어 현재 로캘에 대 한 표준 짧은 형식 값 "6/15/2003 오후 4시 35분: 47"입니다. 그러나 `CStr` 표시 하지 않습니다는 *중립 값* 의 1/1/0001 한 날짜와 시간에 대 한 00시: 00입니다.  
  
 반환 값에 대 한 세부 `CStr`, 참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.  
  
## <a name="cuint-example"></a>CUInt 예제  
 다음 예제에서는 `CUInt` 숫자 값을 변환 하려면 함수 `UInteger`합니다.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>CULng 예제  
 다음 예제에서는 `CULng` 숫자 값을 변환 하려면 함수 `ULong`합니다.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>CUShort 예제  
 다음 예제에서는 `CUShort` 숫자 값을 변환 하려면 함수 `UShort`합니다.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>참고 항목  
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
 [변환 함수](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
