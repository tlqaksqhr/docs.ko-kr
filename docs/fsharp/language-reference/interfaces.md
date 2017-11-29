---
title: "인터페이스(F#)"
description: "F # 인터페이스에서 다른 클래스에서 구현 하는 관련된 멤버의 집합을 지정 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a082459-17d4-45cf-9153-0b7550a154ec
ms.openlocfilehash: d7c95e5f5cc0bc6c7f6393af990427ac491c5b79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="interfaces"></a><span data-ttu-id="a9fca-104">인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9fca-104">Interfaces</span></span>

<span data-ttu-id="a9fca-105">*인터페이스* 다른 클래스에서 구현 하는 관련된 멤버의 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-105">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9fca-106">구문</span><span class="sxs-lookup"><span data-stu-id="a9fca-106">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="a9fca-107">설명</span><span class="sxs-lookup"><span data-stu-id="a9fca-107">Remarks</span></span>
<span data-ttu-id="a9fca-108">인터페이스 선언 없는 멤버가 구현 된 점을 제외 하 고 클래스 선언 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-108">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="a9fca-109">대신, 모든 멤버는 키워드로 표시 된 대로 추상적 `abstract`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-109">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="a9fca-110">추상 메서드에 대 한 메서드 본문을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-110">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="a9fca-111">와 함께 방법으로 멤버의 별도 정의 포함 하 여 기본 구현을 제공할 수 있습니다는 `default` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-111">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="a9fca-112">이렇게 다른.NET 언어에서 기본 클래스의 가상 메서드를 작성 하는 것과 결과가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-112">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="a9fca-113">클래스에서 인터페이스를 구현 하는 가상 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-113">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="a9fca-114">필요에 따라 일반 F # 구문을 사용 하 여 이름을 각 메서드 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="a9fca-115">위의 `ISprintable` 예제에서는 `Print` 메서드에 형식의 단일 매개 변수는 `string` 이름의 `format`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="a9fca-116">인터페이스를 구현 하는 방법은 두 가지가: 개체 식을 사용 하 고 클래스 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="a9fca-117">두 경우 모두 클래스 형식이 나 개체 식은 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="a9fca-118">구현 된 인터페이스를 구현 하는 각 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="a9fca-119">따라서 서로 다른 형식에 대 한 인터페이스 메서드를 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="a9fca-120">키워드 `interface` 및 `end`, 시작 및 끝의 정의 표시 하는 간단한 구문을 사용 하는 경우 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="a9fca-121">이러한 키워드를 사용 하지 않으면 컴파일러는 형식이 인지는 클래스 또는 인터페이스 사용 하는 구문 분석 하 여 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="a9fca-122">멤버를 정의 하거나 다른 클래스 구문을 사용 하 여 형식은 클래스로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="a9fca-123">대문자로 모든 인터페이스를 시작 하는 코딩 스타일.NET `I`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="a9fca-124">클래스 형식을 사용 하 여 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-124">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="a9fca-125">클래스 형식에 사용 하 여 하나 이상의 인터페이스를 구현할 수는 `interface` 인터페이스의 이름, 키워드 및 `with` 키워드, 다음 코드에 표시 된 인터페이스 멤버 정의 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="a9fca-126">인터페이스 구현은 상속 되므로 모든 파생된 클래스에서는를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="a9fca-127">인터페이스 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="a9fca-127">Calling Interface Methods</span></span>
<span data-ttu-id="a9fca-128">인터페이스를 구현 하는 형식의 모든 개체를 통해서가 아니라 인터페이스를 통해서만 인터페이스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="a9fca-129">따라서 해야할 인터페이스 형식으로 업캐스팅을 사용 하 여는 `:>` 연산자 또는 `upcast` 이러한 메서드를 호출 하기 위해 연산자.</span><span class="sxs-lookup"><span data-stu-id="a9fca-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="a9fca-130">메서드를 호출 하는 인터페이스 형식의 개체가 있으면 `SomeClass`, 다음 코드에 나와 있는 것 처럼 개체를 인터페이스 형식으로 업캐스팅을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="a9fca-131">대신 해당 업캐스팅 개체에서 메서드를 선언 하는 것 하 고 다음 예제와 같이 인터페이스 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="a9fca-132">개체 식을 사용 하 여 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-132">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="a9fca-133">개체 식에는 인터페이스를 구현 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="a9fca-134">명명된 된 형식, 만들 필요가 없습니다 하 고 방금 추가 메서드 없이 인터페이스 메서드를 원하는 개체를 원하는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="a9fca-135">다음 코드는 개체 식은 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="a9fca-136">인터페이스 상속</span><span class="sxs-lookup"><span data-stu-id="a9fca-136">Interface Inheritance</span></span>
<span data-ttu-id="a9fca-137">인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fca-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a9fca-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9fca-138">See Also</span></span>
[<span data-ttu-id="a9fca-139">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="a9fca-139">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a9fca-140">개체 식</span><span class="sxs-lookup"><span data-stu-id="a9fca-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="a9fca-141">클래스</span><span class="sxs-lookup"><span data-stu-id="a9fca-141">Classes</span></span>](classes.md)
