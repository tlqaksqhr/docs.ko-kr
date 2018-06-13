---
title: 클래스의 do 바인딩(F#)
description: "F # 'do' 개체가 생성 될 때 유형을 처음 사용할 때 작업을 수행 하는 클래스 정의에서 바인딩을 사용 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 779b33c44b1518135f4c7f270173ec8124fec101
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565193"
---
# <a name="do-bindings-in-classes"></a>클래스의 do 바인딩

A `do` 클래스 정의에서 바인딩 작업을 수행 개체가 생성 될 때 정적 `do` 바인딩 때 형식을 처음으로 사용 합니다.


## <a name="syntax"></a>구문

```fsharp
[static] do expression
```

## <a name="remarks"></a>설명
A `do` 바인딩 표시와 함께 이후인 `let` 바인딩 클래스 정의의 멤버 정의 보다 앞입니다. 하지만 `do` 키워드는 선택 사항에 대 한 `do` 바인딩에 대 한 선택적 아니므로 모듈 수준에서 `do` 클래스 정의에서 바인딩을 합니다.

지정 된 유형의 static이 아닌의 모든 개체의 생성을 위한 `do` 바인딩 및 비정적 `let` 바인딩 클래스 정의에 나타나는 순서 대로 실행 됩니다. 여러 `do` 바인딩이 한 가지 형식으로 발생할 수 있습니다. 정적이 지 않은 `let` 바인딩 및 정적이 지 않은 `do` 바인딩은 기본 생성자의 본문이 됩니다. 정적이 지 않은 코드 `do` 기본 생성자 매개 변수 및 값 또는 함수에 정의 된 바인딩 섹션 참조할 수는 `let` 바인딩 섹션.

Static이 아닌 `do` 바인딩 클래스에 의해 정의 된 자체 식별자도 클래스의 멤버에 액세스할 수는 `as` 제목과 있다면 해당 멤버의 사용 되는 모든 클래스에 대 한 자체 식별자로 정규화 된 클래스에는 키워드입니다.

때문에 `let` 멤버는 예상 대로 작동 하도록 하는 데 필요한 방식은 클래스의 private 필드를 초기화 하는 바인딩 `do` 바인딩 후 일반적으로 사항이 `let` 하도록 하는 코드에서 바인딩을 `do` 바인딩 수 있습니다 완전히 초기화 된 개체와 함께 실행 합니다. 코드를 초기화가 완료 되기 전에 구성원을 사용 하려고 하는 InvalidOperationException 발생 합니다.

정적 `do` 바인딩은 정적 멤버를 참조할 수 있습니다 또는 묶는 필드 클래스 하지만 하지 인스턴스 멤버 또는 필드입니다. 정적 `do` 바인딩은 클래스를 처음 사용 하기 전에 실행 되는 클래스에 대 한 정적 이니셜라이저의 일부가 됩니다.

에 대 한 특성이 무시 됩니다. `do` 종류에서 바인딩을 합니다. 특성은에서 실행 되는 코드에 필요한 경우 한 `do` 바인딩 적용 해야 기본 생성자에 있습니다.

다음 코드에서는 클래스에 정적 `do` 바인딩 및 static이 아닌 `do` 바인딩. 개체에 두 개의 매개 변수가 있는 생성자 `a` 및 `b`, 두 개의 전용 필드에서 정의 됩니다는 `let` 클래스에 대 한 바인딩을 합니다. 두 가지 속성이 정의 됩니다. 모든 정적이 지 않은의 범위 내에 항목이 `do` 이러한 모든 값을 출력 하는 줄에서 볼 수 있듯이 바인딩 섹션.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

출력은 다음과 같습니다.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>참고 항목
[멤버](index.md)

[클래스](../classes.md)

[생성자](constructors.md)

[클래스의 `let` 바인딩](let-bindings-in-classes.md)

[`do` 바인딩](../functions/do-Bindings.md)
