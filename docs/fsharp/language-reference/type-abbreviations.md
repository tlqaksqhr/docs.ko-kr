---
title: 형식 약어(F#)
description: '형식에 이름을 보다 의미 있는 코드를 보다 쉽게 읽을 수 있도록 F # 형식 약어에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="type-abbreviations"></a>형식 약어

A *형식 약어* 별칭 또는 유형에 대 한 대체 이름입니다.

## <a name="syntax"></a>구문

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>설명
코드를 보다 쉽게 읽을 수 있도록 형식을 더 의미 있는 이름을 부여 하려면 형식 약어를 사용할 수 있습니다. 작성 하는 경우 다루기 되는 형식에 대 한 사용 하기 쉬운 이름을 만들 수도 사용할 수 있습니다. 또한 쉽게 형식을 사용 하는 모든 코드를 변경 하지 않고 내부 형식을 변경할 수 있도록 형식 약어를 사용할 수 있습니다. 다음은 단순 형식 약어입니다.

기본 형식 약어의 액세스 권한은 `public`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

형식 약어에는 다음 코드 에서처럼 일반 매개 변수를 포함할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

이전 코드에서 `Transform` 동일한 형식의 단일 값을 반환 하 고 모든 형식의 단일 인수를 사용 하는 함수를 나타내는 형식 약어입니다.

.NET Framework MSIL 코드에서 형식 약어 유지 되지 않습니다. 따라서 다른.NET Framework 언어에서 F # 어셈블리를 사용 하면 형식 약어에 대 한 내부 형식 이름을 사용 해야 합니다.

측정 단위에 형식 약어를 사용할 수도 있습니다. 자세한 내용은 참조 [측정 단위를](units-of-measure.md)합니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

