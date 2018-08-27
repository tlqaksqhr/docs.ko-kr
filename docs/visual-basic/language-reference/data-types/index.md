---
title: 데이터 형식 요약(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
ms.openlocfilehash: 8afeba3f88c4bfe6e1c9777f950c3b458665e340
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925900"
---
# <a name="data-type-summary-visual-basic"></a>데이터 형식 요약(Visual Basic)
다음 표에서 Visual Basic 데이터 형식, 해당 지 원하는 공용 언어 런타임 형식, 해당 일반 저장소 할당 및 해당 값 범위를 보여 줍니다.  
  
|Visual Basic 형식|공용 언어 런타임 형식 구조|일반 저장소 할당|값 범위|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|플랫폼 구현에 따라 달라 집니다.|`True` 또는 `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1바이트|0-255 (부호 없음)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (하나의 문자)|<xref:System.Char>|2바이트|0 ~ 65535 (부호 없음)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8바이트|0:00:00 (자정)에서 9999 년 12 월 31 일 오후 11시 59분: 59 0001 년 1 월 1 일|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16바이트|0 ~ + /-79228162514264337593543950335 (7.9... + /-E + 28) <sup>†</sup> 없이 소수점; 0 ~ 28 자릿수가 소수 자릿수 + /-7.9228162514264337593543950335<br /><br /> 최소 0이 아닌 숫자는 0.0000000000000000000000000001 1E-28) (+ + /- <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) (배정밀도 부동 소수점)|<xref:System.Double>|8바이트|-1.79769313486231570 + 308에서-4.94065645841246544E-324 <sup>†</sup> 음수 값에 대 한<br /><br /> 4.94065645841246544E-324 1.79769313486231570 e + 308 <sup>†</sup> 양수 값|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4바이트|-2,147,483,648 ~ 2,147,483,647 (부호 있음)|  
|[긴](../../../visual-basic/language-reference/data-types/long-data-type.md) (long 정수)|<xref:System.Int64>|8바이트|9223372036854775807-9223372036854775808 (9.2... E + 18 <sup>†</sup>) (부호 있음)|  
|[개체](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (클래스)|32 비트 플랫폼에서 4 바이트<br /><br /> 64 비트 플랫폼에서 8 바이트|형식의 변수에 저장할 수 있는 모든 유형에 `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1바이트|-128에서 127 (부호 있음)를 통해|  
|[짧은](../../../visual-basic/language-reference/data-types/short-data-type.md) (정수)|<xref:System.Int16>|2바이트|-32,768부터 32,767 (부호 있음)를 통해|  
|[단일](../../../visual-basic/language-reference/data-types/single-data-type.md) (단 정밀도 부동 소수점)|<xref:System.Single>|4바이트|-3.4028235E + 38에서-1.401298E-45 <sup>†</sup> 음수 값에 대 한<br /><br /> 1.401298E-45 3.4028235E + 38 까지인 <sup>†</sup> 양수 값|  
|[문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) (가변 길이)|<xref:System.String> (클래스)|플랫폼 구현에 따라 달라 집니다.|0에서 약 2 십억 유니코드 문자입니다.|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4바이트|0 ~ 4294967295 (부호 없음)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8바이트|0에서 18446744073709551615 (1.8... E + 19 <sup>†</sup>) (부호 없음)|  
|[사용자 정의](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (구조)|(에서 상속 <xref:System.ValueType>)|플랫폼 구현에 따라 달라 집니다.|구조체의 각 멤버에 해당 데이터 형식에서 다른 멤버의 범위 독립 결정 범위|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2바이트|0-65535 (부호 없음)|  
  
 <sup>†</sup> 에 *과학적 표기법*, "E"는 10의 거듭제곱을 나타냅니다. 따라서 3.56 e + 2는 3.56 x 10<sup>2</sup> 356를 나타내고 3.56 e 또는-2는 3.56 / 10<sup>2</sup> 또는 0.0356을 나타냅니다.  
  
> [!NOTE]
>  텍스트를 포함 하는 문자열을 사용 하 여는 <xref:Microsoft.VisualBasic.Strings.StrConv%2A> 다른 하나의 텍스트 형식에서 변환 하는 함수입니다.  
  
 를 선언 문의 데이터 형식을 지정 하는 것 외에도 형식 문자를 사용 하 여 데이터 형식의 몇 가지 프로그래밍 요소를 적용할 수 있습니다. 참조 [문자 입력](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)합니다.  
  
## <a name="memory-consumption"></a>메모리 소비  
 기본 데이터 형식에서 선언 하는 경우 메모리 소비가 일반 저장소 할당량과 가정 하에 안전 하지 않습니다. 다음은 다음 고려 사항 때문입니다.  
  
-   **저장소 할당 합니다.** 공용 언어 런타임에서 응용 프로그램이 실행 되는 플랫폼의 현재 특성에 따라 저장소를 할당할 수 있습니다. 메모리 거의 꽉 차면 함께 최대한 가깝게 선언 된 요소가 팩 수 것입니다. 다른 경우에서에 메모리 주소 성능을 최적화 하기 위해 일반적인 하드웨어 경계를 맞출 수 있습니다.  
  
-   **플랫폼 너비입니다.** 64 비트 플랫폼에서 저장소 할당이 32 비트 플랫폼에서 할당와 다릅니다.  
  
### <a name="composite-data-types"></a>복합 데이터 형식  
 배열 또는 구조체와 같은 복합 데이터 형식의 각 멤버에 동일한 고려 사항이 적용 됩니다. 형식 멤버의 일반 저장소 할당량을 단순히 더하거나를 이용할 수 있습니다. 또한 다음과 같은 기타 고려 사항 가지가 있습니다.  
  
-   **오버 헤드입니다.** 일부 복합 형식에는 추가 메모리 요구 사항이 있습니다. 예를 들어, 배열 배열 자체 및 각 차원에 대 한 추가 메모리를 사용합니다. 32 비트 플랫폼에서이 오버 헤드는 현재 12 바이트 + 각 차원에 대 한 8 바이트입니다. 64 비트 플랫폼에서이 요구 사항은 두 배가 됩니다.  
  
-   **저장소 레이아웃입니다.** 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일 하 게 가정할 수 없습니다. 2 바이트 또는 4 바이트 경계를 같은 바이트 맞춤에 대 한 가정을도 만들 수 없습니다. 클래스 또는 구조체를 정의 하는 해당 멤버의 저장소 레이아웃을 제어 해야 하 고 적용할 수 있습니다 하는 경우는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 클래스 또는 구조체입니다.  
  
### <a name="object-overhead"></a>오버 헤드가 개체  
 `Object` 참조에 있는 모든 기본 또는 복합 데이터 형식은 데이터 형식에 포함 된 데이터 외에도 4 바이트를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
