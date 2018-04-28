---
title: 튜플(F#)
description: 'F # 튜플, 명명 되지 않았지만 순서가 지정 된 값의 그룹에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9710f4996a952fdeaab07a30916215f27969e1a3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="tuples"></a><span data-ttu-id="9adbf-103">튜플</span><span class="sxs-lookup"><span data-stu-id="9adbf-103">Tuples</span></span>

<span data-ttu-id="9adbf-104">A *튜플* 은 명명 되지 않았지만 순서가 지정 된 값의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="9adbf-105">튜플 참조 형식 또는 구조체 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="9adbf-106">구문</span><span class="sxs-lookup"><span data-stu-id="9adbf-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="9adbf-107">설명</span><span class="sxs-lookup"><span data-stu-id="9adbf-107">Remarks</span></span>
<span data-ttu-id="9adbf-108">각 *요소* 위 구문에서 올바른 F # 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="9adbf-109">예제</span><span class="sxs-lookup"><span data-stu-id="9adbf-109">Examples</span></span>
<span data-ttu-id="9adbf-110">튜플의 예로 쌍, 삼중 쌍, 등과 같은 종류나 다른 종류의를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="9adbf-111">몇 가지 예는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="9adbf-112">개별 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="9adbf-112">Obtaining Individual Values</span></span>
<span data-ttu-id="9adbf-113">사용할 수 있습니다 패턴 일치를 액세스 하 여 튜플 요소에 이름을 할당 다음 코드에 나와 있는 것 처럼.</span><span class="sxs-lookup"><span data-stu-id="9adbf-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="9adbf-114">외부의 패턴 일치를 통해 튜플을 해체 또한 수는 `match` 식을 통해 `let` 바인딩:</span><span class="sxs-lookup"><span data-stu-id="9adbf-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="9adbf-115">Or 패턴 수 튜플 함수에 대 한 입력으로 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="9adbf-116">튜플의 요소가 하나만 필요한 경우 와일드 카드 문자 (밑줄) 필요 하지 않은 값에 대 한 새 이름을 않도록 하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="9adbf-117">구조체 튜플로 참조 튜플에서 요소를 복사 하는 또한 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="9adbf-118">함수 `fst` 및 `snd` (튜플만 참조) 첫 번째 반환 하 고 각각 요소 튜플의 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="9adbf-119">튜플의 세 번째 요소를 반환 하는 기본 제공 함수가 있지만 쉽게 작성할 수 있습니다 하나 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="9adbf-120">일반적으로 개별 튜플 요소에 액세스 하려면 패턴 일치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="9adbf-121">튜플을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="9adbf-121">Using Tuples</span></span>
<span data-ttu-id="9adbf-122">튜플 다음 예제와 같이 함수에서 여러 값을 반환 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="9adbf-123">이 예에서는 정수 나누기를 반올림된 한 결과 튜플 쌍의 첫 번째 멤버로 작업과 쌍의 두 번째 구성원으로 나머지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="9adbf-124">튜플 사용할 수도 있습니다 함수 인수로 일반적인 함수 구문 암시 하는 함수 인수 암시적 커리 방지 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="9adbf-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="9adbf-125">함수를 정의 하는 일반적인 구문을 `let sum a b = a + b` 다음 코드에 나와 있는 것 처럼는 함수의 첫 번째 인수를 부분 적용 되는 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="9adbf-126">튜플을 매개 변수로 사용 하면 변환이 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="9adbf-127">자세한 내용은의 "인수 부분 응용 프로그램" 참조 [함수](functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="9adbf-128">튜플 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="9adbf-128">Names of Tuple Types</span></span>
<span data-ttu-id="9adbf-129">사용 하는 튜플 된 형식의 이름을 작성 하는 경우는 `*` 요소를 구분 하는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="9adbf-130">구성 된 튜플을 대 한는 `int`, `float`, 및 `string`와 같은 `(10, 10.0, "ten")`, 종류는 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="9adbf-131">C# 튜플와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="9adbf-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="9adbf-132">C# 7.0 언어 튜플을 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="9adbf-133">C#의 튜플 struct 이며 구조체 튜플을 F #에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="9adbf-134">C#과 상호 운용 해야 하는 경우 구조체 튜플을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="9adbf-135">작업을 수행 하는 것과 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-135">This is easy to do.</span></span>  <span data-ttu-id="9adbf-136">예를 들어 C# 클래스에 튜플을 전달 튜플이 수도 있는 결과 사용할를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="9adbf-137">F # 코드에서 구조체 튜플 매개 변수로 전달 하 고 결과 구조체 튜플로 서 사용한 다음 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="9adbf-138">참조 한 구조체 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="9adbf-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="9adbf-139">참조 한 구조체 완전히 다른 기본 표시를 가지기 때문에 암시적으로 변환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="9adbf-140">즉, 다음과 같은 코드 컴파일이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="9adbf-141">패턴 해야 하나 튜플에서 일치 하 고 생성할와 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="9adbf-142">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9adbf-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="9adbf-143">컴파일된 참조 튜플 형식</span><span class="sxs-lookup"><span data-stu-id="9adbf-143">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="9adbf-144">이 섹션 컴파일되는 하는 경우 튜플 형식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="9adbf-145">이 정보는.NET Framework 3.5를 대상으로 하지 않는 한 읽을 필요가 또는 더 낮은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="9adbf-146">튜플 중 모든 명명 된 여러 제네릭 형식에 하나의 개체로 컴파일됩니다 `System.Tuple`, 인자, 또는 형식 매개 변수 수에는 오버 로드입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="9adbf-147">튜플 유형이 F # 구문을 인식 하지 않으므로 도구를 사용 하는 경우 또는 C# 또는 Visual Basic 등의 다른 언어에서 볼 때이 폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="9adbf-148">`Tuple` 형식을.NET Framework 4에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="9adbf-149">컴파일러 버전을 사용 하 여 이전 버전의.NET Framework를 대상으로 하는 경우 [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) 2.0 버전의 F # 핵심 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="9adbf-150">이 라이브러리의 형식에서 2.0, 3.0 및 3.5 버전의.NET Framework를 대상으로 하는 응용 프로그램에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="9adbf-151">형식 전달.NET Framework 2.0 및.NET Framework 4 F # 구성 요소 간의 이진 호환성을 보장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="9adbf-152">컴파일된 구조체 튜플 형식</span><span class="sxs-lookup"><span data-stu-id="9adbf-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="9adbf-153">구조체 튜플 (예를 들어 `struct (x, y)`)은 참조 튜플 근본적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="9adbf-154">로 컴파일되는 <xref:System.ValueTuple> 인자, 또는 형식 매개 변수 수에 의해 오버 로드 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="9adbf-155">에 해당 하는 [C# 7.0 튜플](../../csharp/tuples.md) 및 [Visual Basic 2017 튜플](../../visual-basic/programming-guide/language-features/data-types/tuples.md), 간에 양방향 상호 운용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9adbf-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="9adbf-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9adbf-156">See Also</span></span>
[<span data-ttu-id="9adbf-157">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="9adbf-157">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="9adbf-158">F# 형식</span><span class="sxs-lookup"><span data-stu-id="9adbf-158">F# Types</span></span>](fsharp-types.md)
