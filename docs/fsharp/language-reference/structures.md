---
title: "구조체(F#)"
description: "F # 구조, 종종 간단한 개체 형식에 대 한 자세한 내용은 적은 양의 데이터 적고 동작이 단순한 형식에 대 한 클래스 보다 더 효율적입니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="cbf6f-104">구조체</span><span class="sxs-lookup"><span data-stu-id="cbf6f-104">Structures</span></span>

<span data-ttu-id="cbf6f-105">A *구조* 는 적은 양의 데이터 적고 동작이 단순한 변수가 있는 형식에 대 한 클래스 보다 효율적일 수 있는 간단한 개체 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbf6f-106">구문</span><span class="sxs-lookup"><span data-stu-id="cbf6f-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="cbf6f-107">설명</span><span class="sxs-lookup"><span data-stu-id="cbf6f-107">Remarks</span></span>
<span data-ttu-id="cbf6f-108">구조체는 *값 형식이*, 스택에 직접 또는으로 사용 되는 저장 된 의미 하는 필드 또는 배열 요소, 부모에서 인라인으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="cbf6f-109">클래스나 레코드와 달리 구조체는 pass-by-value 의미 체계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="cbf6f-110">따라서 기본적으로 자주 액세스 및 복사하는 소규모 데이터 집계에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="cbf6f-111">위 구문에는 두 개의 폼이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="cbf6f-112">첫 번째는 간단한 구문은 아니지만 자주 사용됩니다. `struct` 및 `end` 키워드를 사용하는 경우 두 번째 구문에 나와 있는 `StructAttribute` 특성을 생략할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="cbf6f-113">즉, `StructAttribute`를 `Struct`로 간략하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="cbf6f-114">*형식 정의-요소* 위 구문 멤버 선언 및 정의 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="cbf6f-115">구조체는 생성자 및 변경 가능/불가능한 필드를 포함할 수 있으며 멤버 및 인터페이스 구현을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="cbf6f-116">자세한 내용은 참조 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="cbf6f-117">구조체는 상속에 참가할 수 없고, `let` 또는 `do` 바인딩을 포함할 수 없으며, 자신의 형식으로 된 필드를 재귀적으로 포함할 수 없습니다. 그러나 자신의 형식을 참조하는 참조 셀은 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="cbf6f-118">구조체는 `let` 바인딩을 허용하지 않으므로 구조체에서는 `val` 키워드를 사용하여 필드를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="cbf6f-119">`val` 키워드는 필드와 해당 형식을 정의하지만 초기화는 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="cbf6f-120">대신 `val` 선언이 null 또는 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="cbf6f-121">따라서 암시적 생성자(선언에서 구조체 이름 바로 뒤에 지정되는 매개 변수)를 포함하는 구조체에서는 `val` 선언을 `DefaultValue` 특성으로 주석 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="cbf6f-122">정의된 생성자가 있는 구조체도 0으로의 초기화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="cbf6f-123">그러므로 `DefaultValue` 특성은 이러한 0 값이 필드에 유효함을 나타내는 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="cbf6f-124">구조체의 암시적 생성자는 아무런 작업도 수행하지 않습니다. 해당 형식에 대해서는 `let` 및 `do` 바인딩이 허용되지 않지만 전달되는 암시적 생성자 매개 변수 값은 개인 필드로 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="cbf6f-125">명시적 생성자에서는 필드 값이 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="cbf6f-126">명시적 생성자를 포함하는 구조체는 0으로의 초기화도 지원합니다. 그러나 `DefaultValue` 선언에서 `val` 특성을 사용하는 경우 명시적 생성자와 충돌하므로 해당 특성은 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="cbf6f-127">에 대 한 자세한 내용은 `val` 선언 참조 [명시적 필드:는 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="cbf6f-128">특성 및 액세스 가능성 한정자는 구조체에서 허용되며 다른 형식과 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="cbf6f-129">자세한 내용은 참조 [특성](attributes.md) 및 [액세스 제어](access-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="cbf6f-130">다음 코드 예제에서는 구조체 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="cbf6f-131">구조체 레코드 및 구분 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="cbf6f-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="cbf6f-132">표현할 수 있는 F # 4.1 부터는 [레코드](records.md) 및 [구별 된 공용 구조체](discriminated-unions.md) 와 구조체로 `[<Struct>]` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="cbf6f-133">자세한 내용을 보려면 각 문서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cbf6f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbf6f-134">See Also</span></span>
[<span data-ttu-id="cbf6f-135">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="cbf6f-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="cbf6f-136">클래스</span><span class="sxs-lookup"><span data-stu-id="cbf6f-136">Classes</span></span>](classes.md)

[<span data-ttu-id="cbf6f-137">레코드</span><span class="sxs-lookup"><span data-stu-id="cbf6f-137">Records</span></span>](records.md)

[<span data-ttu-id="cbf6f-138">멤버</span><span class="sxs-lookup"><span data-stu-id="cbf6f-138">Members</span></span>](members/index.md)
