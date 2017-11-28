---
title: "C# 형식 및 변수 - C# 언어 둘러보기"
description: "C#에서 형식 정의 및 변수 선언에 대한 자세한 정보"
keywords: ".NET, csharp, 형식, 참조 형식, 값 형식"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: 1f1031384520b9ed37246361da8bbc1b42addb0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="types-and-variables"></a><span data-ttu-id="6bb65-104">형식 및 변수</span><span class="sxs-lookup"><span data-stu-id="6bb65-104">Types and variables</span></span>

<span data-ttu-id="6bb65-105">C#에는 두 가지 종류의 형식, 즉 *값 형식*과 *참조 형식*이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-105">There are two kinds of types in C#: *value types* and *reference types*.</span></span> <span data-ttu-id="6bb65-106">값 형식의 변수에는 해당 데이터가 직접 포함되지만 참조 형식의 변수에는 데이터(개체라고도 함)에 대한 참조가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-106">Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects.</span></span> <span data-ttu-id="6bb65-107">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-107">With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="6bb65-108">값 형식에서는 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(`ref` 및 `out` ref 및 out 매개 변수 제외).</span><span class="sxs-lookup"><span data-stu-id="6bb65-108">With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).</span></span>

<span data-ttu-id="6bb65-109">C#의 값 형식은 *단순 형식*, *열거형 형식*, *구조체 형식* 및 *null 허용 값 형식*으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-109">C#’s value types are further divided into *simple types*, *enum types*, *struct types*, and *nullable value types*.</span></span> <span data-ttu-id="6bb65-110">C#의 참조 형식은 *클래스 형식*, *인터페이스 형식*, *배열 형식*, 및 *대리자 형식*으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-110">C#’s reference types are further divided into *class types*, *interface types*, *array types*, and *delegate types*.</span></span>

<span data-ttu-id="6bb65-111">다음은 C# 형식 시스템의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-111">The following provides an overview of C#’s type system.</span></span>

* <span data-ttu-id="6bb65-112">값 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-112">Value types</span></span>
    - <span data-ttu-id="6bb65-113">@FSHO2@단순 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-113">Simple Types</span></span>
        * <span data-ttu-id="6bb65-114">부호 있는 정수: `sbyte`, `short`, `int`,`long`</span><span class="sxs-lookup"><span data-stu-id="6bb65-114">Signed integral: `sbyte`, `short`, `int`, `long`</span></span>
        * <span data-ttu-id="6bb65-115">부호 없는 정수: `byte`, `ushort`, `uint`,`ulong`</span><span class="sxs-lookup"><span data-stu-id="6bb65-115">Unsigned integral: `byte`, `ushort`, `uint`, `ulong`</span></span>
        * <span data-ttu-id="6bb65-116">유니코드 문자: `char`</span><span class="sxs-lookup"><span data-stu-id="6bb65-116">Unicode characters: `char`</span></span>
        * <span data-ttu-id="6bb65-117">IEEE 부동 소수점: `float`, `double`</span><span class="sxs-lookup"><span data-stu-id="6bb65-117">IEEE floating point: `float`, `double`</span></span>
        * <span data-ttu-id="6bb65-118">High-Precision 10진수:`decimal`</span><span class="sxs-lookup"><span data-stu-id="6bb65-118">High-precision decimal: `decimal`</span></span>
        * <span data-ttu-id="6bb65-119">부울: `bool`</span><span class="sxs-lookup"><span data-stu-id="6bb65-119">Boolean: `bool`</span></span>
    - <span data-ttu-id="6bb65-120">열거형</span><span class="sxs-lookup"><span data-stu-id="6bb65-120">Enum types</span></span>
        * <span data-ttu-id="6bb65-121">`enum E {...}` 양식의 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-121">User-defined types of the form `enum E {...}`</span></span>
    - <span data-ttu-id="6bb65-122">구조체 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-122">Struct types</span></span>
        * <span data-ttu-id="6bb65-123">`struct S {...}` 양식의 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-123">User-defined types of the form `struct S {...}`</span></span>
    - <span data-ttu-id="6bb65-124">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-124">Nullable value types</span></span>
        * <span data-ttu-id="6bb65-125">`null` 값을 갖는 다른 모든 값 형식의 확장</span><span class="sxs-lookup"><span data-stu-id="6bb65-125">Extensions of all other value types with a `null` value</span></span>
