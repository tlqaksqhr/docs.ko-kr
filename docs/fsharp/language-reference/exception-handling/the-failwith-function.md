---
title: '예외: failwith 함수(F#)'
description: "'Failwith' 함수에서 F # 예외를 생성 하는 방법에 대해 알아봅니다."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: af1e3b7dc96b3b822e2e19b7bac435940d15922f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-failwith-function"></a>예외: failwith 함수

`failwith` 함수 F # 예외를 생성 합니다.


## <a name="syntax"></a>구문

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>설명
*오류 메시지 문자열* 위 구문에는 리터럴 문자열 또는 형식의 값 `string`합니다. 됩니다는 `Message` 예외의 속성입니다.

생성 되는 예외 `failwith` 는 `System.Exception` 예외 이름을 가진 대 한 참조 인 `Failure` F # 코드에서. 다음 코드에서는 `failwith` 예외를 throw 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외 형식](exception-types.md)

[예외: `try...with` 식](the-try-with-expression.md)

[예외: `try...finally` 식](the-try-finally-expression.md)

[예외: `raise` 함수](the-raise-function.md)
