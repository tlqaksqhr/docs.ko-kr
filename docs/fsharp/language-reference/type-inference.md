---
title: 형식 유추(F#)
description: 'F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 93e1568ebe71436ad8f7119ac9d9628cdf58012a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-inference"></a>형식 유추

이 항목에서는 F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법을 설명 합니다.

## <a name="type-inference-in-general"></a>형식 유추를 일반 사항
형식 유추 방법은 때 컴파일러 추론할 수 없습니다. 결정적 유형을 제외 하 고 F # 구문 형식을 지정할 필요가 없습니다. F #은 동적으로 형식화 된 언어 또는 F #의 값은 약하게 형식화 된 명시적 형식 정보를 생략 하는 것은 의미가 아닙니다. F # 컴파일러를 컴파일하는 동안 각 구문에 대 한 정확한 형식을 추론 하는 정적 형식의 언어인은입니다. 각 구문의 형식을 추론 하도록 컴파일러에 대 한 정보가 충분 하지 않으면, 코드에서 어딘가에 명시적인 형식 주석을 추가 하 여 추가 형식 정보를 일반적으로 제공 해야 있습니다.


## <a name="inference-of-parameter-and-return-types"></a>매개 변수 및 반환 형식 유추
매개 변수 목록에서 각 매개 변수의 형식을 지정할 필요가 없습니다. 및 F #은 정적으로 형식화 된 언어 및 따라서 모든 값과 식의 형식이 정해 집니다 컴파일 타임에 아직 합니다. 명시적으로 지정 하지 않으면 해당 형식에 컴파일러는 컨텍스트를 기준으로 형식을 유추 합니다. 형식에 별도로 지정 하지 않은 경우 제네릭인 것으로 유추 됩니다. 코드를 사용 하는 값 일관 되지 않게 하는 방식에 더 단일 임을 유추 컴파일러에서 오류를 보고 하는 값의 모든 사용을 충족 하.

함수의 반환 형식은 함수에서 마지막 식 유형에 따라 결정 됩니다.

예를 들어 다음 코드에서는 형식 매개 변수에서에서 `a` 및 `b` 반환 형식 모두로 유추 하 고 `int` 때문에 리터럴 `100` 유형의 `int`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

리터럴을 변경 하 여 형식 유추를 적용할 수 있습니다. 만들면는 `100` 는 `uint32` 접미사를 추가 하 여 `u`, 유형의 `a`, `b`, 반환 값으로 유추 되 고 `uint32`합니다.

수도 내재 함수 및 특정 유형과 함께 작동 하는 메서드 같은 형식에 대 한 제한 된 다른 구문을 사용 하 여 형식 유추 합니다.

또한 또는 적용할 수 있습니다 명시적 형식 주석을 함수 또는 메서드 매개 변수를 식에서 변수를 다음 예제에 나와 있는 것 처럼 합니다. 오류가 다른 제약 조건 사이 충돌이 발생 하면 발생 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

명시적으로 제공 하 여 형식 주석을 모든 매개 변수는 함수의 반환 값을 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

형식 주석이 매개 변수에 유용 일반적인 경우에도 매개 변수는 개체 유형 및 멤버를 사용 하려는 경우.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a>자동 일반화
함수 코드 매개 변수의 형식에 종속 된 경우 컴파일러는 제네릭 매개 변수를 고려 합니다. 이 라고 *자동 일반화*, 복잡성 증가 하지 않고 제네릭 코드를 작성를 수 있습니다.

예를 들어 다음 함수에 모든 형식의 두 매개 변수를 결합합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

형식 유추 됩니다.

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>추가 정보
형식 유추에서 F # 언어 사양에 자세히 설명 되어 있습니다.


## <a name="see-also"></a>참고 항목
[자동 일반화](generics/automatic-generalization.md)