* <span data-ttu-id="6bb65-126">참조 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-126">Reference types</span></span>
    - <span data-ttu-id="6bb65-127">클래스 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-127">Class types</span></span>
        * <span data-ttu-id="6bb65-128">다른 모든 형식의 기본 클래스: `object`</span><span class="sxs-lookup"><span data-stu-id="6bb65-128">Ultimate base class of all other types: `object`</span></span>
        * <span data-ttu-id="6bb65-129">유니코드 문자열: `string`</span><span class="sxs-lookup"><span data-stu-id="6bb65-129">Unicode strings: `string`</span></span>
        * <span data-ttu-id="6bb65-130">`class C {...}` 양식의 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-130">User-defined types of the form `class C {...}`</span></span>
    - <span data-ttu-id="6bb65-131">인터페이스 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-131">Interface types</span></span>
        * <span data-ttu-id="6bb65-132">`interface I {...}` 양식의 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-132">User-defined types of the form `interface I {...}`</span></span>
    - <span data-ttu-id="6bb65-133">배열 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-133">Array types</span></span>
        * <span data-ttu-id="6bb65-134">단일 차원 및 다차원(예: `int[]` 및`int[,]`)</span><span class="sxs-lookup"><span data-stu-id="6bb65-134">Single- and multi-dimensional, for example, `int[]` and `int[,]`</span></span>
    - <span data-ttu-id="6bb65-135">대리자 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-135">Delegate types</span></span>
        * <span data-ttu-id="6bb65-136">`delegate int D(...)` 양식의 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-136">User-defined types of the form `delegate int D(...)`</span></span>

<span data-ttu-id="6bb65-137">8가지 정수 형식은 부호 있는 형식 또는 부호 없는 형식으로 8비트, 16비트, 32비트 및 64비트 값에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-137">The eight integral types provide support for 8-bit, 16-bit, 32-bit, and 64-bit values in signed or unsigned form.</span></span>

<span data-ttu-id="6bb65-138">2가지 부동 소수점 형식 `float` 및 `double`은 각각 32비트 단정밀도 및 64비트 배정밀도 IEC-60559 형식을 사용하여 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-138">The two floating-point types, `float` and `double`, are represented using the 32-bit single-precision and 64-bit double-precision IEC-60559 formats, respectively.</span></span>

<span data-ttu-id="6bb65-139">`decimal` 형식은 재무 및 통화 계산에 적합한 128비트 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-139">The `decimal` type is a 128-bit data type suitable for financial and monetary calculations.</span></span>

<span data-ttu-id="6bb65-140">C#의 `bool` 형식은 부울 값, 즉 `true` 또는 `false`를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-140">C#’s `bool` type is used to represent Boolean values—values that are either `true` or `false`.</span></span>

<span data-ttu-id="6bb65-141">C#의 문자 및 문자열 처리에서는 유니코드 인코딩이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-141">Character and string processing in C# uses Unicode encoding.</span></span> <span data-ttu-id="6bb65-142">`char` 형식은 UTF-16 코드 단위를 나타내고, `string` 형식은 UTF-16 코드 단위 시퀀스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-142">The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.</span></span>

<span data-ttu-id="6bb65-143">이를 통해 C#의 숫자 형식이 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-143">This summarizes C#’s numeric types.</span></span>

* <span data-ttu-id="6bb65-144">부호 있는 정수</span><span class="sxs-lookup"><span data-stu-id="6bb65-144">Signed Integral</span></span>
    - <span data-ttu-id="6bb65-145">`sbyte`: 8비트(-128~127)</span><span class="sxs-lookup"><span data-stu-id="6bb65-145">`sbyte`:  8 bits, range from -128 - 127</span></span>
    - <span data-ttu-id="6bb65-146">`short`: 16비트(-32,768~32,767)</span><span class="sxs-lookup"><span data-stu-id="6bb65-146">`short`: 16 bits, range from -32,768 - 32,767</span></span>
    - <span data-ttu-id="6bb65-147">`int`: 32비트(-2,147,483,648~2,147,483,647)</span><span class="sxs-lookup"><span data-stu-id="6bb65-147">`int`  : 32 bits, range from -2,147,483,648 - 2,147,483,647</span></span>
    - <span data-ttu-id="6bb65-148">`long` : 64비트(–9,223,372,036,854,775,808~9,223,372,036,854,775,807)</span><span class="sxs-lookup"><span data-stu-id="6bb65-148">`long` : 64 bits, range from –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>
