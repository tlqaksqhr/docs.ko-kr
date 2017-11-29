---
title: "클래스의 do 바인딩(F#)"
description: "F # 'do' 개체가 생성 될 때 유형을 처음 사용할 때 작업을 수행 하는 클래스 정의에서 바인딩을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="a5e3b-104">클래스의 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="a5e3b-104">do Bindings in Classes</span></span>

<span data-ttu-id="a5e3b-105">A `do` 클래스 정의에서 바인딩 작업을 수행 개체가 생성 될 때 정적 `do` 바인딩 때 형식을 처음으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="a5e3b-106">구문</span><span class="sxs-lookup"><span data-stu-id="a5e3b-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="a5e3b-107">설명</span><span class="sxs-lookup"><span data-stu-id="a5e3b-107">Remarks</span></span>
<span data-ttu-id="a5e3b-108">A `do` 바인딩 표시와 함께 이후인 `let` 바인딩 클래스 정의의 멤버 정의 보다 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="a5e3b-109">하지만 `do` 키워드는 선택 사항에 대 한 `do` 바인딩에 대 한 선택적 아니므로 모듈 수준에서 `do` 클래스 정의에서 바인딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="a5e3b-110">지정 된 유형의 static이 아닌의 모든 개체의 생성을 위한 `do` 바인딩 및 비정적 `let` 바인딩 클래스 정의에 나타나는 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="a5e3b-111">여러 `do` 바인딩이 한 가지 형식으로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="a5e3b-112">정적이 지 않은 `let` 바인딩 및 정적이 지 않은 `do` 바인딩은 기본 생성자의 본문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="a5e3b-113">정적이 지 않은 코드 `do` 기본 생성자 매개 변수 및 값 또는 함수에 정의 된 바인딩 섹션 참조할 수는 `let` 바인딩 섹션.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="a5e3b-114">Static이 아닌 `do` 바인딩 클래스에 의해 정의 된 자체 식별자도 클래스의 멤버에 액세스할 수는 `as` 제목과 있다면 해당 멤버의 사용 되는 모든 클래스에 대 한 자체 식별자로 정규화 된 클래스에는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="a5e3b-115">때문에 `let` 멤버는 예상 대로 작동 하도록 하는 데 필요한 방식은 클래스의 private 필드를 초기화 하는 바인딩 `do` 바인딩 후 일반적으로 사항이 `let` 하도록 하는 코드에서 바인딩을 `do` 바인딩 수 있습니다 완전히 초기화 된 개체와 함께 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="a5e3b-116">코드를 초기화가 완료 되기 전에 구성원을 사용 하려고 하는 InvalidOperationException 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="a5e3b-117">정적 `do` 바인딩은 정적 멤버를 참조할 수 있습니다 또는 묶는 필드 클래스 하지만 하지 인스턴스 멤버 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="a5e3b-118">정적 `do` 바인딩은 클래스를 처음 사용 하기 전에 실행 되는 클래스에 대 한 정적 이니셜라이저의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="a5e3b-119">에 대 한 특성이 무시 됩니다. `do` 종류에서 바인딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="a5e3b-120">특성은에서 실행 되는 코드에 필요한 경우 한 `do` 바인딩 적용 해야 기본 생성자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="a5e3b-121">다음 코드에서는 클래스에 정적 `do` 바인딩 및 static이 아닌 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="a5e3b-122">개체에 두 개의 매개 변수가 있는 생성자 `a` 및 `b`, 두 개의 전용 필드에서 정의 됩니다는 `let` 클래스에 대 한 바인딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="a5e3b-123">두 가지 속성이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-123">Two properties are also defined.</span></span> <span data-ttu-id="a5e3b-124">모든 정적이 지 않은의 범위 내에 항목이 `do` 이러한 모든 값을 출력 하는 줄에서 볼 수 있듯이 바인딩 섹션.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="a5e3b-125">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="a5e3b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5e3b-126">See Also</span></span>
[<span data-ttu-id="a5e3b-127">멤버</span><span class="sxs-lookup"><span data-stu-id="a5e3b-127">Members</span></span>](index.md)

[<span data-ttu-id="a5e3b-128">클래스</span><span class="sxs-lookup"><span data-stu-id="a5e3b-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="a5e3b-129">생성자</span><span class="sxs-lookup"><span data-stu-id="a5e3b-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="a5e3b-130">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="a5e3b-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="a5e3b-131">`do`바인딩</span><span class="sxs-lookup"><span data-stu-id="a5e3b-131">`do` Bindings</span></span>](../functions/do-Bindings.md)
