---
title: 클래스의 let 바인딩(F#)
description: "클래스 정의에서 'let' 바인딩을 사용 하 여 private 필드 및 F # 클래스에 대 한 전용 함수를 정의 하는 방법을 알아봅니다."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: c4511a541403dde517acaf902e86de8d48f13781
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings-in-classes"></a>클래스의 let 바인딩

Private 필드 및 F # 클래스에 대 한 전용 함수를 사용 하 여 정의할 수 있습니다 `let` 클래스 정의에 바인딩.


## <a name="syntax"></a>구문

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>설명
위 구문 자 클래스 상속 및 제목을 선언 뒤, 다른 모든 멤버 정의 앞에 나타납니다. 구문은 `let` 클래스에 제한 된 범위가 클래스, 하지만 클래스에 정의 된 이름은 외부에서 바인딩. A `let` 바인딩을 전용 필드 또는 데이터를 노출 하려면 함수를 통해 또는 함수는 속성 또는 멤버 메서드를 공개적으로 선언 합니다.

A `let` 바인딩에 없는 정적 인스턴스 라고 `let` 바인딩. 인스턴스 `let` 바인딩은 개체가 만들어질 때 실행 됩니다. 정적 `let` 바인딩 형식을 처음으로 사용 하기 전에 실행 되는 클래스에 대 한 정적 이니셜라이저의 일부인 합니다.

인스턴스 내에서 코드 `let` 바인딩에서는 기본 생성자의 매개 변수를 사용할 수 있습니다.

특성 및 액세스 가능성 한정자에 허용 되지 않는 `let` 클래스에서 합니다.

다음 코드 예제에서는 여러 유형의 설명 `let` 클래스에서 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

출력은 다음과 같습니다.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>필드를 만드는 다른 방법
사용할 수도 있습니다는 `val` 키워드 전용 필드를 만들려고 합니다. 사용 하는 경우는 `val` 키워드를 필드 값이 주어 지는 개체를 만들었지만 대신 기본 값으로 초기화 하는 경우. 자세한 내용은 참조 [명시적 필드: val 키워드](explicit-fields-the-val-keyword.md)합니다.

멤버 정의 사용 하는 키워드를 추가 하 여 클래스에서 private 필드를 정의할 수도 있습니다 `private` 을 정의 합니다. 이 코드를 다시 작성 하지 않고 멤버의 액세스 가능성을 변경 하려는 경우에 유용할 수 있습니다. 자세한 내용은 [액세스 제어](../access-control.md)를 참조하세요.

## <a name="see-also"></a>참고 항목
[멤버](index.md)

[클래스의 `do` 바인딩](do-bindings-in-classes.md)

[`let` 바인딩](../functions/let-bindings.md)
