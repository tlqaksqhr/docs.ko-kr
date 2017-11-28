---
title: "구조체(F#)"
description: "F # 구조, 종종 간단한 개체 형식에 대 한 자세한 내용은 적은 양의 데이터 적고 동작이 단순한 형식에 대 한 클래스 보다 더 효율적입니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a>구조체

A *구조* 는 적은 양의 데이터 적고 동작이 단순한 변수가 있는 형식에 대 한 클래스 보다 효율적일 수 있는 간단한 개체 형식입니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a>설명
구조체는 *값 형식이*, 스택에 직접 또는으로 사용 되는 저장 된 의미 하는 필드 또는 배열 요소, 부모에서 인라인으로 입력 합니다. 클래스나 레코드와 달리 구조체는 pass-by-value 의미 체계를 포함합니다. 따라서 기본적으로 자주 액세스 및 복사하는 소규모 데이터 집계에 유용합니다.

위 구문에는 두 개의 폼이 표시되어 있습니다. 첫 번째는 간단한 구문은 아니지만 자주 사용됩니다. `struct` 및 `end` 키워드를 사용하는 경우 두 번째 구문에 나와 있는 `StructAttribute` 특성을 생략할 수 있기 때문입니다. 즉, `StructAttribute`를 `Struct`로 간략하게 작성할 수 있습니다.

*형식 정의-요소* 위 구문 멤버 선언 및 정의 나타냅니다. 구조체는 생성자 및 변경 가능/불가능한 필드를 포함할 수 있으며 멤버 및 인터페이스 구현을 선언할 수 있습니다. 자세한 내용은 참조 [멤버](members/index.md)합니다.

구조체는 상속에 참가할 수 없고, `let` 또는 `do` 바인딩을 포함할 수 없으며, 자신의 형식으로 된 필드를 재귀적으로 포함할 수 없습니다. 그러나 자신의 형식을 참조하는 참조 셀은 포함할 수 있습니다.

구조체는 `let` 바인딩을 허용하지 않으므로 구조체에서는 `val` 키워드를 사용하여 필드를 선언해야 합니다. `val` 키워드는 필드와 해당 형식을 정의하지만 초기화는 허용하지 않습니다. 대신 `val` 선언이 null 또는 0으로 초기화됩니다. 따라서 암시적 생성자(선언에서 구조체 이름 바로 뒤에 지정되는 매개 변수)를 포함하는 구조체에서는 `val` 선언을 `DefaultValue` 특성으로 주석 처리해야 합니다. 정의된 생성자가 있는 구조체도 0으로의 초기화를 지원합니다. 그러므로 `DefaultValue` 특성은 이러한 0 값이 필드에 유효함을 나타내는 선언입니다. 구조체의 암시적 생성자는 아무런 작업도 수행하지 않습니다. 해당 형식에 대해서는 `let` 및 `do` 바인딩이 허용되지 않지만 전달되는 암시적 생성자 매개 변수 값은 개인 필드로 사용할 수 있기 때문입니다.

명시적 생성자에서는 필드 값이 초기화될 수 있습니다. 명시적 생성자를 포함하는 구조체는 0으로의 초기화도 지원합니다. 그러나 `DefaultValue` 선언에서 `val` 특성을 사용하는 경우 명시적 생성자와 충돌하므로 해당 특성은 사용하지 않아야 합니다. 에 대 한 자세한 내용은 `val` 선언 참조 [명시적 필드:는 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.

특성 및 액세스 가능성 한정자는 구조체에서 허용되며 다른 형식과 동일한 규칙을 따릅니다. 자세한 내용은 참조 [특성](attributes.md) 및 [액세스 제어](access-control.md)합니다.

다음 코드 예제에서는 구조체 정의를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a>구조체 레코드 및 구분 된 공용 구조체

표현할 수 있는 F # 4.1 부터는 [레코드](records.md) 및 [구별 된 공용 구조체](discriminated-unions.md) 와 구조체로 `[<Struct>]` 특성입니다.  자세한 내용을 보려면 각 문서를 참조 합니다.
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[클래스](classes.md)

[레코드](records.md)

[멤버](members/index.md)
