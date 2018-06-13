---
title: 지연 계산(F#)
description: 'F # 지연 계산 응용 프로그램 및 라이브러리의 성능이 향상 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563934"
---
# <a name="lazy-computations"></a>지연 계산

*지연 계산* 에 즉시 평가 되지 않은 하지만 결과가 필요할 때 대신 평가 됩니다. 이 코드의 성능을 향상 시킬 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>설명

위 구문에서 *식* 는 결과가 필요한 경우에 평가 되는 코드 및 *식별자* 결과 저장 하는 값입니다. 형식의 값은 [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)위치는 실제 형식은에 사용 되 `'T` 식의 결과에서 결정 됩니다.

지연 계산을 사용 하 여 계산을 결과가 필요한 경우에만 실행 하도록 제한 하 여 성능을 향상 시킬 수 있습니다.

메서드를 호출 하면 계산을 강제로 수행할, `Force`합니다. `Force` 한 번만 수행 하 고 실행을 하면 됩니다. 에 대 한 후속 호출 `Force` 동일한 결과 실행 하지는 않습니다 모든 코드를 반환 합니다.

다음 코드에서는 지연 계산의 사용 및 사용 `Force`합니다. 이 코드의 형식 `result` 은 `Lazy<int>`, 및 `Force` 메서드가 반환 되는 `int`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

지연 계산 하지 않고는 `Lazy` 입력, 시퀀스에도 사용 됩니다. 자세한 내용은 참조 [시퀀스](sequences.md)합니다.

## <a name="see-also"></a>참고 항목

[F# 언어 참조](index.md)

[LazyExtensions 모듈](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