* <span data-ttu-id="6bb65-149">부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="6bb65-149">Unsigned integral</span></span>
    - <span data-ttu-id="6bb65-150">`byte`: 8비트(0~255)</span><span class="sxs-lookup"><span data-stu-id="6bb65-150">`byte`   :  8 bits, range from 0 - 255</span></span>
    - <span data-ttu-id="6bb65-151">`ushort`: 16비트(0~65,535)</span><span class="sxs-lookup"><span data-stu-id="6bb65-151">`ushort` : 16 bits, range from 0 - 65,535</span></span>
    - <span data-ttu-id="6bb65-152">`uint`: 32비트(0~4,294,967,295)</span><span class="sxs-lookup"><span data-stu-id="6bb65-152">`uint`   : 32 bits, range from 0 - 4,294,967,295</span></span>
    - <span data-ttu-id="6bb65-153">`ulong`: 64비트(0~18,446,744,073,709,551,615)</span><span class="sxs-lookup"><span data-stu-id="6bb65-153">`ulong`  : 64 bits, range from 0 - 18,446,744,073,709,551,615</span></span>
* <span data-ttu-id="6bb65-154">부동 소수점</span><span class="sxs-lookup"><span data-stu-id="6bb65-154">Floating point</span></span>
    - <span data-ttu-id="6bb65-155">`float`  : 32비트(1.5 × 10<sup>−45</sup> - 3.4 × 10<sup>38</sup>), 전체 자릿수 7자리</span><span class="sxs-lookup"><span data-stu-id="6bb65-155">`float`  : 32 bits, range from 1.5 × 10<sup>−45</sup> - 3.4 × 10<sup>38</sup>,    7-digit precision</span></span>
    - <span data-ttu-id="6bb65-156">`double` : 64비트(5.0 × 10<sup>−324</sup> - 1.7 × 10<sup>308</sup>), 전체 자릿수 15자리</span><span class="sxs-lookup"><span data-stu-id="6bb65-156">`double` : 64 bits, range from 5.0 × 10<sup>−324</sup> - 1.7 × 10<sup>308</sup>, 15-digit precision</span></span>
* <span data-ttu-id="6bb65-157">Decimal</span><span class="sxs-lookup"><span data-stu-id="6bb65-157">Decimal</span></span>
    - <span data-ttu-id="6bb65-158">`decimal` : 128비트(–7.9 × 10<sup>−28</sup> -  7.9 × 10<sup>28</sup>) 전체 자릿수 28자리 이상</span><span class="sxs-lookup"><span data-stu-id="6bb65-158">`decimal` : 128 bits, range is at least –7.9 × 10<sup>−28</sup> -  7.9 × 10<sup>28</sup>, with at least 28-digit precision</span></span>
    
<span data-ttu-id="6bb65-159">C# 프로그램에서는 *형식 선언*을 사용하여 새 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-159">C# programs use *type declarations* to create new types.</span></span> <span data-ttu-id="6bb65-160">형식 선언은 새 형식의 이름과 멤버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-160">A type declaration specifies the name and the members of the new type.</span></span> <span data-ttu-id="6bb65-161">사용자 정의가 가능한 C#의 5가지 형식 범주는 클래스 형식, 구조체 형식, 인터페이스 형식, 열거형 형식 및 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-161">Five of C#’s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.</span></span>

<span data-ttu-id="6bb65-162">`class` 형식은 데이터 멤버(필드) 및 함수 멤버(메서드, 속성 및 기타)를 포함하는 데이터 구조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-162">A `class` type defines a data structure that contains data members (fields) and function members (methods, properties, and others).</span></span> <span data-ttu-id="6bb65-163">클래스 형식은 단일 상속 및 다형성과 파생된 클래스가 기본 클래스를 확장하고 특수화할 수 있는 메커니즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-163">Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.</span></span>

<span data-ttu-id="6bb65-164">`struct` 형식은 데이터 멤버 및 함수 멤버로 구조체를 나타내는 클래스 형식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-164">A `struct` type is similar to a class type in that it represents a structure with data members and function members.</span></span> <span data-ttu-id="6bb65-165">그러나 클래스와 달리 구조체는 값 형식이며 일반적으로 힙 할당이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-165">However, unlike classes, structs are value types and do not typically require heap allocation.</span></span> <span data-ttu-id="6bb65-166">구조체 형식은 사용자 지정 상속을 지원하지 않으며 모든 구조체 형식은 `object` 형식에서 암시적으로 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-166">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.</span></span>

