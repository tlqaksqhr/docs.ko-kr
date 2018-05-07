---
title: 레코드(F#)
description: 'F # 레코드 멤버와 필요에 따라 명명 된 값의 간단한 집계를 표시 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 5bd1f76937bf5839b7da5cae7dea578747ec9b99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="records"></a>레코드

레코드는 명명된 값의 간단한 집계(경우에 따라 멤버가 포함된)를 나타냅니다.  F # 4.1 부터는 하거나 구조체 또는 참조 형식이 될 수 있습니다.  기본적으로 참조 형식입니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a>설명
위 구문에서 *typename* 레코드 종류의 이름인 *label1* 및 *label2* 는 라고 값의 이름 *레이블을*, 및 *type1* 및 *type2* 이러한 값의 형식입니다. *멤버 목록* 멤버 유형에 대 한 선택적 목록입니다.  사용할 수는 `[<Struct>]` 특성 참조 형식인 하는 레코드 대신 구조체 레코드를 만듭니다.

다음은 몇 가지 예입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

각 레이블에 이면 별도 줄에 세미콜론 선택 사항입니다.

라고 하는 식의 값을 설정할 수 *식 기록*합니다. 컴파일러에는 (레이블이 있는 경우 충분히 구별의 다른 레코드 종류)을 사용 하는 레이블 중에서 형식을 유추 합니다. 중괄호 ({}) 레코드 식을 묶습니다. 다음 코드에서는 세 개의 float 요소 레이블 사용 하 여 레코드를 초기화 하는 레코드 식을 `x`, `y` 및 `z`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

다른 형식에도 동일한 레이블이 될 수 있는 경우에 축소 된 형식을 사용 하지 마십시오.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

이전에 선언 된 형식 보다 우선 순위가 높으므로 가장 최근에 선언 된 형식 변수의 여러 레이블을 앞의 예제에는 `mypoint3D` 것으로 유추 `Point3D`합니다. 다음 코드 에서처럼 레코드 종류를 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

클래스 형식 마찬가지로 레코드 형식에 대 한 메서드를 정의할 수 있습니다.

## <a name="creating-records-by-using-record-expressions"></a>레코드 식을 사용 하 여 레코드 만들기
레코드에 정의 되는 레이블을 사용 하 여 레코드를 초기화할 수 있습니다. 이 작업을 수행 하는 식 이라고는 *식 기록*합니다. 레코드 식을 묶는 및 구분 기호로 세미콜론을 사용 하 여 중괄호를 사용 합니다.

다음 예제에는 레코드를 만드는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

레코드 식에서 및 형식 정의의 마지막 필드 뒤에 세미콜론은 필드 모두 한 줄에에서 있는지에 관계 없이 선택적 항목입니다.

레코드를 만들 때 각 필드에 대 한 값을 제공 해야 합니다. 모든 필드에 대 한 초기화 식의 다른 필드의 값을 참조할 수 없습니다.

다음 코드의 형식 `myRecord2` 필드의 이름에서 유추 됩니다. 필요에 따라 형식 이름을 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

레코드 생성의 또 다른 형태 기존 레코드를 복사 하 고 필드 값의 일부를 변경 해야 할 경우 유용할 수 있습니다. 다음 코드 줄은이입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

이 레코드 식이 형식의 라고는 *복사 및 업데이트 레코드 식*합니다.

레코드는 기본적으로 변경할 수 없습니다. 그러나 복사 및 업데이트 식을 사용 하 여 수정 된 레코드를 쉽게 만들 수 있습니다. 변경 가능한 필드를 명시적으로 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

DefaultValue 특성 레코드 필드와 함께 사용 하지 마십시오. 기본값으로 초기화 된 필드와 레코드의 기본 인스턴스를 정의 합니다. 다음 복사본을 사용 및 업데이트 레코드 식 기본 값과 다른 모든 필드를 설정 하는 것이 좋습니다.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a>레코드를 사용한 패턴 일치
레코드 패턴 일치에 사용할 수 있습니다. 일부 필드를 명시적으로 지정 하 고 일치 하는 항목이 때 할당 되는 다른 필드에 대 한 값을 제공할 수 합니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

이 코드의 출력은 다음과 같습니다.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>레코드 및 클래스 간의 차이점
레코드 필드 속성으로 노출 되어 자동으로 생성에 사용 되 고 레코드의 복사 한다는 점에서 클래스에서 다릅니다. 레코드 생성 클래스 생성에서도 다릅니다. 레코드 종류에는 생성자를 정의할 수 없습니다. 대신,이 항목에서 설명한 구문이 적용 됩니다. 클래스는 생성자 매개 변수, 필드 및 속성 간 직접 관계가 있어야 합니다.

공용 구조체 및 구조체 형식 처럼 레코드 구조적 같음 의미 체계를 가져야합니다. 클래스에는 참조 같음 의미 체계입니다. 다음 코드 예제에서는 이 작업을 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

클래스를 사용 하 여 동일한 코드를 작성 하는 경우 두 클래스 개체가 같지 주소만 비교 되며 하 고 두 값은 힙의 두 개체를 나타냅니다 (해당 클래스 형식에서 `System.Object.Equals` 메서드).

레코드에 대 한 같음을 참조 하 고 필요한 경우 추가 특성 `[<ReferenceEquality>]` 레코드 위에 있습니다.

## <a name="see-also"></a>참고 항목
[F# 형식](fsharp-types.md)

[클래스](classes.md)

[F# 언어 참조](index.md)

[참조 같음](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[패턴 일치](pattern-matching.md)
