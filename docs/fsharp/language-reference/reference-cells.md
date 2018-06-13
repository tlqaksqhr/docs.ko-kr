---
title: 참조 셀(F#)
description: 'F # 참조 셀은 참조 의미론을 통해 변경할 수 있는 값을 만들 수 있도록 하는 저장소 위치 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 3a632425356a250f07e5babd2751b9923eec6552
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149064"
---
# <a name="reference-cells"></a><span data-ttu-id="a84a4-103">참조 셀</span><span class="sxs-lookup"><span data-stu-id="a84a4-103">Reference Cells</span></span>

<span data-ttu-id="a84a4-104">*참조 셀* 참조 의미론을 통해 변경할 수 있는 값을 만들 수 있도록 하는 저장소 위치 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="a84a4-105">구문</span><span class="sxs-lookup"><span data-stu-id="a84a4-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="a84a4-106">설명</span><span class="sxs-lookup"><span data-stu-id="a84a4-106">Remarks</span></span>
<span data-ttu-id="a84a4-107">값 앞에 `ref` 연산자를 사용하여 값을 캡슐화하는 새 참조 셀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="a84a4-108">이는 변경 가능한 변수이므로 참조 셀을 만든 다음 내부 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="a84a4-109">참조 셀은 단순한 주소가 아니라 실제 값을 저장하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="a84a4-110">`ref` 연산자를 사용하여 참조 셀을 만들면 캡슐화되고 변경 가능한 값으로 내부 값의 복사본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="a84a4-111">`!`(느낌표) 연산자를 사용하여 참조 셀을 역참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="a84a4-112">다음 코드 예제에서는 참조 셀을 선언하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="a84a4-113">출력은 `50`입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-113">The output is `50`.</span></span>

<span data-ttu-id="a84a4-114">참조 셀은 다음과 같이 선언되는 `Ref` 제네릭 레코드 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="a84a4-115">형식 `'a ref`는 `Ref<'a>`와 같은 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="a84a4-116">IDE의 컴파일러와 IntelliSense에서는 이 형식을 전자와 같이 표시하지만 그 내부 정의는 후자와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="a84a4-117">`ref` 연산자는 새 참조 셀을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="a84a4-118">다음 코드는 `ref` 연산자의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="a84a4-119">다음 표에는 참조 셀에 사용할 수 있는 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="a84a4-120">연산자, 멤버 또는 필드</span><span class="sxs-lookup"><span data-stu-id="a84a4-120">Operator, member, or field</span></span>|<span data-ttu-id="a84a4-121">설명</span><span class="sxs-lookup"><span data-stu-id="a84a4-121">Description</span></span>|<span data-ttu-id="a84a4-122">형식</span><span class="sxs-lookup"><span data-stu-id="a84a4-122">Type</span></span>|<span data-ttu-id="a84a4-123">정의</span><span class="sxs-lookup"><span data-stu-id="a84a4-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="a84a4-124">`!`(역참조 연산자)</span><span class="sxs-lookup"><span data-stu-id="a84a4-124">`!` (dereference operator)</span></span>|<span data-ttu-id="a84a4-125">내부 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="a84a4-126">`:=`(할당 연산자)</span><span class="sxs-lookup"><span data-stu-id="a84a4-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="a84a4-127">내부 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="a84a4-128">`ref`(연산자)</span><span class="sxs-lookup"><span data-stu-id="a84a4-128">`ref` (operator)</span></span>|<span data-ttu-id="a84a4-129">값을 새 참조 셀로 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="a84a4-130">`Value`(속성)</span><span class="sxs-lookup"><span data-stu-id="a84a4-130">`Value` (property)</span></span>|<span data-ttu-id="a84a4-131">내부 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="a84a4-132">`contents`(레코드 필드)</span><span class="sxs-lookup"><span data-stu-id="a84a4-132">`contents` (record field)</span></span>|<span data-ttu-id="a84a4-133">내부 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="a84a4-134">내부 값에 액세스하는 데는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="a84a4-135">역참조 연산자(`!`)를 통해 반환되는 값은 할당 가능한 값이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="a84a4-136">따라서 내부 값을 수정하는 경우에는 할당 연산자(`:=`)를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="a84a4-137">`Value` 속성과 `contents` 필드는 둘 다 할당 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="a84a4-138">따라서 다음 코드에서와 같이 이들 속성과 필드를 사용하여 내부 값에 액세스하거나 내부 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="a84a4-139">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="a84a4-140">필드 `contents`는 다른 ML 버전과의 호환성을 위해 제공되며 컴파일 과정에서 이 필드로 인해 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="a84a4-141">경고가 발생하지 않도록 하려면 `--mlcompatibility` 컴파일러 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="a84a4-142">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a84a4-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="a84a4-143">다음 코드에서는 매개 변수 전달에 참조 셀을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-143">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="a84a4-144">증분 형식에는 메서드가 증가 byref 매개 변수 형식에 포함 된 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-144">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="a84a4-145">매개 변수 형식에 byref 호출자에 게 전달 해야 한다는 의미 지정 된 형식의 일반적인 변수에 대 한 주소 또는 참조 셀이 case 없는 정수에 코드의 나머지 부분 모두 이러한 유형의 인수를 사용 하 여 증분을 호출 하는 방법을 보여 줍니다. 하 고 변수에 참조 셀 (ref myDelta1) 만들 수는 ref 연산자의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-145">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="a84a4-146">그런 다음 이 예제에서는 주소 연산자(&amp;)를 사용하여 적절한 인수를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-146">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="a84a4-147">마지막으로, 증분 메서드를 할 수 있도록된 바인딩을 사용 하 여 선언한 참조 셀을 사용 하 여 다시 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-147">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="a84a4-148">코드의 마지막 줄의 사용법을 보여줍니다는!</span><span class="sxs-lookup"><span data-stu-id="a84a4-148">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="a84a4-149">연산자는 인쇄할 참조 셀을 역참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-149">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="a84a4-150">참조로 전달 하는 방법에 대 한 자세한 내용은 참조 [매개 변수 및 인수](parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-150">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="a84a4-151">C# 프로그래머는 ref 다르게 작동 F #에서 C#에서 사용 하지 않고 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-151">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="a84a4-152">예를 들어 인수를 전달 하는 경우 ref 사용 않아도 같습니다 F #에서 C#에서 마찬가지로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-152">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

>[!NOTE]
<span data-ttu-id="a84a4-153">`mutable` 변수를 자동으로 승격 될 수 있습니다 `'a ref` 클로저;에 의해 캡처된 참조 [값](values/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-153">`mutable` variables may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="a84a4-154">C# 사용 `ref` 반환</span><span class="sxs-lookup"><span data-stu-id="a84a4-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="a84a4-155">사용할 수 있는 F # 4.1 부터는 `ref` C#의 생성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="a84a4-156">이러한 호출의 결과 `byref<_>` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="a84a4-157">다음 C# 메서드.</span><span class="sxs-lookup"><span data-stu-id="a84a4-157">The following C# method:</span></span>

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

<span data-ttu-id="a84a4-158">투명 하 게 호출할 수 F #에서 특별 한 구문 없음:</span><span class="sxs-lookup"><span data-stu-id="a84a4-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="a84a4-159">걸릴 수도 있는 함수를 선언할 수도 있습니다는 `ref` 예를 들어를 입력으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="a84a4-160">현재 생성 하려면 방법이 있으면는 `ref` C#에서 소비 될 수 있는 F #에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a84a4-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="a84a4-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a84a4-161">See Also</span></span>
[<span data-ttu-id="a84a4-162">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="a84a4-162">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a84a4-163">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="a84a4-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="a84a4-164">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="a84a4-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)

[<span data-ttu-id="a84a4-165">값</span><span class="sxs-lookup"><span data-stu-id="a84a4-165">Values</span></span>](values/index.md)
