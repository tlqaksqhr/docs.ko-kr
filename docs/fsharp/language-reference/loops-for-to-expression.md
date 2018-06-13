---
title: '루프: for...to 식(F#)'
description: '참조 방식을 F # >for.. 식으로 하는 데 루프 변수 값의 범위에 대해 루프를 반복 합니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563404"
---
# <a name="loops-forto-expression"></a>루프: for...to 식

`for...to` 식은 루프 변수 값의 범위에 대해 루프를 반복 하는 데 사용 됩니다.


## <a name="syntax"></a>구문

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>설명
식별자의 형식은 형식에서 유추 됩니다는 *시작* 및 *마침* 식입니다. 이러한 식에 대 한 형식에는 32 비트 정수 여야 합니다.

하지만 식을 기술적으로 `for...to` 는 더 일반적인 명령형 프로그래밍 언어의 문에 같습니다. 반환 형식에는 *본문 식* 해야 `unit`합니다. 다음 예제에서는 보여의 다양 한 용도 `for...to` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

위 코드는 다음과 같이 출력됩니다.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[루프: `for...in` 식](loops-for-in-expression.md)

[루프: `while...do` 식](loops-while-do-expression.md)
