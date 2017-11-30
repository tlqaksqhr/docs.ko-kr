---
title: "추상 클래스(F#)"
description: "다양 한 개체 유형 집합의 공통 기능을 나타내는 및 F # 추상 클래스에 구현 되지 않았으며 일부 또는 모든 멤버가 둡니다 알아보십시오."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 209bcca70318db59506011b1f2bb74a09bf3814a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="abstract-classes"></a>추상 클래스

*추상 클래스* 한 클래스 파생된 클래스에서 구현할 수 있도록 구현 되지 않았으며, 일부 또는 모든 멤버가 둡니다.

## <a name="syntax"></a>구문

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>설명
개체 지향 프로그래밍에서 추상 클래스는 계층의 기본 클래스로 사용 되 고 다양 한 개체 유형 집합의 공통 기능을 나타냅니다. "추상" 이름에서 알 수 있듯이 추상 클래스 종종 맞지 않는 문제 도메인의 구체적인 엔터티에 직접 드롭하면 합니다. 그러나 어떤 다른 여러 구체적인 엔터티에 서로 공통 되는 표현 않는다는 사실을 합니다.

추상 클래스에 있어야는 `AbstractClass` 특성입니다. 구현 및 멤버를 구현 되지 않았으며 있을 수 있습니다. 그러나 용어를 사용 하는 *추상* 클래스는 다른.NET 언어; 동일에 적용 될 때 용어의 사용 *추상* 메서드 (및 속성)에 적용 될 때 F #에서 약간 다르게은 해당 다른.NET 언어에서 사용 합니다. F #에서는으로 표시 되는 메서드는 `abstract` 키워드,이 멤버가 의미 이라고 하는 항목을는 *가상 디스패치 슬롯*, 해당 형식에 대 한 가상 함수의 내부 테이블에 있습니다. 즉, 메서드는 virtual 이거나 있지만 `virtual` 키워드는 F # 언어에서 사용 되지 않습니다. 키워드 `abstract` 메서드가 구현 여부에 관계 없이 가상 메서드에 사용 됩니다. 가상 디스패치 슬롯의 선언 해당 디스패치 슬롯에 대 한 메서드의 정의와 분리 됩니다. 따라서 F #의 해당 가상 메서드 선언 및 정의 다른.NET 언어에는 추상 메서드 선언 및 사용 하 여 별도 정의 모두의 결합 된 `default` 키워드 또는 `override` 키워드입니다. 자세한 내용 및 예제에 대 한 참조 [메서드](members/methods.md)합니다.

클래스는 선언 되지만 정의 되지 않은 추상 메서드가 필요한 경우에 추상 간주 됩니다. 따라서 추상 메서드가 있는 클래스는 필수적으로 추상화 클래스가 아닙니다. 클래스의 추상 메서드를 정의 되지 않은 경우가 아니면 사용 하지 않습니다는 **AbstractClass** 특성입니다.

위 구문에서 *접근성 한정자* 수 `public`, `private` 또는 `internal`합니다. 자세한 내용은 [액세스 제어](access-control.md)를 참조하세요.

다른 형식과 마찬가지로 추상 클래스는 기본 클래스 및 하나 이상의 기본 인터페이스 있을 수 있습니다. 각 기본 클래스 또는 인터페이스와 함께 별도 줄에 표시 되는 `inherit` 키워드입니다.

추상 클래스의 형식 정의는 완벽 하 게 정의 된 멤버를 포함할 수 있습니다 하지만 추상 멤버를 포함할 수도 있습니다. 추상 멤버에 대 한 구문 위 구문에서 별도로 표시 됩니다. 이 구문에서는 *형식 시그니처* 멤버의 목록을 포함 하는 매개 변수 형식 및 반환 형식, 순서 대로 구분 된 `->` 토큰 및/또는 `*` 변환에 대 한 적절 하 게 토큰 및 튜플 매개 변수입니다. 추상 멤버 형식 서명에 대 한 구문은 서명 파일에서 사용 하 고 Visual Studio 코드 편집기의 IntelliSense에서 표시는 동일 합니다.

다음 코드에서는 추상 클래스를 비추상 파생된 클래스 2 개의 정사각형, 원에 셰이프를 보여 줍니다. 이 예제에서는 추상 클래스, 메서드 및 속성을 사용 하는 방법을 보여 줍니다. 예제에서는 추상 클래스 셰이프는 구체적인 엔터티 원과 사각형의 공통 요소를 나타냅니다. 모든 셰이프 (2 차원 좌표 상의)의 일반적인 기능 Shape 클래스에 추상화 됩니다: 눈금 위치, 회전의 각도, 영역 및 주변 속성입니다. 이 재정의할 수 있습니다 위치에 없는 개별 셰이프를 변경할 수 없습니다 동작 제외 하 고 있습니다.

회전 고정 되어이 해당 대칭 Circle 클래스와 같이 회전 메서드를 재정의할 수 있습니다. 따라서 Circle 클래스 회전 메서드는 아무 작업도 수행 하는 메서드로 대체 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**출력:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>참고 항목
[클래스](classes.md)

[멤버](members/index.md)

[메서드](members/methods.md)

[속성](members/Properties.md)
