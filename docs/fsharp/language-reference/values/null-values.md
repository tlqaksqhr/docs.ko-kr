---
title: Null 값(F#)
description: 'F # 프로그래밍 언어에서 null 값이 사용 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 8d302cc78c5de582f58c6f9b9dea7b23ee7ddfea
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="null-values"></a>Null 값

이 항목에서는 F #에서 null 값이 사용 하는 방법을 설명 합니다.


## <a name="null-value"></a>Null 값
Null 값은 사용 되지 않습니다 일반적으로 F #에서 값 또는 변수. 그러나 특정 상황에서 비정상적인 값으로 null이 나타납니다. F #에 형식이 정의 되어, null은 허용 되지 않습니다 일반 값으로 하지 않는 한는 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) 특성 형식에 적용 됩니다. 일부 다른.NET 언어에는 형식이 정의 되어, null은 가능한 값을 및 이러한 유형과 상호 운용, 하는 경우 F # 코드에서는 null 값이 발생할 수 있습니다.

형식의 정의 F # 및 F #에서 엄격 하 게 사용, 사용 하는 유일한 방법은 직접 F # 라이브러리를 사용 하 여 null 값을 만들 수는 [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) 또는 [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)합니다. 그러나 다른.NET 언어에서 사용 되는 F # 형식에 대 한 또는 F #으로.NET Framework 같은 기록 되지 않습니다는 API를 통해 해당 형식을 사용 하는 경우에 null 값 발생할 수 있습니다.

사용할 수는 `option` F # 가능한 값이 다른.NET 언어에서 null 인 참조 변수를 사용할 수 있는 경우의 형식입니다. F # null 대신 `option` 형식 옵션 값을 사용 하 여 `None` 개체가 없는 경우. 옵션 값을 사용 하 여 `Some(obj)` 개체와 `obj` 개체 하는 경우. 자세한 내용은 참조 [옵션](../options.md)합니다.

`null` 키워드는 유효한 F # 언어, 키워드 및.NET Framework Api 또는 다른.NET 언어에서 작성 된 다른 Api를 사용 하 여 작업할 때 사용 해야 합니다. Null 값을 할 수 있는 두 가지 경우는.NET API를 호출 하 고, 인수로 null 값을 전달 하는 경우 반환 값 또는.NET 메서드 호출에서 출력 매개 변수를 해석할 때 되며 있습니다.

.NET 메서드를 null 값을 전달 하려면 사용 하는 `null` 호출 코드에서 키워드입니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

.NET 메서드에서 가져온 null 값을 해석, 가능 하면 패턴 일치를 사용 합니다. 다음 코드 예제에서는에서 반환 되는 null 값을 해석 하려면 패턴 일치를 사용 하는 방법을 보여 줍니다. `ReadLine` 입력 스트림의 끝을 지나서 읽으려고 할 것입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

F # 형식에 대 한 null 값 사용 하는 경우와 같은 다른 방법으로 생성할 수도 있습니다 `Array.zeroCreate`, 되는 호출 `Unchecked.defaultof`합니다. 캡슐화 된 null 값을 유지 하려면이 코드로 주의 해야 합니다. 만 위한 F # 라이브러리에서는 모든 함수에 null 값을 검사할 필요가 없습니다. 다른.NET 언어와의 상호 운용성에 대 한 라이브러리를 작성 하는 경우 null에 대 한 검사 입력 매개 변수 및 throw를 추가 해야 할 수 있습니다 있습니다는 `ArgumentNullException`것 처럼 C# 또는 Visual Basic 코드에서 작업을 수행 합니다.

임의의 값이 null 인지 확인 하려면 다음 코드를 사용할 수 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>참고 항목
[값](index.md)

[일치 식](../match-expressions.md)
