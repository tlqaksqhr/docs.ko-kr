---
title: "예외: failwith 함수(F#)"
description: "'Failwith' 함수에서 F # 예외를 생성 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
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
