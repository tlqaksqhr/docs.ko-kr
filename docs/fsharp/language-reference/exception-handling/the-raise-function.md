---
title: '예외: raise 함수(F#)'
description: "오류 또는 예외 조건이 발생 했음을 알리는 데 F # 'raise' 함수를 사용 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-raise-function"></a>예외: raise 함수

`raise` 함수는 오류 또는 예외 조건이 발생 했음을 알리는 데 사용 됩니다. 오류에 대 한 정보는 예외 개체에 캡처됩니다.


## <a name="syntax"></a>구문

```fsharp
raise (expression)
```

## <a name="remarks"></a>설명
`raise` 함수는 예외 개체를 생성 하 고 스택 해제 프로세스를 시작 합니다. 스택 해제 프로세스는이 프로세스의 동작이 다른 모든.NET 언어에 있는 것과 같은 공용 언어 런타임 (CLR)에 의해 관리 됩니다. 스택 해제 프로세스는 생성 된 예외와 일치 하는 예외 처리기에 대 한 검색입니다. 현재에서 검색 시작 `try...with` 식에 있는 경우. 각 패턴에는 `with` 순서 대로 블록 검사 합니다. 일치 하는 예외 처리기가 발견 되 면 예외 것으로 간주 됩니다; 처리 그렇지 않으면 스택의 스택이 해제 되 고 `with` 일치 하는 처리기를 찾을 때까지 호출 체인 블록을 검사 합니다. 모든 `finally` 스택이 해제 되므로 순서 대로 호출 체인에 있는 블록도 실행 됩니다.

`raise` 함수는 해당 하는 `throw` C# 또는 c + +입니다. 사용 하 여 `reraise` 에 catch 처리기 호출 체인 동일한 예외를 전파 합니다.

다음 코드 예제는 사용법을 보여 줍니다.는 `raise` 함수에서 예외가 발생 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

`raise` 다음 예제와 같이 함수를.NET 예외를 발생 사용 수도 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외 형식](exception-types.md)

[예외: `try...with` 식](the-try-with-expression.md)

[예외: `try...finally` 식](the-try-finally-expression.md)

[예외: `failwith` 함수](the-failwith-function.md)

[예외: `invalidArg` 함수](the-invalidArg-function.md)
