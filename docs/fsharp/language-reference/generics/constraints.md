---
title: 제약 조건(F#)
description: '제네릭 형식 또는 함수에서 형식 인수에 대 한 요구 사항을 지정 하려면 제네릭 형식 매개 변수에 적용 되는 F # 제약 조건에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562312"
---
# <a name="constraints"></a><span data-ttu-id="9132e-103">제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-103">Constraints</span></span>

<span data-ttu-id="9132e-104">제네릭에 적용할 수 있는 제약 조건을 설명 하는이 항목 형식 매개 변수는 제네릭 형식 또는 함수에서 형식 인수에 대 한 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="9132e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9132e-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="9132e-106">설명</span><span class="sxs-lookup"><span data-stu-id="9132e-106">Remarks</span></span>
<span data-ttu-id="9132e-107">제네릭 형식에 사용할 수 있는 형식을 제한 적용할 수 있는 여러 다른 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="9132e-108">다음 표에서 나열 하 고 이러한 제약 조건을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="9132e-109">제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-109">Constraint</span></span>|<span data-ttu-id="9132e-110">구문</span><span class="sxs-lookup"><span data-stu-id="9132e-110">Syntax</span></span>|<span data-ttu-id="9132e-111">설명</span><span class="sxs-lookup"><span data-stu-id="9132e-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="9132e-112">형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-112">Type Constraint</span></span>|<span data-ttu-id="9132e-113">*형식 매개 변수* :&gt; *유형*</span><span class="sxs-lookup"><span data-stu-id="9132e-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="9132e-114">제공 된 형식 또는 그 파생, 지정 된 형식에서 이거나, 형식이 인터페이스 이면 제공 된 형식이 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="9132e-115">Null 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-115">Null Constraint</span></span>|<span data-ttu-id="9132e-116">*형식 매개 변수* : null</span><span class="sxs-lookup"><span data-stu-id="9132e-116">*type-parameter* : null</span></span>|<span data-ttu-id="9132e-117">제공 된 형식에는 null 리터럴을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-117">The provided type must support the null literal.</span></span> <span data-ttu-id="9132e-118">여기에 모든.NET 개체 유형 하지만 하지 F # 목록, 튜플, 함수, 클래스, 레코드 또는 공용 구조체 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="9132e-119">명시적 멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-119">Explicit Member Constraint</span></span>|<span data-ttu-id="9132e-120">[()]*형식 매개 변수* [또는... 또는 *형식 매개 변수*)]: (* 멤버 시그너처 *)</span><span class="sxs-lookup"><span data-stu-id="9132e-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="9132e-121">지정한 서명을 가진 멤버를 제공 된 형식 인수 중 하나 이상 있어야 일반적인 용도 대 한 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="9132e-122">멤버 정의 되어야 합니다 하거나 명시적으로 명시적 멤버 제약 조건을 대 한 유효한 대상이 될 형식이 나 암시적 형식 확장의 일부가에.</span><span class="sxs-lookup"><span data-stu-id="9132e-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="9132e-123">생성자 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-123">Constructor Constraint</span></span>|<span data-ttu-id="9132e-124">*형식 매개 변수* : (new: 장치-&gt; '는)</span><span class="sxs-lookup"><span data-stu-id="9132e-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="9132e-125">제공 된 형식이 기본 생성자를 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="9132e-126">값 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-126">Value Type Constraint</span></span>|<span data-ttu-id="9132e-127">: 구조체</span><span class="sxs-lookup"><span data-stu-id="9132e-127">: struct</span></span>|<span data-ttu-id="9132e-128">제공 된 형식에는.NET 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="9132e-129">참조 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-129">Reference Type Constraint</span></span>|<span data-ttu-id="9132e-130">: 하지 구조체</span><span class="sxs-lookup"><span data-stu-id="9132e-130">: not struct</span></span>|<span data-ttu-id="9132e-131">제공 된 형식에는.NET 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="9132e-132">열거형 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="9132e-133">: 열거형&lt;*기본 형식*&gt;</span><span class="sxs-lookup"><span data-stu-id="9132e-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="9132e-134">제공 된 형식이 지정 된 기본 형식이; 지정 된 열거 형식 이어야 합니다. 일반적인 용도 대 한 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="9132e-135">대리자 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-135">Delegate Constraint</span></span>|<span data-ttu-id="9132e-136">: 위임&lt;*튜플 매개 변수 형식*, *반환 형식*&gt;</span><span class="sxs-lookup"><span data-stu-id="9132e-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="9132e-137">제공 된 형식이 지정 된 인수를 포함 하는 대리자 형식 이어야 하며 반환 값입니다. 일반적인 용도 대 한 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="9132e-138">제약 조건 비교</span><span class="sxs-lookup"><span data-stu-id="9132e-138">Comparison Constraint</span></span>|<span data-ttu-id="9132e-139">: 비교</span><span class="sxs-lookup"><span data-stu-id="9132e-139">: comparison</span></span>|<span data-ttu-id="9132e-140">제공 된 형식 비교를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="9132e-141">동등 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-141">Equality Constraint</span></span>|<span data-ttu-id="9132e-142">: 같음</span><span class="sxs-lookup"><span data-stu-id="9132e-142">: equality</span></span>|<span data-ttu-id="9132e-143">제공 된 형식 일치를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="9132e-144">관리 되지 않는 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-144">Unmanaged Constraint</span></span>|<span data-ttu-id="9132e-145">: 관리 되지 않는</span><span class="sxs-lookup"><span data-stu-id="9132e-145">: unmanaged</span></span>|<span data-ttu-id="9132e-146">제공 된 형식에는 관리 되지 않는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="9132e-147">관리 되지 않는 유형은 특정 기본 형식 (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, 또는 `decimal`), 열거형 형식 `nativeptr&lt;_&gt;`, 또는 제네릭이 아닌 구조 해당 필드는 모두 관리 되지 않는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="9132e-148">코드에서 일반적 형식 제외 제약 조건 형식 에서만 사용할 수 있는 기능을 사용 하 여 때 제약 조건을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="9132e-149">예를 들어 형식 제약 조건을 사용 하 여 클래스 유형을 지정 하는 제네릭 함수 또는 형식에 해당 클래스의 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="9132e-150">제약 조건을 지정 하는 경우에 필요 형식 매개 변수를 명시적으로 작성 한 제약 조건 없이 컴파일러에는 기능을 사용 하는 형식에 대해 런타임 시 제공 될 수도 있습니다는 모든 형식에 사용할 수 있는지 확인할 방법이 없어 있기 때문에 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="9132e-151">F # 코드에서 사용 하는 가장 일반적인 제약 조건에는 기본 클래스 또는 인터페이스를 지정 하는 형식 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="9132e-152">다른 제약 조건과 산술 연산자에 대 한 오버 로드 된 연산자를 구현 하는 데 사용 하거나 F #에서는 전체 기능이 있기 때문에 제공 되는 명시적 멤버 제약 조건 등의 특정 기능을 구현할 위해 F # 라이브러리에서 사용 하거나 공용 언어 런타임에서 지원 되는 제약 조건의 집합.</span><span class="sxs-lookup"><span data-stu-id="9132e-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="9132e-153">형식 유추 과정에서 몇 가지 제약 조건이 컴파일러에 의해 자동으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="9132e-154">예를 들어, 사용 하는 경우는 `+` 함수에 연산자를 컴파일러가 식에 사용 되는 변수 유형에 대 한 명시적 멤버 제약 조건을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="9132e-155">다음 코드에서는 몇 가지 제약 조건 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9132e-155">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="9132e-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9132e-156">See Also</span></span>
[<span data-ttu-id="9132e-157">제네릭</span><span class="sxs-lookup"><span data-stu-id="9132e-157">Generics</span></span>](index.md)

[<span data-ttu-id="9132e-158">제약 조건</span><span class="sxs-lookup"><span data-stu-id="9132e-158">Constraints</span></span>](constraints.md)
