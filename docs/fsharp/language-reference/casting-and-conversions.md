---
title: "캐스팅 및 변환(F#)"
description: "F # 프로그래밍 언어로 제공 하는 방법을 변환 연산자 다양 한 기본 형식 간의 산술 변환에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: f17d3919c59c5881213d28a59cea7ae184493949
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="bded2-104">캐스팅 및 변환(F#)</span><span class="sxs-lookup"><span data-stu-id="bded2-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="bded2-105">이 항목에서는 F #의 형식 변환에 대 한 지원을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="bded2-106">산술 형식</span><span class="sxs-lookup"><span data-stu-id="bded2-106">Arithmetic Types</span></span>
<span data-ttu-id="bded2-107">F #은 변환 연산자 다양 한 기본 형식 사이의 변환의 산술와 같은 정수 및 부동 소수점 형식 간의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="bded2-108">변환 연산자는 정수 계열 및 char를 얻게 하 고 선택 되지 않은 형식을 연산자는 부동 소수점 및 `enum` 변환 연산자는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="bded2-109">선택 되지 않은 형식에 정의 된 `Microsoft.FSharp.Core.Operators` checked 형식은에 정의 된 및 `Microsoft.FSharp.Core.Operators.Checked`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="bded2-110">Checked 형식은 오버플로 검사 하 고 결과 값은 대상 유형의 제한을 초과 하면 런타임 예외를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="bded2-111">이러한 연산자의 각 대상 형식의 이름으로 동일한 이름을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="bded2-112">예를 들어 다음 코드를 있는 형식을 명시적으로 주석을에서 `byte` 두 가지 의미를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="bded2-113">맨 처음 발견 되는 형식이 고 두 번째는 변환 연산자.</span><span class="sxs-lookup"><span data-stu-id="bded2-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="bded2-114">다음 표에서 F #에 정의 된 변환 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="bded2-115">연산자</span><span class="sxs-lookup"><span data-stu-id="bded2-115">Operator</span></span>|<span data-ttu-id="bded2-116">설명</span><span class="sxs-lookup"><span data-stu-id="bded2-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="bded2-117">부터 최상위에 이르는 8 비트 부호 없는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="bded2-118">부호 있는 바이트를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="bded2-119">16 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="bded2-120">16 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="bded2-121">32 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="bded2-122">32 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="bded2-123">64 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="bded2-124">64 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="bded2-125">네이티브 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="bded2-126">네이티브 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="bded2-127">64 비트 배정밀 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="bded2-128">32 비트 단 정밀도 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="bded2-129">변환할 `System.Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="bded2-130">변환할 `System.Char`, 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="bded2-131">열거 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="bded2-132">기본 제공 기본 유형 외에도 이러한 연산자를 구현 하는 형식과 함께 사용할 수 있습니다 `op_Explicit` 또는 `op_Implicit` 적절 한 시그니처가 메서드.</span><span class="sxs-lookup"><span data-stu-id="bded2-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="bded2-133">예를 들어는 `int` 변환 연산자를 정적 메서드를 제공 하는 모든 형식을 사용할 `op_Explicit` 형식을 매개 변수로 사용 하 고 반환 하는 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="bded2-134">반환 형식 그 메서드를 오버 로드할 수 없는 일반 규칙에 특별 한 예외로 이렇게 하려면에 대 한 `op_Explicit` 및 `op_Implicit`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="bded2-135">열거 형식</span><span class="sxs-lookup"><span data-stu-id="bded2-135">Enumerated Types</span></span>
<span data-ttu-id="bded2-136">`enum` 연산자의 유형을 나타내는 하나의 형식 매개 변수를 사용 하는 일반 연산자는는 `enum` 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="bded2-137">열거 형식으로 변환 하는 경우 입력의 형식을 확인 하려고 하는 유추는 `enum` 를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="bded2-138">다음 예에서 변수 `col1` 명시적으로 주석을 달지 않으면 되지만 해당 형식은 나오는 같음 테스트에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="bded2-139">따라서 컴파일러는 변환 하는 추론할 수는 `Color` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="bded2-140">형식 주석을 입력할 수 있습니다와 마찬가지로 `col2` 다음 예에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="bded2-141">다음 코드 처럼 형식 매개 변수와 대상 열거형 형식을 명시적으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="bded2-142">Note 열거형의 내부 형식이 변환 되는 형식의와 호환 되는 경우에 열거 작업을 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="bded2-143">다음 코드에서 변환이 간에 일치 하지 않아 컴파일하는 데 실패 `int32` 및 `uint32`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="bded2-144">자세한 내용은 참조 [열거형](enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="bded2-145">개체 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="bded2-145">Casting Object Types</span></span>
<span data-ttu-id="bded2-146">개체 계층에서 형식 간의 변환 개체 지향 프로그래밍 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="bded2-147">변환의 기본 유형에: (업 캐스트)을 캐스팅 하 고 (좋기는) 아래로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="bded2-148">계층 구조 위로 캐스팅은 기본 개체 참조에 대 한 파생 된 개체 참조에서 캐스팅을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="bded2-149">이러한 캐스트는 기본 클래스는 파생된 클래스의 상속 계층 구조에서 정상적으로 작동 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="bded2-150">파생 된 개체 참조에 대 한 기준 개체 참조는 계층 구조 아래로 캐스팅 개체가 실제로 올바른 대상 (파생) 형식 또는 대상 형식에서 파생 되는 형식 인스턴스의 경우에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="bded2-151">F #에서는 이러한 유형의 변환에 대 한 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="bded2-152">`:>` 연산자는 계층 구조 위로 캐스팅 및 `:?>` 연산자는 계층 구조 아래로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="bded2-153">업 캐스트</span><span class="sxs-lookup"><span data-stu-id="bded2-153">Upcasting</span></span>
<span data-ttu-id="bded2-154">대부분의 개체 지향 언어 업 캐스트는 암시적; F #에서 규칙은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="bded2-155">업 캐스트는 개체 형식에 메서드를 인수를 전달 하는 경우 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="bded2-156">그러나 모듈의 let 바인딩 함수에 대 한 업캐스팅 자동이 아니면 유연한 형식으로 매개 변수 형식을 선언 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="bded2-157">자세한 내용은 참조 [유연한 형식](flexible-Types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="bded2-158">`:>` 연산자로 수행 된 정적 캐스팅, 캐스트의 성공 컴파일 타임에 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="bded2-159">사용 하는 캐스팅이 `:>` 성공적으로 컴파일되면 유효한 캐스팅 하 고 실행 시 오류가 발생할 가능성이 없습니다 있어서 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="bded2-160">사용할 수도 있습니다는 `upcast` 이러한 변환을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="bded2-161">다음 식은 계층 구조 변환을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="bded2-162">Upcast 연산자를 사용 하면 컴파일러는 컨텍스트에서 변환 하는 형식을 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="bded2-163">컴파일러가 대상 형식을 확인할 수 없는 경우 컴파일러는 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="bded2-164">좋기</span><span class="sxs-lookup"><span data-stu-id="bded2-164">Downcasting</span></span>
<span data-ttu-id="bded2-165">`:?>` 연산자로 수행 동적 캐스팅을 캐스팅 성공 런타임에 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="bded2-166">사용 하는 캐스트는 `:?>` ; 컴파일 타임에 연산자를 선택 하지 않으면 하지만 런타임 시 지정된 된 형식으로 캐스팅 하는 시도가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="bded2-167">개체가 대상 형식과 호환 이면 캐스팅에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="bded2-168">런타임에서 발생 하는 개체가 대상 형식과 호환 되지 않으면는 `InvalidCastException`합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="bded2-169">사용할 수도 있습니다는 `downcast` 동적 형식 변환을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="bded2-170">다음 식은 프로그램 컨텍스트를 통해 유추 된 형식으로의 계층 구조 아래로 변환을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="bded2-171">에 대 한는 `upcast` 연산자를 컴파일러에서 컨텍스트를 특정 대상 형식을 유추할 수 없습니다 경우 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="bded2-172">다음 코드에서는 사용 된 `:>` 및 `:?>` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="bded2-173">코드를 보면는 `:?>` 연산자 가장 잘 알고 있는 경우 변환 성공할 지 throw 하기 때문에 사용 되는 `InvalidCastException` 경우 변환이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="bded2-174">변환이 성공할 지를 사용 하는 형식 테스트 알 수 없는 경우는 `match` 예외를 생성 하는 오버 헤드를 방지 하기 때문에 식은 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="bded2-175">때문에 제네릭 연산자 `downcast` 및 `upcast` 인수 및 반환 형식을 위의 코드에서 형식 유추를 사용 하 여 바꿀 수 있습니다,</span><span class="sxs-lookup"><span data-stu-id="bded2-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="bded2-176">을(를) 다음으로 바꾸면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-176">with</span></span>

```fsharp
base1 = upcast d1
```

<span data-ttu-id="bded2-177">이전 코드에서 형식 인수 및 반환 형식은 `Derived1` 및 `Base1`각각.</span><span class="sxs-lookup"><span data-stu-id="bded2-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="bded2-178">형식 테스트에 대 한 자세한 내용은 참조 [일치 식](match-Expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bded2-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bded2-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bded2-179">See Also</span></span>
[<span data-ttu-id="bded2-180">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="bded2-180">F# Language Reference</span></span>](index.md)
