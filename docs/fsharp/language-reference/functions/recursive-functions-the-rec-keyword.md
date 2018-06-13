---
title: '재귀 함수: rec 키워드(F#)'
description: "F # 'rec' 키워드를 하는 방법을 'let' 키워드와 함께 재귀 함수 정의 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 6039a48eae2b16aa1d82617176460d727a878d87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562923"
---
# <a name="recursive-functions-the-rec-keyword"></a>재귀 함수: rec 키워드

`rec` 키워드와 함께 사용 되는 `let` 재귀 함수를 정의 하는 키워드입니다.


## <a name="syntax"></a>구문

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>설명
재귀 함수는 자기 자신을 호출 하는 함수는 F # 언어에서 명시적으로 식별 됩니다. 이렇게 하면 함수 범위에서 사용할 수 정의 되는 식별자입니다.

다음 코드에서는 재귀 함수를 계산 하는 *n*번째 피보나치 수 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
실제로 그렇게 위의 코드는 이전에 계산 된 값의 다시 계산 기능을 포함 하기 때문에 메모리 및 프로세서 시간을 낭비 됩니다.


메서드는 암시적으로; 형식 내에서 재귀 추가할 필요가 없습니다는 `rec` 키워드입니다. Let 바인딩 클래스 내에서 암시적으로 재귀 되지 않습니다.


## <a name="mutually-recursive-functions"></a>상호 재귀 함수
함수는 경우에 따라 *상호 재귀*, 즉 호출 원, 하나의 함수 호출 하는 경우 호출 하는 첫 번째 개수에 관계 없이 호출 된 다른 사이를 형성 합니다. 번째에서 함께 이러한 함수를 정의 해야 `let` 바인딩을 사용 하는 `and` 키워드를 함께 연결 합니다.

다음 예제에서는 두 번호를 표시 상호 재귀 함수.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>참고 항목
[함수](index.md)
