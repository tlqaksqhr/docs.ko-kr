---
title: 기본 형식(F#)
description: 'F # 언어에 사용 되는 기본 기본 형식을 검색 합니다.'
ms.date: 05/16/2016
ms.openlocfilehash: efe419e5ebf2e49be9433bbd3025ff290d648296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564471"
---
# <a name="primitive-types"></a>기본 형식

이 항목에서는 F # 언어에 사용 되는 기본 기본 형식을 나열 합니다. 또한 각 유형의 해당 .NET 형식과 최소 및 최대값을 제공합니다.

## <a name="summary-of-primitive-types"></a>기본 형식 요약
다음 표에서 기본 F # 형식의 속성이 요약 되어 있습니다.

|형식|.NET 형식|설명|
|----|---------|-----------|
|`bool`|`System.Boolean`|가능한 값은 `true`와 `false`입니다.|
|`byte`|`System.Byte`|0에서 255 사이의 값입니다.|
|`sbyte`|`System.SByte`|-128에서 127 까지의 값입니다.|
|`int16`|`System.Int16`|-32768에서 32767 까지의 값입니다.|
|`uint16`|`System.UInt16`|0에서 65535 사이의 값입니다.|
|`int`|`System.Int32`|-2147483648에서 2147483647 사이의 값입니다.|
|`uint32`|`System.UInt32`|0에서 4,294,967,295 사이의 값입니다.|
|`int64`|`System.Int64`|-9223372036854775808에서 9223372036854775807 값입니다.|
|`uint64`|`System.UInt64`|0에서 18446744073709551615 값입니다.|
|`nativeint`|`System.IntPtr`|부호 있는 정수로 네이티브 포인터입니다.|
|`unativeint`|`System.UIntPtr`|부호 없는 정수는 네이티브 포인터입니다.|
|`char`|`System.Char`|유니코드 문자 값입니다.|
|`string`|`System.String`|유니코드 텍스트입니다.|
|`decimal`|`System.Decimal`|부동 소수점 적어도 28 개의 유효 자릿수를 가진 데이터 형식입니다.|
|`unit`|적용할 수 없음|실제 값이 없음을 나타냅니다. 형식에는 하나의 정식 값 `()`합니다. 단위 값 `()`, 여기서는 값이 필요 하지만 실제 값이 없거나 의미 자리 표시자로 흔히 사용 됩니다.|
|`void`|`System.Void`|없는 형식 또는 값을 나타냅니다.|
|`float32, single`|`System.Single`|32 비트 부동 소수점 형식입니다.|
|`float, double`|`System.Double`|64 비트 부동 소수점 형식입니다.|

>[!NOTE]
64 비트 정수 형식에 대 한 너무 큰 정수를 계산 하는 데 사용 하 여 수행할 수 있습니다는 [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) 유형입니다. `bigint` 기본 형식; 간주 되지 않습니다. 에 대 한 약어 `System.Numerics.BigInteger`합니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
