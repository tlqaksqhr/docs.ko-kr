---
title: 열거형(F#)
description: 'F # 열거형 리터럴 대신 코드를 더 읽기 쉽고 쉽게 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4b1a61fb69403f826733893667e55991d39867c6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="enumerations"></a>열거형

*열거형*라고도 *열거형*, 레이블 값의 하위 집합에 할당 되는 위치는 정수 계열 형식입니다. 코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.


## <a name="syntax"></a>구문

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>설명
열거형은 매우 간단한 값을 가진 구별된 된 공용 구조체 유사 제외 하 고 값을 지정할 수 있습니다. 값은 일반적으로 0 또는 1부터 시작 하는 정수 또는 비트 위치를 나타내는 정수입니다. 열거형 비트 위치를 나타내는 하려는 경우 또한을 사용 해야는 [플래그](xref:System.FlagsAttribute) 특성입니다.

열거형의 내부 형식은 사용 되는 리터럴을에서 결정, 예를 들어 있습니다 사용할 수 있도록 리터럴 접미사가 있는 같은 `1u`, `2u`, 등의 부호 없는 정수에 대 한 (`uint32`) 형식입니다.

명명된 된 값을 참조할 때 사용 해야 열거형 형식 자체의 이름 한정자로 즉, `enum-name.value1`뿐 아니라, `value1`합니다. 이 동작은 구별 된 공용 구조체의에서 다릅니다. 열거형이 항상 있기 때문입니다는 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성입니다.

다음 코드에서는 선언 및 열거형의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

다음 코드에 나와 있는 것 처럼 적절 한 연산자를 사용 하 여 기본 형식에 열거형 변환할 쉽게.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

열거 형식은 다음 기본 유형 중 하나일 수 있습니다: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, 및 `char`합니다. 열거형 형식에서 상속 된 형식으로.NET Framework에서 표현 됩니다 `System.Enum`를 차례로에서 상속 됨 `System.ValueType`합니다. 따라서 스택 또는 인라인으로 포함 하는 개체에 있는 값 형식 및 기본 형식의 모든 값이 열거형의 유효한 값입니다. 이 기능은 중요 열거형에 패턴 일치, 값이 될 때 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문에 있습니다.

`enum` F # 라이브러리의 함수가 데 사용할 수는 미리 정의 된 다른 값도 하는 열거형 값을 생성할 명명 된 값입니다. 사용 된 `enum` 다음과 같이 작동 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

기본 `enum` 함수는 형식 `int32`합니다. 따라서 다른 기본 형식을 포함 하는 열거형 형식에 사용할 수 없습니다. 대신, 다음을 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[캐스팅 및 변환](casting-and-conversions.md)
