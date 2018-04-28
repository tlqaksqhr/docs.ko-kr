---
title: 형식 확장명(F#)
description: '이전에 정의 된 개체 형식에 새 멤버를 추가할 F # 형식 확장을 사용 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 3399778799fbf0f8eee56e332135656150918a60
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="type-extensions"></a><span data-ttu-id="d3ba7-103">형식 확장명</span><span class="sxs-lookup"><span data-stu-id="d3ba7-103">Type Extensions</span></span>

<span data-ttu-id="d3ba7-104">형식 확장을 사용 하면 이전에 정의 된 개체 형식에 새 멤버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-104">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3ba7-105">구문</span><span class="sxs-lookup"><span data-stu-id="d3ba7-105">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="d3ba7-106">설명</span><span class="sxs-lookup"><span data-stu-id="d3ba7-106">Remarks</span></span>
<span data-ttu-id="d3ba7-107">두 가지 형태의 형식 확장에 약간 다른 구문 및 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-107">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="d3ba7-108">*기본 확장* 되는 확장 유형으로는 동일한 네임 스페이스 또는 모듈에, 동일한 소스 파일 및 동일한 어셈블리 (DLL 또는 실행 파일)에 표시 되는 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-108">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="d3ba7-109">*선택적 확장* 는 원래 모듈, 네임 스페이스 또는 확장 되는 형식의 어셈블리 외부에 표시 하는 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-109">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="d3ba7-110">기본 확장 유형 리플렉션을 통해 검사 되지만 선택적 확장 되지 않습니다 때 형식에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-110">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="d3ba7-111">확장 모듈 이어야 하며 확장을 포함 하는 모듈 열릴 때에 범위에는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-111">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="d3ba7-112">위 구문에서 *typename* 확장 하 고 하는 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-112">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="d3ba7-113">액세스할 수 있는 모든 형식이 확장 될 수 있습니다, 하지만 형식 이름은 실제 형식 이름, 형식 약어가 아니라 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-113">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="d3ba7-114">형식 확장에서 여러 멤버를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-114">You can define multiple members in one type extension.</span></span> <span data-ttu-id="d3ba7-115">*자체 식별자* 일반 멤버와 마찬가지로 호출 되는 개체의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-115">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="d3ba7-116">`end` 키워드는 간단한 구문에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-116">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="d3ba7-117">클래스 형식에 다른 멤버와 마찬가지로 형식 확장에 정의 된 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-117">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="d3ba7-118">다른 멤버와 마찬가지로 정적 또는 인스턴스 멤버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-118">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="d3ba7-119">이러한 메서드는 라고도 *확장 메서드*; 속성 이라고 *확장 속성*등입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-119">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="d3ba7-120">선택적 확장 멤버를 개체 인스턴스 암시적으로 매개 변수로 전달 되는 첫 번째 정적 멤버에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-120">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="d3ba7-121">그러나 큐브인 것 처럼 인스턴스 멤버나 정적 멤버는 선언 된 방식에 따라 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-121">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="d3ba7-122">암시적 확장 멤버 종류의 구성원으로 포함 되어 있으며 제한 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-122">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="d3ba7-123">확장 메서드는 가상 또는 추상 메서드 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-123">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="d3ba7-124">이름이 같은 다른 메서드를 오버 로드할 수 있지만 비 확장 메서드 호출이 모호에 우선 순위를 지정 하면 컴파일러가 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-124">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="d3ba7-125">한 형식에 대 한 여러 기본 형식 확장이 있는, 모든 멤버 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-125">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="d3ba7-126">동일한 형식으로 서로 다른 형식 확장의 멤버는 선택적 형식 확장에 대 한 이름이 동일한 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-126">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="d3ba7-127">모호성으로 인해 오류가 클라이언트 코드는 동일한 멤버 이름을 정의 하는 두 개의 서로 다른 범위를가 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-127">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="d3ba7-128">다음 예제에서는 모듈의 형식은 확장명이 내장 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-128">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="d3ba7-129">모듈 외부 클라이언트 코드에 형식 확장 형식과 모든 측면에서의 일반 멤버로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-129">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="d3ba7-130">섹션으로 형식 정의 구분 하려면 내장 형식 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-130">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="d3ba7-131">이 별도 컴파일러에서 생성 된 코드와 작성 된 코드를 유지 하거나 다른 사람에 의해 생성 되거나 다른 기능와 관련 된 코드를 그룹화 하 여 큰 형식 정의 관리에 유용한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-131">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="d3ba7-132">다음 예에서는 선택적 형식 확장 확장는 `System.Int32` 확장 메서드에 형식 `FromString` 정적 멤버를 호출 하는 `Parse`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-132">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="d3ba7-133">`testFromString` 메서드 새 멤버의 모든 인스턴스 멤버와 마찬가지로 호출 되도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-133">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="d3ba7-134">새 인스턴스 멤버의 다른 모든 메서드처럼 표시 됩니다는 `Int32` intellisense에서 하지만에 있을 때만 확장을 포함 하는 모듈 열려 있거나 기타 범위 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-134">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="d3ba7-135">제네릭 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="d3ba7-135">Generic Extension Methods</span></span>
<span data-ttu-id="d3ba7-136">F # 컴파일러 F # 3.1의 경우, 하기 전에 C#의 사용을 지원 하지 않았습니다-확장 메서드는 제네릭 형식 변수, 배열 형식, 튜플 형식 또는 "this" 매개이 변수는 F # 함수 형식과 스타일 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-136">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="d3ba7-137">F # 3.1 이러한 확장 멤버의 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-137">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="d3ba7-138">예를 들어 F # 3.1 코드에서 C#에서 다음 구문과 유사 하는 서명이 있는 확장 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-138">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="d3ba7-139">이 방법은 제네릭 형식 매개 변수가 제한 되는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-139">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="d3ba7-140">또한 이제 F # 코드에서 다음과 같은 확장 멤버를 선언 고 추가 이며 의미상 풍부한 일련의 확장 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-140">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="d3ba7-141">F #에서 일반적으로 다음 예제와 같이 확장 멤버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-141">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="d3ba7-142">그러나 제네릭 형식에 대 한 유형 변수에 하지 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-142">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="d3ba7-143">선언할 수 있습니다는 C#-이 제한을 해결 하려면 F #에서 스타일 확장 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-143">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="d3ba7-144">F #의 인라인와 함께 이러한 종류의 선언 결합 하는 경우에 확장 멤버로 일반 알고리즘을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-144">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="d3ba7-145">다음 선언을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-145">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="d3ba7-146">이 선언은 사용 하 여 다음 예제와 유사한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-146">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="d3ba7-147">이 코드에서는 단일 확장 멤버를 정의 하 여 오버 로드 하지 않고 동일한 일반 산술 코드는 두 형식의 목록을에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba7-147">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="d3ba7-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3ba7-148">See Also</span></span>
[<span data-ttu-id="d3ba7-149">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d3ba7-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d3ba7-150">멤버</span><span class="sxs-lookup"><span data-stu-id="d3ba7-150">Members</span></span>](members/index.md)
