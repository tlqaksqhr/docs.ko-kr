---
title: "예외 형식(F#)"
description: "정의 및 F # 예외 형식을 사용 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a>예외 형식

두 종류의 F #에서 예외:.NET 예외 형식 및 F # 예외 형식입니다. 이 항목에서는 정의 하 고 F # 예외 형식을 사용 하는 방법을 설명 합니다.


## <a name="syntax"></a>구문

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>설명
위 구문에서 *예외 형식을* 새 F # 예외 유형, 이름 및 *인수 형식* 이 유형의 예외를 발생 시킬 때 제공할 수 있는 인수 형식을 나타냅니다. 에 대 한 튜플을 유형을 사용 하 여 여러 인수를 지정할 수 있습니다 *인수 형식*합니다.

F # 예외에 대 한 일반적인 정의 다음과 같습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

사용 하 여 이러한 유형의 예외를 생성할 수 있습니다는 `raise` 다음과 같이 작동 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

F # 예외 형식에 있는 필터에서 직접 사용할 수 있습니다는 `try...with` 다음 예제와 같이 식입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

정의 된 예외 형식을 `exception` F #에 키워드는에서 상속 되는 새 형식을 `System.Exception`합니다.


## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외: `raise` 함수](the-raise-function.md)

[예외 계층](https://msdn.microsoft.com/library/z4c5tckx.aspx)
