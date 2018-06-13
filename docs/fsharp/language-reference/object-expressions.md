---
title: 개체 식(F#)
description: '명명 된 형식을 추가 코드와 새로 만드는 데 필요한 오버 헤드를 방지 하려면 때 F # 식을 개체를 사용 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564393"
---
# <a name="object-expressions"></a>개체 식

*식 개체* 하는 개체를 동적으로 생성, 익명 형식의 새 인스턴스를 만드는 되는 식을 기반으로 기존의 기본 형식, 인터페이스 또는 인터페이스 집합이 합니다.


## <a name="syntax"></a>구문

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>설명
위 구문에는 *typename* 은 기존 클래스 형식 또는 인터페이스 형식입니다. *형식 매개 변수* 선택적 제네릭 형식 매개 변수에 대해 설명 합니다. *인수* 생성자 매개 변수를 요구 하는 클래스 형식에만 사용 됩니다. *멤버 정의* 기본 클래스 메서드의 재정의 또는 기본 클래스 또는 인터페이스에서 추상 메서드의 구현 됩니다.

다음 예제는 여러 다른 종류의 개체 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>개체 식 사용
개체 식을 사용 하 여 추가 코드와 명명 된 형식을 새로 만드는 데 필요한는 오버 헤드를 방지 하려는 경우. 프로그램에서 만든 형식의 수를 최소화 하기 위해 개체 식을 사용 하는 경우 코드의 줄 수가 줄어들 수 있으며 형식의 불필요 한 확산을 방지. 특정 상황을 처리할 수만 많은 종류를 만드는 대신 기존 형식의 사용자 지정 하거나 특정 사례에 대 한 적절 한 인터페이스의 구현을 제공 하는 개체 식을 사용할 수 있습니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
