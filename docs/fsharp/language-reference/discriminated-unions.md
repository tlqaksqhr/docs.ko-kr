---
title: Discriminated Unions(F#)
description: "F #을 사용 하는 방법을 알아봅니다 구별 된 공용 구조체입니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e2a011-c785-48c8-859f-79df7f3a0e29
ms.openlocfilehash: a374f521bcde7506bb3a9eebb627eaffcd8b94a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="discriminated-unions"></a><span data-ttu-id="58e73-104">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="58e73-104">Discriminated Unions</span></span>

<span data-ttu-id="58e73-105">구분 된 공용 구조체는 여러 명명 된 사례의 다양 한 값과 형식 중 하나일 수 있는 값에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-105">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="58e73-106">구분 된 공용 구조체는 다른 유형의 데이터는 데 유용 특별 한 경우를 포함 하 여 유효한 및 오류의 경우; 가질 수 있는 데이터 한 인스턴스에서 다른; 형식에 따라 다른 데이터 작은 개체 계층 구조에 대 한 대신으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-106">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="58e73-107">또한 재귀 구별 된 공용 구조체 트리 데이터 구조를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-107">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="58e73-108">구문</span><span class="sxs-lookup"><span data-stu-id="58e73-108">Syntax</span></span>

```fsharp
[ attributes ]
type type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a><span data-ttu-id="58e73-109">설명</span><span class="sxs-lookup"><span data-stu-id="58e73-109">Remarks</span></span>
<span data-ttu-id="58e73-110">구분 된 공용 구조체 다른 언어의 공용 구조체 형식과 유사 하지만 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-110">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="58e73-111">으로 c + +에서 공용 구조체 형식 또는 Visual Basic의 variant 형식과 함께 값에 저장 된 데이터를 수정 하지 않으면; 여러 가지 옵션 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-111">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="58e73-112">그러나 구조체와 달리 이러한 다른 언어로, 각각의 가능한 옵션은 부여는 *케이스 식별자*합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-112">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="58e73-113">케이스 식별자에 가능한 다양 한 유형의 값이 유형의 개체 수; 이름에는 값은 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-113">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="58e73-114">값이 대/소문자는 열거형 케이스와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-114">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="58e73-115">값이 더 있는 경우 각 값 단일 값에 지정된 된 형식 또는 동일한 또는 다른 형식의 여러 필드를 집계 하는 튜플이 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-115">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="58e73-116">F # 3.1의 경우, 현재 이름을, 개별 필드를 지정할 수 있지만 이름이 선택 사항 대/소문자 그대로의 다른 필드에 이름이 지정 된 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-116">As of F# 3.1, you can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="58e73-117">예를 들어 셰이프 형식의 다음 선언을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="58e73-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="58e73-118">위의 코드의 세 가지 경우 중 하나는 값을 가질 수 있는 모양 구별된 된 공용 구조체 선언: 사각형, 원, 및 프리즘 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="58e73-119">각각의 경우에는 다른 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-119">Each case has a different set of fields.</span></span> <span data-ttu-id="58e73-120">형식의 두 사례에서 두 개의 명명 된 사각형 필드 `float`, 하거나 이름 너비와 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="58e73-121">원 사례에서 한 명명 된 필드 반지름입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="58e73-122">프리즘 케이스에 세 개의 필드가 있는 (너비 및 높이)의 두 필드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="58e73-123">명명 되지 않은 필드는 익명 필드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="58e73-124">다음 예제에 따라 명명 된 형식과 익명 필드에 대 한 값을 제공 하 여 개체를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="58e73-125">이 코드에서는 명명된 된 필드를 초기화 하는를 사용 하거나 또는 선언에서 필드의 순서에 의존 하 고 차례로 각 필드에 대 한 값을 방금 제공 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="58e73-126">에 대 한 생성자 호출 `rect` 이전 코드에서 명명 된 필드는 않지만,에 대 한 생성자 호출을 사용 하 여 `circ` 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="58e73-127">순서가 지정 된 필드를 혼합할 수와 이름이 같은 필드의 구조와 같이 `prism`합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="58e73-128">`option` F # 핵심 라이브러리의 간단한 공용된 구조체로 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="58e73-129">`option` 유형을 다음과 같이 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="58e73-130">앞의 코드를 지정 하는 형식을 `Option` 이라는 두 case가 구별 된 공용 구조체 `Some` 및 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="58e73-131">`Some` 사례에서 해당 형식을 형식 매개 변수에 의해 표현 되는 하나의 익명 필드로 구성 된 연관된 된 값 `'a`합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="58e73-132">`None` 사례에서 관련된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-132">The `None` case has no associated value.</span></span> <span data-ttu-id="58e73-133">따라서는 `option` 형식은 일부 형식이 나 값이 없는 제네릭 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="58e73-134">형식 `Option` 소문자 형식 별칭을 역시 `option`, 즉 더 일반적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="58e73-135">케이스 식별자 구별 된 공용 구조체 형식에 대 한 생성자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="58e73-136">예를 들어 다음 코드는의 값을 만드는 데는 `option` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="58e73-137">일치 식 패턴에서 케이스 식별자도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="58e73-138">패턴 일치 식에서에서 식별자는 개별 사례와 관련 된 값에 대 한 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="58e73-139">예를 들어, 다음 코드에서에서 `x` 식별자와 연결 된 값이 지정 되는 `Some` 의 사례는 `option` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="58e73-140">패턴 일치 식에서 구별 된 공용 구조체 일치 항목을 지정 하려면 명명 된 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="58e73-141">이전에 선언 된 셰이프 형식 필드의 값을 추출 하려면 다음 코드와 같이 명명된 된 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="58e73-142">일반적으로 공용 구조체의 이름으로 정규화 하지 않고 케이스 식별자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="58e73-143">항상 공용 구조체의 이름으로 한정 되어야 하는 이름, 원하는 경우 적용할 수 있습니다는 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성을 공용 구조체 형식 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="58e73-144">래핑 해제 구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="58e73-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="58e73-145">F # 구별 된 공용 구조체에는 보통에 사용 도메인 모델링은 하나로 줄 바꿈 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="58e73-146">패턴 일치도 통해 기본 값을 추출 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="58e73-147">단일 사례에 대 한 일치 하는 식을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-147">You don't need to use a match expression for a single case:</span></span>
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="58e73-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="58e73-149">구조체 구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="58e73-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="58e73-150">F # 4.1 부터는 구조체로 구별 된 공용 구조체를 또한 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="58e73-151">이러한 용도로 `[<Struct>]` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of string
    | Case2 of int
    | Case3 of double
```

<span data-ttu-id="58e73-152">없기 때문에 이러한는 값 형식 및 형식을 참조 하지를 추가로 구별 된 공용 구조체 참조와 비교 하는 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="58e73-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="58e73-153">프로필은 값 형식으로 복사 하며 값 형식 의미 체계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="58e73-154">구별 된 공용 구조체에 multicase 구조체 재귀 형식 정의 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="58e73-155">Multicase 구조체 구별 된 공용 구조체에 대 한 고유한 사례 이름을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="58e73-156">구분 된 공용 구조체를 사용 하 여 개체 계층 구조 대신</span><span class="sxs-lookup"><span data-stu-id="58e73-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>
<span data-ttu-id="58e73-157">흔히 소형 개체 계층에 더 간단한 방법으로 구별된 된 공용 구조체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="58e73-158">대신 다음 구별 된 공용 구조체를 사용할 수 예를 들어 한 `Shape` 기본 클래스에 대 한 파생 형식이 원, 사각형, 등입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="58e73-159">대신 영역이 나 경계를 계산 하는 가상 메서드로 사용 되는 개체 지향 구현에서 적절 한 수식으로 분기에 패턴 일치를 사용 하 여 이러한 수량을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="58e73-160">다음 예제에서는 서로 다른 수식은 모양에 따라 영역을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="58e73-161">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="58e73-162">트리 데이터 구조에 대 한 구별 된 공용 구조체를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="58e73-162">Using Discriminated Unions for Tree Data Structures</span></span>
<span data-ttu-id="58e73-163">구분 된 공용 구조체에는 재귀 공용 구조체 자체의 경우 하나 이상의 형식에 포함 될 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="58e73-164">재귀 구별 된 공용 구조체는 프로그래밍 언어에서 식을 모델링 하는 데 사용 되는 트리 구조를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="58e73-165">다음 코드에서는 재귀 구별 된 공용 구조체는 이진 트리 데이터 구조를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="58e73-166">합집합의 두 가지 경우 구성 `Node`는 정수 값과 왼쪽 및 오른쪽 하위 트리 노드인 및 `Tip`, 트리를 종료 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="58e73-167">이전 코드에서 `resultSumTree` 10 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="58e73-168">다음 그림에 대 한 트리 구조를 보여 줍니다. `myTree`합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Mytree 트리 구조](../media/TreeStructureDiagram.png)

<span data-ttu-id="58e73-170">구별 된 공용 구조체의 트리 노드는 다른 유형의 경우 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="58e73-171">다음 코드 형식에서에서 `Expression` 숫자와 변수는 곱하기 및 지 원하는 추가 간단한 프로그래밍 언어에 있는 식의 추상 구문 트리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="58e73-172">일부 공용 구조체 케이스의 재귀를 없거나 두 숫자를 나타냅니다 (`Number`) 또는 변수 (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="58e73-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="58e73-173">다른 경우 재귀 하 고 작업을 나타냅니다 (`Add` 및 `Multiply`)는 또한 식, 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="58e73-174">`Evaluate` 함수는 일치 하는 식 구문 트리를 재귀적으로 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="58e73-175">이 코드를 실행 하면,의 가치 `result` 은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="58e73-176">공통 특성</span><span class="sxs-lookup"><span data-stu-id="58e73-176">Common Attributes</span></span>

<span data-ttu-id="58e73-177">다음 특성은 일반적으로 구분 된 공용 구조체에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e73-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* <span data-ttu-id="58e73-178">`[Struct]`(F # 4.1)</span><span class="sxs-lookup"><span data-stu-id="58e73-178">`[Struct]` (F# 4.1 and higher)</span></span>

## <a name="see-also"></a><span data-ttu-id="58e73-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58e73-179">See Also</span></span>
[<span data-ttu-id="58e73-180">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="58e73-180">F# Language Reference</span></span>](index.md)