<span data-ttu-id="6bb65-167">`interface` 형식은 계약을 공용 함수 멤버의 명명된 집합으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-167">An `interface` type defines a contract as a named set of public function members.</span></span> <span data-ttu-id="6bb65-168">`interface`를 구현하는 `class` 또는 `struct`는 인터페이스의 함수 멤버 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-168">A `class` or `struct` that implements an `interface` must provide implementations of the interface’s function members.</span></span> <span data-ttu-id="6bb65-169">`interface`는 여러 기본 인터페이스에서 상속될 수 있으며 `class` 또는 `struct`는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-169">An `interface` may inherit from multiple base interfaces, and a `class` or `struct` may implement multiple interfaces.</span></span>

<span data-ttu-id="6bb65-170">`delegate` 형식은 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-170">A `delegate` type represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="6bb65-171">대리자는 메서드를 변수에 할당되고 매개 변수로 전달될 수 있는 엔터티로 취급할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-171">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="6bb65-172">대리자는 함수 언어에서 제공하는 함수 형식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-172">Delegates are analogous to function types provided by functional languages.</span></span> <span data-ttu-id="6bb65-173">또한 다른 언어에 나오는 함수 포인터의 개념과 비슷하지만 함수 포인터와 달리 대리자는 개체 지향적이며 형식 안전 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-173">They are also similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="6bb65-174">`class`, `struct`, `interface` 및 `delegate` 형식은 모두 제네릭을 지원하므로 다른 형식으로 매개 변수화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-174">The `class`, `struct`, `interface` and `delegate` types all support generics, whereby they can be parameterized with other types.</span></span>

<span data-ttu-id="6bb65-175">`enum` 형식은 명명된 상수가 있는 고유한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-175">An `enum` type is a distinct type with named constants.</span></span> <span data-ttu-id="6bb65-176">모든 `enum` 형식은 8가지 정수 형식 중 하나인 내부 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-176">Every `enum` type has an underlying type, which must be one of the eight integral types.</span></span> <span data-ttu-id="6bb65-177">`enum` 형식의 값 집합은 내부 형식의 값 집합과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-177">The set of values of an `enum` type is the same as the set of values of the underlying type.</span></span>

<span data-ttu-id="6bb65-178">C#은 형식의 단일 차원 및 다차원 배열을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-178">C# supports single- and multi-dimensional arrays of any type.</span></span> <span data-ttu-id="6bb65-179">위에 나열된 형식과 달리, 배열 형식은 사용하기 전에 먼저 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-179">Unlike the types listed above, array types do not have to be declared before they can be used.</span></span> <span data-ttu-id="6bb65-180">대신, 배열 형식은 형식 이름을 대괄호로 묶어 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-180">Instead, array types are constructed by following a type name with square brackets.</span></span> <span data-ttu-id="6bb65-181">예를 들어 `int[]`는`int`의 1차원 배열이고, `int[,]`는 `int`의 2차원 배열이고 `int[][]`는 `int`의 1차원 배열의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-181">For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional array of `int`.</span></span>

<span data-ttu-id="6bb65-182">Null 허용 값 형식도 사용하기 전에 먼저 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-182">Nullable value types also do not have to be declared before they can be used.</span></span> <span data-ttu-id="6bb65-183">null을 허용하지 않는 값 형식 `T`의 경우 `T?`, 추가 값 `null`을 보유할 수 있는 해당 null 허용 값 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-183">For each non-nullable value type `T` there is a corresponding nullable value type `T?`, which can hold an additional value, `null`.</span></span> <span data-ttu-id="6bb65-184">예를 들어 `int?`는 32비트 정수 또는 값 `null`을 보유할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-184">For instance, `int?` is a type that can hold any 32-bit integer or the value `null`.</span></span>

<span data-ttu-id="6bb65-185">C#의 형식 시스템은 모든 형식의 값이 `object`로 취급될 수 있도록 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-185">C#’s type system is unified such that a value of any type can be treated as an `object`.</span></span> <span data-ttu-id="6bb65-186">C#의 모든 형식은 `object` 클래스 형식에서 직접 또는 간접적으로 파생되고 `object`는 모든 형식의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-186">Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types.</span></span> <span data-ttu-id="6bb65-187">참조 형식의 값은 `object`로 인식함으로써 간단히 개체로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-187">Values of reference types are treated as objects simply by viewing the values as type `object`.</span></span> <span data-ttu-id="6bb65-188">값 형식의 값은 *boxing* 및 *unboxing 작업*을 수행하여 개체로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-188">Values of value types are treated as objects by performing *boxing* and *unboxing operations*.</span></span> <span data-ttu-id="6bb65-189">다음 예제에서 `int` 값은 `object`로 변환되었다가 다시 `int`로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-189">In the following example, an `int` value is converted to `object` and back again to `int`.</span></span>

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

