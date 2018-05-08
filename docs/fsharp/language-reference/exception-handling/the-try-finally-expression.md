---
title: '예외: try...finally 식(F#)'
description: "자세한 내용은 어떻게 F # ' try … 마지막 ' 코드 블록에서 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다."
ms.date: 05/16/2016
ms.openlocfilehash: a5fdec7b3986fc9a85c34b08d20dc31947c92b2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-tryfinally-expression"></a>예외: try...finally 식

`try...finally` 코드 블록에서 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다.


## <a name="syntax"></a>구문

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>설명
`try...finally` 에 코드를 실행 하는 식은 사용할 수 있습니다 *expression2* 실행 하는 동안 예외가 생성 되는지 여부에 관계 없이 위 구문에 *expression1*합니다.

유형의 *expression2* , 전체 식의 값에 영향을 주지 않습니다 예외가 발생 하지 않는 경우 반환 되는 형식에서 마지막 값은 *expression1*합니다. 예외가 발생 아무 값도 반환 하 고 제어 흐름이 호출 스택으로 다음 일치 하는 예외 처리기로 이동 합니다. 예외 처리기가 있으면 프로그램 종료 합니다. 일치 하는 처리기의 코드가 실행 되 고 프로그램이 종료 코드에 전에 `finally` 분기가 실행 됩니다.

다음 코드에서는 `try...finally` 식입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

콘솔에 출력은 다음과 같습니다.

```
Closing stream
Exception handled.
```

출력에서 볼 수 있듯이 외부 예외를 처리 하기 전에 스트림이 닫히고 및 파일 `test.txt` 텍스트 포함 `test1`, 버퍼 플러시 하 고 예외 전송 디스크에 기록 된 나타냅니다 외부 예외 처리기에 제어 합니다.

`try...with` 구문은 별도에서 `try...finally` 생성 합니다. 따라서 코드 둘 다 요구 하는 경우는 `with` 블록 및 `finally` 블록에서 두 구문이, 다음 코드 예제와 같이 중첩 해야 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

계산 식의 컨텍스트에서 시퀀스 식 및 비동기 워크플로 비롯 한 **try... 마지막** 식에는 사용자 지정 구현을 가질 수 있습니다. 자세한 내용은 참조 [계산 식](../computation-expressions.md)합니다.


## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외: `try...with` 식](the-try-with-expression.md)
