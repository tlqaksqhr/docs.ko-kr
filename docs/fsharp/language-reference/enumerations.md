---
title: 열거형(F#)
description: 'F # 열거형 리터럴 대신 더 읽기 쉽고 코드를 쉽게 사용 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: b51df53caf2e193496cb3694c913cbae08f7eaf5
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003101"
---
# <a name="enumerations"></a>열거형

*열거형*이 라고도 *열거형*,는 정수 계열 형식 값의 하위 집합에 레이블 할당 되는 위치입니다. 코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.


## <a name="syntax"></a>구문

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>설명
열거형 유사한 간단한 값이 있는 구별된 된 공용 구조체는 값을 지정할 수 있습니다. 값은 일반적으로 0 또는 1부터 시작 하는 정수 또는 비트 위치를 나타내는 정수입니다. 열거형은 비트 위치를 나타내는 데, 하는 경우 사용 해야 합니다 [플래그](xref:System.FlagsAttribute) 특성입니다.

열거형의 내부 형식, 예를 들어 하면 사용할 수 있도록 리터럴 접미사를 사용 하 여 같은 사용 되는 리터럴을 기준으로 결정 됩니다 `1u`, `2u`등, 부호 없는 정수 (`uint32`) 형식입니다.

명명된 된 값을 참조할 때 사용 해야 열거형 형식 자체의 이름 한정자로, 즉 `enum-name.value1`뿐 아니라, `value1`합니다. 구별 된 공용 구조체의 경우 다르게이 동작 합니다. 열거형에는 항상 이므로이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성입니다.

다음 코드는 선언과 열거형의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

쉽게 변환할 수 있습니다 열거형 기본 형식에 적절 한 연산자를 사용 하 여 다음 코드와 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

열거 형식은 다음 기본 형식 중 하나일 수 있습니다: `sbyte`, `byte`, `int16`, `uint16`, `int32`를 `uint32`, `int64`, `uint16`, `uint64`, 및 `char`합니다. 열거형 형식에서 상속 된 형식으로.NET Framework에서 표현 됩니다 `System.Enum`를 차례로에서 상속 됨 `System.ValueType`합니다. 따라서 스택 또는 인라인으로 포함 하는 개체에 있는 값 형식 및 기본 형식의 모든 값이 열거형의 유효한 값입니다. 중요 한 경우 이것이 열거형에 패턴 일치 값으로 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문입니다.

`enum` 명명 된 값은 미리 정의 된 중이 아닌 값도 열거형 값을 생성 하는 F # 라이브러리에서 함수를 사용할 수 있습니다. 사용 된 `enum` 다음과 같이 작동 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

기본값 `enum` 형식을 사용 하 여 함수가 작동 `int32`합니다. 따라서 다른 기본 형식을 포함 하는 열거형을 사용 하 여 사용할 수 없습니다. 대신, 다음을 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

또한으로 항상 내보내지는 열거형에 대 한 사례 `public`합니다. 이 C# 및.NET 플랫폼의 rest를 사용 하 여 정렬 됩니다.
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[캐스팅 및 변환](casting-and-conversions.md)