<span data-ttu-id="6bb65-190">값 형식의 값이 `object` 형식으로 변환되면 "box"라고도 하는 `object` 인스턴스가 값을 보유하기 위해 할당되고 값이 해당 box에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-190">When a value of a value type is converted to type `object`, an `object` instance, also called a "box", is allocated to hold the value, and the value is copied into that box.</span></span> <span data-ttu-id="6bb65-191">반대로 `object` 참조가 값 형식으로 캐스트될 때 참조된 `object`가 올바른 값 형식의 box인지 확인한 후 확인 결과가 성공이면 box의 값이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-191">Conversely, when an `object` reference is cast to a value type, a check is made that the referenced `object` is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.</span></span>

<span data-ttu-id="6bb65-192">C# 통합 형식 시스템은 결과적으로 값 형식이 "요청 시" 개체가 될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-192">C#’s unified type system effectively means that value types can become objects "on demand."</span></span> <span data-ttu-id="6bb65-193">통합 때문에 `object` 형식을 사용하는 범용 라이브러리는 참조 형식 및 값 형식 둘 다에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-193">Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.</span></span>

<span data-ttu-id="6bb65-194">C#에는 필드, 배열 요소, 지역 변수 및 매개 변수를 포함하는 여러 종류의 *변수*가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-194">There are several kinds of *variables* in C#, including fields, array elements, local variables, and parameters.</span></span> <span data-ttu-id="6bb65-195">변수는 저장소 위치를 나타내고, 모든 변수는 아래와 같이 변수에 저장될 수 있는 값을 결정하는 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb65-195">Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown below.</span></span>

* <span data-ttu-id="6bb65-196">Null을 허용하지 않는 값 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-196">Non-nullable value type</span></span>
    - <span data-ttu-id="6bb65-197">정확한 해당 형식의 값</span><span class="sxs-lookup"><span data-stu-id="6bb65-197">A value of that exact type</span></span>
* <span data-ttu-id="6bb65-198">Null 허용 값 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-198">Nullable value type</span></span>
    - <span data-ttu-id="6bb65-199">`null` 값 또는 정확한 해당 형식의 값</span><span class="sxs-lookup"><span data-stu-id="6bb65-199">A `null` value or a value of that exact type</span></span>
* <span data-ttu-id="6bb65-200">object</span><span class="sxs-lookup"><span data-stu-id="6bb65-200">object</span></span>
    - <span data-ttu-id="6bb65-201">`null` 참조, 참조 형식의 개체에 대한 참조 또는 값 형식의 boxed 값에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6bb65-201">A `null` reference, a reference to an object of any reference type, or a reference to a boxed value of any value type</span></span>
* <span data-ttu-id="6bb65-202">클래스 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-202">Class type</span></span>
    - <span data-ttu-id="6bb65-203">`null` 참조, 해당 클래스 형식의 인스턴스에 대한 참조 또는 해당 클래스 형식에서 파생된 클래스의 인스턴스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6bb65-203">A `null` reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type</span></span>
* <span data-ttu-id="6bb65-204">인터페이스 유형</span><span class="sxs-lookup"><span data-stu-id="6bb65-204">Interface type</span></span>
    - <span data-ttu-id="6bb65-205">`null` 참조, 해당 인터페이스 형식을 구현하는 클래스 형식의 인스턴스에 대한 참조 또는 해당 인터페이스 형식을 구현하는 값 형식의 boxed 값에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6bb65-205">A `null` reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type</span></span>
* <span data-ttu-id="6bb65-206">배열 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-206">Array type</span></span>
    - <span data-ttu-id="6bb65-207">`null` 참조, 해당 배열 형식의 인스턴스에 대한 참조 또는 호환되는 배열 형식의 인스턴스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6bb65-207">A `null` reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type</span></span>
* <span data-ttu-id="6bb65-208">대리자 형식</span><span class="sxs-lookup"><span data-stu-id="6bb65-208">Delegate type</span></span>
    - <span data-ttu-id="6bb65-209">`null` 참조 또는 호환되는 대리자 형식의 인스턴스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6bb65-209">A `null` reference or a reference to an instance of a compatible delegate type</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6bb65-210">[이전](program-structure.md)
[다음](expressions.md)</span><span class="sxs-lookup"><span data-stu-id="6bb65-210">[Previous](program-structure.md)
[Next](expressions.md)</span></span>
