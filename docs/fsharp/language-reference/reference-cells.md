---
title: 참조 셀(F#)
description: 'F # 참조 셀은 참조 의미론을 통해 변경할 수 있는 값을 만들 수 있도록 하는 저장소 위치 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e017adb2a031dff996892e2bb6585fc95f644ff9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="reference-cells"></a>참조 셀

*참조 셀* 참조 의미론을 통해 변경할 수 있는 값을 만들 수 있도록 하는 저장소 위치 같습니다.

## <a name="syntax"></a>구문

```fsharp
ref expression
```

## <a name="remarks"></a>설명
값 앞에 `ref` 연산자를 사용하여 값을 캡슐화하는 새 참조 셀을 만들 수 있습니다. 이는 변경 가능한 변수이므로 참조 셀을 만든 다음 내부 값을 변경할 수 있습니다.

참조 셀은 단순한 주소가 아니라 실제 값을 저장하는 위치입니다. `ref` 연산자를 사용하여 참조 셀을 만들면 캡슐화되고 변경 가능한 값으로 내부 값의 복사본이 만들어집니다.

`!`(느낌표) 연산자를 사용하여 참조 셀을 역참조할 수 있습니다.

다음 코드 예제에서는 참조 셀을 선언하고 사용하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

출력은 `50`입니다.

참조 셀은 다음과 같이 선언되는 `Ref` 제네릭 레코드 형식의 인스턴스입니다.

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

형식 `'a ref`는 `Ref<'a>`와 같은 의미입니다. IDE의 컴파일러와 IntelliSense에서는 이 형식을 전자와 같이 표시하지만 그 내부 정의는 후자와 같습니다.

`ref` 연산자는 새 참조 셀을 만드는 데 사용됩니다. 다음 코드는 `ref` 연산자의 선언입니다.

```fsharp
let ref x = { contents = x }
```

다음 표에는 참조 셀에 사용할 수 있는 기능이 나와 있습니다.

|연산자, 멤버 또는 필드|설명|형식|정의|
|--------------------------|-----------|----|----------|
|`!`(역참조 연산자)|내부 값을 반환합니다.|`'a ref -> 'a`|`let (!) r = r.contents`|
|`:=`(할당 연산자)|내부 값을 변경합니다.|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|`ref`(연산자)|값을 새 참조 셀로 캡슐화합니다.|`'a -> 'a ref`|`let ref x = { contents = x }`|
|`Value`(속성)|내부 값을 가져오거나 설정합니다.|`unit -> 'a`|`member x.Value = x.contents`|
|`contents`(레코드 필드)|내부 값을 가져오거나 설정합니다.|`'a`|`let ref x = { contents = x }`|
내부 값에 액세스하는 데는 여러 가지 방법이 있습니다. 역참조 연산자(`!`)를 통해 반환되는 값은 할당 가능한 값이 아닙니다. 따라서 내부 값을 수정하는 경우에는 할당 연산자(`:=`)를 대신 사용해야 합니다.

`Value` 속성과 `contents` 필드는 둘 다 할당 가능한 값입니다. 따라서 다음 코드에서와 같이 이들 속성과 필드를 사용하여 내부 값에 액세스하거나 내부 값을 변경할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

출력은 다음과 같습니다.

```
10
10
11
12
```

필드 `contents`는 다른 ML 버전과의 호환성을 위해 제공되며 컴파일 과정에서 이 필드로 인해 경고가 발생합니다. 경고가 발생하지 않도록 하려면 `--mlcompatibility` 컴파일러 옵션을 사용해야 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.

다음 코드에서는 매개 변수 전달에 참조 셀을 사용하는 방법을 보여 줍니다. 증분 형식에는 메서드가 증가 byref 매개 변수 형식에 포함 된 매개 변수를 사용 합니다. 매개 변수 형식에 byref 호출자에 게 전달 해야 한다는 의미 지정 된 형식의 일반적인 변수에 대 한 주소 또는 참조 셀이 case 없는 정수에 코드의 나머지 부분 모두 이러한 유형의 인수를 사용 하 여 증분을 호출 하는 방법을 보여 줍니다. 하 고 변수에 참조 셀 (ref myDelta1) 만들 수는 ref 연산자의 사용을 보여 줍니다. 그런 다음 이 예제에서는 주소 연산자(&amp;)를 사용하여 적절한 인수를 생성하는 방법을 보여 줍니다. 마지막으로, 증분 메서드를 할 수 있도록된 바인딩을 사용 하 여 선언한 참조 셀을 사용 하 여 다시 호출 됩니다. 코드의 마지막 줄의 사용법을 보여줍니다는! 연산자는 인쇄할 참조 셀을 역참조입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

참조로 전달 하는 방법에 대 한 자세한 내용은 참조 [매개 변수 및 인수](parameters-and-arguments.md)합니다.

>[!NOTE]
C# 프로그래머는 ref 다르게 작동 F #에서 C#에서 사용 하지 않고 알고 있어야 합니다. 예를 들어 인수를 전달 하는 경우 ref 사용 않아도 같습니다 F #에서 C#에서 마찬가지로 됩니다.

## <a name="consuming-c-ref-returns"></a>C# 사용 `ref` 반환

사용할 수 있는 F # 4.1 부터는 `ref` C#의 생성을 반환 합니다.  이러한 호출의 결과 `byref<_>` 포인터입니다.

다음 C# 메서드.

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

투명 하 게 호출할 수 F #에서 특별 한 구문 없음:

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

걸릴 수도 있는 함수를 선언할 수도 있습니다는 `ref` 예를 들어를 입력으로 반환 합니다.

```fsharp
let f (x: byref<int>) = &x
```

현재 생성 하려면 방법이 있으면는 `ref` C#에서 소비 될 수 있는 F #에서 반환 합니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[매개 변수 및 인수](parameters-and-arguments.md)

[기호 및 연산자 참조](symbol-and-operator-reference/index.md)
