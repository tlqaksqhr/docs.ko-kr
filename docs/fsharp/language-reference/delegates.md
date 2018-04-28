---
title: 대리자(F#)
description: 'F #에서 대리자와 작업 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a>대리자

대리자는 개체와 함수 호출을 나타냅니다. F #에서 일반적으로 값을 사용 해야 함수를 고급 값으로; 함수를 나타내는 그러나 대리자는.NET Framework에서 사용 및 있으므로 시기와 필요한 예상 대로 Api와 상호 운용 합니다. 있습니다 사용할 수도 있습니다 다른.NET Framework 언어에서 사용 하기 위한 라이브러리를 작성할 때.


## <a name="syntax"></a>구문

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>설명
위 구문에서 `type1` 인수 형식 또는 형식 및 `type2` 반환 형식을 나타냅니다. 으로 표현 되는 인수 형식을 `type1` 자동 변환 됩니다. 튜플 형식에 이미 있는 인수에 대 한 괄호로 묶인 튜플 및 튜플 형식을 사용 하 여 대상 함수의 인수 변환 되는 경우이 형식에 대 한는 원인 중 하나입니다. 자동 커리 대상 메서드를 일치 하는 튜플 인수가 괄호를 제거 합니다. 각 경우에 사용 해야 하는 구문에 대 한 코드 예제를 참조 하십시오.

대리자는 F # 값, 및 정적 첨부할 수 또는 인스턴스 메서드. F # 값 대리 생성자에 인수로 직접 전달할 수 있습니다. 정적 메서드에 대 한 클래스 및 메서드 이름을 사용 하 여 대리자를 구성 합니다. 인스턴스 메서드를 개체 인스턴스와 메서드 하나의 인수를 제공 해야 합니다. 두 경우 모두, 멤버 액세스 연산자 (`.`) 사용 됩니다.

`Invoke` 대리자 형식의 메서드는 캡슐화 된 함수를 호출 합니다. 또한 대리자는 괄호 없이 Invoke 메서드 이름을 참조 하 여 함수 값으로 전달할 수 있습니다.

다음 코드는 클래스의 다양 한 메서드를 나타내는 대리자를 만드는 구문을 보여 줍니다. 메서드는 정적 메서드 또는 인스턴스 메서드를 인지 및 인수에 튜플 형식 또는 변환된 형식 있는지에 따라 선언 하 고 대리자를 할당 하는 구문은 약간 차이가 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

다음 코드에서는 작업할 수 있는 대리자 다양 한 방법으로 일부를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

이전 코드 예제의 출력은 다음과 같습니다.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[매개 변수 및 인수](parameters-and-arguments.md)

[이벤트](members/events.md)
