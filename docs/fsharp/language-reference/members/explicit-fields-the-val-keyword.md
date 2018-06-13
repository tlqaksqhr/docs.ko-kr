---
title: '명시적 필드: val 키워드(F#)'
description: "F # 'val'에 대 한 자세한 내용은 키워드 형식을 초기화 하지 않고 클래스 또는 구조체 형식의 값을 저장 하는 위치를 선언 하는 데 사용 됩니다."
ms.date: 05/16/2016
ms.openlocfilehash: 2bd1aae24a5823ddcd6bb8f121d8110f4a211a6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565823"
---
# <a name="explicit-fields-the-val-keyword"></a><span data-ttu-id="3d3ae-103">명시적 필드: val 키워드</span><span class="sxs-lookup"><span data-stu-id="3d3ae-103">Explicit Fields: The val Keyword</span></span>

<span data-ttu-id="3d3ae-104">`val` 키워드는 클래스 또는 구조체 형식의 값을 초기화하지 않고 저장할 위치를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-104">The `val` keyword is used to declare a location to store a value in a class or structure type, without initializing it.</span></span> <span data-ttu-id="3d3ae-105">이런이 방식으로 선언 하는 저장소 위치 라고 *명시적 필드*합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-105">Storage locations declared in this manner are called *explicit fields*.</span></span> <span data-ttu-id="3d3ae-106">`val` 키워드는 `member` 키워드와 함께 자동으로 구현된 속성을 선언하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-106">Another use of the `val` keyword is in conjunction with the `member` keyword to declare an auto-implemented property.</span></span> <span data-ttu-id="3d3ae-107">자동 구현 속성에 대 한 자세한 내용은 참조 하십시오. [속성](properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-107">For more information on auto-implemented properties, see [Properties](properties.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="3d3ae-108">구문</span><span class="sxs-lookup"><span data-stu-id="3d3ae-108">Syntax</span></span>

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a><span data-ttu-id="3d3ae-109">설명</span><span class="sxs-lookup"><span data-stu-id="3d3ae-109">Remarks</span></span>
<span data-ttu-id="3d3ae-110">클래스 또는 구조체 형식의 필드를 정의하는 일반적인 방법은 `let` 바인딩을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-110">The usual way to define fields in a class or structure type is to use a `let` binding.</span></span> <span data-ttu-id="3d3ae-111">그러나 `let` 바인딩은 반드시 클래스 생성자의 일부로 초기화해야 한다는 문제가 있습니다. 이와 같은 초기화는 경우에 따라 불가능하거나, 필요하지 않거나, 바람직하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-111">However, `let` bindings must be initialized as part of the class constructor, which is not always possible, necessary, or desirable.</span></span> <span data-ttu-id="3d3ae-112">초기화되지 않은 필드가 필요하면 `val` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-112">You can use the `val` keyword when you want a field that is uninitialized.</span></span>

<span data-ttu-id="3d3ae-113">명시적 필드는 정적이거나 정적이지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-113">Explicit fields can be static or non-static.</span></span> <span data-ttu-id="3d3ae-114">*액세스 한정자* 수 `public`, `private`, 또는 `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-114">The *access-modifier* can be `public`, `private`, or `internal`.</span></span> <span data-ttu-id="3d3ae-115">기본적으로 명시적 필드는 public입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-115">By default, explicit fields are public.</span></span> <span data-ttu-id="3d3ae-116">클래스의 `let` 바인딩은 항상 private이며 바로 이 점에서 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-116">This differs from `let` bindings in classes, which are always private.</span></span>

<span data-ttu-id="3d3ae-117">[DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) 기본 생성자가 있는 클래스 형식의 명시적 필드에이 특성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-117">The [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attribute is required on explicit fields in class types that have a primary constructor.</span></span> <span data-ttu-id="3d3ae-118">이 특성은 필드가 0으로 초기화되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-118">This attribute specifies that the field is initialized to zero.</span></span> <span data-ttu-id="3d3ae-119">필드의 형식은 0 초기화를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-119">The type of the field must support zero-initialization.</span></span> <span data-ttu-id="3d3ae-120">0 초기화를 지원하는 형식은 다음 중 하나에 해당하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-120">A type supports zero-initialization if it is one of the following:</span></span>

- <span data-ttu-id="3d3ae-121">0 값이 있는 기본 형식</span><span class="sxs-lookup"><span data-stu-id="3d3ae-121">A primitive type that has a zero value.</span></span>

- <span data-ttu-id="3d3ae-122">null 값을 정상 값, 비정상 값 또는 값의 표현으로 지원하는 형식.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-122">A type that supports a null value, either as a normal value, as an abnormal value, or as a representation of a value.</span></span> <span data-ttu-id="3d3ae-123">여기에는 클래스, 튜플, 레코드, 함수, 인터페이스, .NET 참조 형식, `unit` 형식 및 구별된 공용 구조체 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-123">This includes classes, tuples, records, functions, interfaces, .NET reference types, the `unit` type, and discriminated union types.</span></span>

- <span data-ttu-id="3d3ae-124">.NET 값 형식</span><span class="sxs-lookup"><span data-stu-id="3d3ae-124">A .NET value type.</span></span>

- <span data-ttu-id="3d3ae-125">해당 필드가 모두 기본 0 값을 지원하는 구조체</span><span class="sxs-lookup"><span data-stu-id="3d3ae-125">A structure whose fields all support a default zero value.</span></span>


<span data-ttu-id="3d3ae-126">예를 들어 변경 불가능한 `someField` 필드에는 이름이 `someField@`인 .NET 컴파일 표현의 지원 필드가 있으므로 `someField` 속성을 사용하여 저장된 값에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-126">For example, an immutable field called `someField` has a backing field in the .NET compiled representation with the name `someField@`, and you access the stored value using a property named `someField`.</span></span>

<span data-ttu-id="3d3ae-127">변경 가능한 필드의 경우 .NET 컴파일 표현은 .NET 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-127">For a mutable field, the .NET compiled representation is a .NET field.</span></span>


>[!WARNING] 
<span data-ttu-id="3d3ae-128">`Note` .NET Framework 네임 스페이스 `System.ComponentModel` 동일한 이름이 있는 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-128">`Note` The .NET Framework namespace `System.ComponentModel` contains an attribute that has the same name.</span></span> <span data-ttu-id="3d3ae-129">이 특성에 대한 자세한 내용은 `System.ComponentModel.DefaultValueAttribute`를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-129">For information about this attribute, see `System.ComponentModel.DefaultValueAttribute`.</span></span>


<span data-ttu-id="3d3ae-130">다음 코드에서는 기본 생성자가 있는 클래스에 명시적 필드를 사용하는 방법을 보여 주고 이와 비교하기 위해 `let` 바인딩을 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-130">The following code shows the use of explicit fields and, for comparison, a `let` binding in a class that has a primary constructor.</span></span> <span data-ttu-id="3d3ae-131">`let` 바인딩된 필드 `myInt1`은 전용 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-131">Note that the `let`-bound field `myInt1` is private.</span></span> <span data-ttu-id="3d3ae-132">`let` 바인딩된 필드 `myInt1`을 멤버 메서드에서 참조하는 경우 자체 식별자 `this`가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-132">When the `let`-bound field `myInt1` is referenced from a member method, the self identifier `this` is not required.</span></span> <span data-ttu-id="3d3ae-133">그러나 명시적 필드 `myInt2`와 `myString`을 참조할 때는 자체 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-133">But when you are referencing the explicit fields `myInt2` and `myString`, the self identifier is required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

<span data-ttu-id="3d3ae-134">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-134">The output is as follows:</span></span>

```
11 12 abc
30 def
```

<span data-ttu-id="3d3ae-135">다음 코드에서는 기본 생성자가 없는 클래스에 명시적 필드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-135">The following code shows the use of explicit fields in a class that does not have a primary constructor.</span></span> <span data-ttu-id="3d3ae-136">이 경우 `DefaultValue` 특성은 필요하지 않지만 형식에 대해 정의되는 생성자에서 모든 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-136">In this case, the `DefaultValue` attribute is not required, but all the fields must be initialized in the constructors that are defined for the type.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

<span data-ttu-id="3d3ae-137">출력은 `35 22`입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-137">The output is `35 22`.</span></span>

<span data-ttu-id="3d3ae-138">다음 코드에서는 구조체에 명시적 필드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-138">The following code shows the use of explicit fields in a structure.</span></span> <span data-ttu-id="3d3ae-139">구조체는 값 형식이므로 해당 필드 값이 0으로 설정되는 기본 생성자를 자동으로 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-139">Because a structure is a value type, it automatically has a default constructor that sets the values of its fields to zero.</span></span> <span data-ttu-id="3d3ae-140">따라서 `DefaultValue` 특성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-140">Therefore, the `DefaultValue` attribute is not required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

<span data-ttu-id="3d3ae-141">출력은 `11 xyz`입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-141">The output is `11 xyz`.</span></span>

<span data-ttu-id="3d3ae-142">명시적 필드는 루틴에 사용하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-142">Explicit fields are not intended for routine use.</span></span> <span data-ttu-id="3d3ae-143">일반적으로는 가능한 경우 항상 명시적 필드 대신 클래스의 `let` 바인딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-143">In general, when possible you should use a `let` binding in a class instead of an explicit field.</span></span> <span data-ttu-id="3d3ae-144">명시적 필드는 네이티브 API에 대한 플랫폼 호출에 사용할 구조체를 정의해야 하는 경우 등과 같은 특정 상호 운용성 시나리오나 COM interop 시나리오에서 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-144">Explicit fields are useful in certain interoperability scenarios, such as when you need to define a structure that will be used in a platform invoke call to a native API, or in COM interop scenarios.</span></span> <span data-ttu-id="3d3ae-145">자세한 내용은 참조 [외부 함수](../functions/external-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-145">For more information, see [External Functions](../functions/external-functions.md).</span></span> <span data-ttu-id="3d3ae-146">명시적 필드가 필요할 수 있는 또 다른 상황으로는 기본 생성자가 없는 클래스를 만드는 F# 코드 생성기를 사용하여 작업해야 하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-146">Another situation in which an explicit field might be necessary is when you are working with an F# code generator which emits classes without a primary constructor.</span></span> <span data-ttu-id="3d3ae-147">명시적 필드는 스레드에 정적인 변수나 그와 유사한 구문에도 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-147">Explicit fields are also useful for thread-static variables or similar constructs.</span></span> <span data-ttu-id="3d3ae-148">자세한 내용은 `System.ThreadStaticAttribute`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-148">For more information, see `System.ThreadStaticAttribute`.</span></span>

<span data-ttu-id="3d3ae-149">`member val` 키워드가 형식 정의에 함께 표시되는 경우 이는 자동으로 구현된 속성의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-149">When the keywords `member val` appear together in a type definition, it is a definition of an automatically implemented property.</span></span> <span data-ttu-id="3d3ae-150">자세한 내용은 참조 [속성](properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3ae-150">For more information, see [Properties](properties.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="3d3ae-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d3ae-151">See Also</span></span>
[<span data-ttu-id="3d3ae-152">속성</span><span class="sxs-lookup"><span data-stu-id="3d3ae-152">Properties</span></span>](properties.md)

[<span data-ttu-id="3d3ae-153">멤버</span><span class="sxs-lookup"><span data-stu-id="3d3ae-153">Members</span></span>](index.md)

[<span data-ttu-id="3d3ae-154">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="3d3ae-154">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
