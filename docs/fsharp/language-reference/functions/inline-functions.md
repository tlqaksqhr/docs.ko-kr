---
title: 인라인 함수(F#)
description: 'F # 인라인 함수를 호출 하는 코드에 직접 통합을 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cb0addd1456af1ab97e249b9c5ece4d9f0818fa3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="inline-functions"></a>인라인 함수

*인라인 함수* 는 호출 코드에 직접 통합 함수입니다.


## <a name="using-inline-functions"></a>인라인 함수를 사용 하 여
정적 형식 매개 변수를 사용 하면 형식 매개 변수를 통해 매개 변수화 하는 모든 기능은 인라인 이어야 합니다. 이렇게 하면 컴파일러 이러한 형식 매개 변수를 확인할 수 있습니다. 일반적인 제네릭 형식 매개 변수를 사용 하는 경우에 이러한 제한이 없습니다.

멤버 제약 조건 사용을 설정, 이외의 인라인 함수 코드를 최적화 하는 데 도움이 될 수 있습니다. 그러나 인라인 함수 남용 되지 않도록 어려울 수 컴파일러 최적화 하 고 라이브러리 함수 구현의 변화에 따라 코드를 발생할 수 있습니다. 이러한 이유로 모든 다른 최적화 기술을 시도한 하지 않는 한 최적화에 대 한 인라인 함수를 사용 하지 않아야 합니다. 함수 또는 메서드 인라인 만들기 성능이 향상 될 수 있습니다 사용할 수 있지만 항상 대/소문자입니다. 따라서 특정된 함수를 인라인으로 만드는 영향을 주었는지 권한이 실제로 있는지 확인 하려면 성능 측정값을도 사용 해야 합니다.

`inline` 최상위 수준에, 모듈 수준 또는 클래스에서 메서드 수준에서 함수에 한정자를 적용 될 수 있습니다.

다음 코드 예제에서는 최상위 수준, 인라인 인스턴스 메서드인 및 인라인 정적 메서드는 인라인 함수를 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a>인라인 함수 및 형식 유추
존재 여부 `inline` 형식 유추 영향을 줍니다. 비인라인 함수 수 없는 반면 인라인 함수 수 있는 정적으로 확인 된 형식 매개 변수 때문입니다. 다음 코드 예제는 경우를 보여 줍니다. 여기서 `inline` 정적으로 확인 된 형식 매개 변수를 가진 함수를 사용 하는 때문에 유용는 `float` 변환 연산자.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

없이 `inline` 한정자,이 경우 특정 형식을 사용 하도록 함수를 사용 형식 유추 하면 `int`합니다. 하지만 `inline` 한정자가 있으면 함수가 유추에 정적으로 확인 된 형식 매개 변수가 있어야 합니다. 와 `inline` 다음 한정자를 형식 유추 됩니다.

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

함수를 변환할 수 있는 모든 형식을 허용 하는 것이 즉 **float**합니다.


## <a name="see-also"></a>참고 항목
[함수](index.md)

[제약 조건](../generics/constraints.md)

[정적으로 확인된 형식 매개 변수](../generics/statically-resolved-type-parameters.md)
