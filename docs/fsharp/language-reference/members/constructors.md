---
title: 생성자(F#)
description: '정의 하 고 F #에서 생성자를 사용 하 여 만들고 클래스 및 구조체 개체를 초기화 하는 방법을 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 1773c111e0398aa83951afe14979d8a4ebc4907f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564435"
---
# <a name="constructors"></a><span data-ttu-id="20089-103">생성자</span><span class="sxs-lookup"><span data-stu-id="20089-103">Constructors</span></span>

<span data-ttu-id="20089-104">이 항목에서는 정의 만들고 클래스 및 구조체 개체를 초기화 하려면 생성자를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="20089-105">클래스 개체 생성</span><span class="sxs-lookup"><span data-stu-id="20089-105">Construction of Class Objects</span></span>
<span data-ttu-id="20089-106">클래스 형식의 개체에는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-106">Objects of class types have constructors.</span></span> <span data-ttu-id="20089-107">생성자는 다음과 같은 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-107">There are two kinds of constructors.</span></span> <span data-ttu-id="20089-108">하나는 매개 변수를 가진 형식 이름 바로 뒤 괄호 안에 표시 하는 기본 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="20089-109">기타, 선택적 추가 생성자를 사용 하 여 지정 된 `new` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="20089-110">이러한 추가 생성자는 기본 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="20089-111">기본 생성자를 포함 `let` 및 `do` 바인딩 클래스 정의의 시작 부분에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="20089-112">A `let` 바인딩 선언 되지 않는 전용 필드 및 클래스의 메서드는 `do` 바인딩 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="20089-113">에 대 한 자세한 내용은 `let` 클래스 생성자에 대 한 바인딩을 참조 [ `let` 클래스에서](let-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="20089-114">에 대 한 자세한 내용은 `do` 생성자에서 바인딩을 참조 [ `do` 클래스에서](do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="20089-115">또는 관계 없이 생성자를 호출 하려면 기본 생성자 추가 생성자를 사용 하 여 개체를 만들 수는 `new` 상관 없이 선택적 식을 `new` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="20089-116">쉼표로 구분 하 여 및 괄호 안에 명명 된 인수 및 값을 사용 하 여 또는 괄호로 묶인 함께 생성자 인수, 인수를 순서 대로 나열 하 여 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="20089-117">있습니다도 속성을 설정할 수 있는 개체 개체를 생성 하는 동안 속성 이름을 사용 하 여 및 생성자 인수를 명명 된와 같은 방식으로 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="20089-118">다음 코드를 가진 생성자 및 다양 한 개체를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20089-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="20089-119">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="20089-120">구조체를 생성</span><span class="sxs-lookup"><span data-stu-id="20089-120">Construction of Structures</span></span>
<span data-ttu-id="20089-121">구조체는 클래스의 모든 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="20089-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="20089-122">따라서 기본 생성자를 지정할 수 있으며 다른 생성자를 사용 하 여 제공할 수 있습니다 `new`합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="20089-123">그러나 구조체와 클래스 간의 한 가지 중요 한 차이점 있습니다: 없는 기본 생성자가 정의 하는 경우에 구조 (즉, 하나는 인수 없이) 기본 생성자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="20089-124">기본 생성자는 모든 필드를 해당 유형, 일반적으로 0 또는 동등한 항목에 대 한 기본값을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="20089-125">구조체에 대해 정의 하는 모든 생성자는 기본 생성자와 충돌 하지 않는 하나 이상의 인수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="20089-126">또한 구조를 사용 하 여 만든 필드에 두 종종 개는 `val` 키워드입니다; 클래스는 이러한 필드를 가질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="20089-127">구조체와 클래스를 사용 하 여 정의 된 필드가 있는 클래스는 `val` 키워드 수 초기화할 수도 추가 생성자의 레코드 식을 사용 하 여 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="20089-128">자세한 내용은 참조 [명시적 필드:는 `val` 키워드](explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="20089-129">생성자의 파생 작업 실행</span><span class="sxs-lookup"><span data-stu-id="20089-129">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="20089-130">클래스에서 기본 생성자에서 코드를 실행 한 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="20089-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="20089-131">그러나 경우에 어떻게 해야 없이 추가 생성자의 코드를 실행 하는 `do` 바인딩?</span><span class="sxs-lookup"><span data-stu-id="20089-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="20089-132">이 위해 사용 하 여 `then` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="20089-133">기본 생성자의 부작용은 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="20089-134">따라서 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="20089-135">생성자의 자체 식별자</span><span class="sxs-lookup"><span data-stu-id="20089-135">Self Identifiers in Constructors</span></span>
<span data-ttu-id="20089-136">다른 멤버에 각 멤버의 정의에 있는 현재 개체에 대 한 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="20089-137">사용 하 여 클래스 정의의 첫 번째 줄에 자체 식별자를 추가할 수도 있습니다는 `as` 키워드 바로 뒤에 따라오는 생성자 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="20089-138">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20089-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="20089-139">추가 생성자에서 정의할 수도 있습니다 자체 식별자를 배치 하 여는 `as` 생성자 매개 변수 바로 뒤 절.</span><span class="sxs-lookup"><span data-stu-id="20089-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="20089-140">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20089-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="20089-141">완전히 정의 하기 전에 개체를 사용 하려고 할 때 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="20089-142">따라서 자체 식별자의 사용 하 여 경고를 표시 하 고 개체의 멤버 개체가 초기화 되기 전에 액세스 하지 않도록 하려면 추가 검사를 삽입 하도록 컴파일러에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="20089-143">자체 식별자만 사용 해야는 `do` 바인딩 후 또는 기본 생성자의 여 `then` 추가 생성자의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="20089-144">자체 식별자의 이름 수 않아도 `this`합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="20089-145">유효한 식별자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-145">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="20089-146">초기화 시 속성에 값 할당</span><span class="sxs-lookup"><span data-stu-id="20089-146">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="20089-147">폼의 할당 목록을 추가 하 여 초기화 코드에서 클래스 개체의 속성에 값을 할당할 수 `property = value` 생성자의 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="20089-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="20089-148">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="20089-149">이전 코드의 다음 버전 일반 인수, 선택적 인수 및 생성자 호출에서 속성 설정의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20089-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="20089-150">상속 된 클래스의 생성자</span><span class="sxs-lookup"><span data-stu-id="20089-150">Constructors in inherited class</span></span>
<span data-ttu-id="20089-151">생성자가 있는 기본 클래스에서 상속 시에 상속 절에서 해당 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="20089-152">자세한 내용은 참조 [생성자 및 상속](../inheritance.md#constructors-and-inheritance)합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="20089-153">정적 생성자 또는 형식 생성자</span><span class="sxs-lookup"><span data-stu-id="20089-153">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="20089-154">정적 개체를 만들기 위한 코드를 지정 하는 것 외에도 `let` 및 `do` 바인딩을 형식 수준에서 초기화를 수행 하는 형식을 처음으로 사용 하기 전에 실행 되는 클래스 형식에서 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20089-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="20089-155">자세한 내용은 참조 [ `let` 클래스에서](let-bindings-in-classes.md) 및 [ `do` 클래스에서](do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20089-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20089-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20089-156">See Also</span></span>
[<span data-ttu-id="20089-157">멤버</span><span class="sxs-lookup"><span data-stu-id="20089-157">Members</span></span>](index.md)
