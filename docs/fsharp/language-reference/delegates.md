---
title: "대리자(F#)"
description: "F #에서 대리자와 작업 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="b39ff-104">대리자</span><span class="sxs-lookup"><span data-stu-id="b39ff-104">Delegates</span></span>

<span data-ttu-id="b39ff-105">대리자는 개체와 함수 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-105">A delegate represents a function call as an object.</span></span> <span data-ttu-id="b39ff-106">F #에서 일반적으로 값을 사용 해야 함수를 고급 값으로; 함수를 나타내는 그러나 대리자는.NET Framework에서 사용 및 있으므로 시기와 필요한 예상 대로 Api와 상호 운용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-106">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="b39ff-107">있습니다 사용할 수도 있습니다 다른.NET Framework 언어에서 사용 하기 위한 라이브러리를 작성할 때.</span><span class="sxs-lookup"><span data-stu-id="b39ff-107">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="b39ff-108">구문</span><span class="sxs-lookup"><span data-stu-id="b39ff-108">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="b39ff-109">설명</span><span class="sxs-lookup"><span data-stu-id="b39ff-109">Remarks</span></span>
<span data-ttu-id="b39ff-110">위 구문에서 `type1` 인수 형식 또는 형식 및 `type2` 반환 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-110">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="b39ff-111">으로 표현 되는 인수 형식을 `type1` 자동 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-111">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="b39ff-112">튜플 형식에 이미 있는 인수에 대 한 괄호로 묶인 튜플 및 튜플 형식을 사용 하 여 대상 함수의 인수 변환 되는 경우이 형식에 대 한는 원인 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-112">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="b39ff-113">자동 커리 대상 메서드를 일치 하는 튜플 인수가 괄호를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-113">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="b39ff-114">각 경우에 사용 해야 하는 구문에 대 한 코드 예제를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b39ff-114">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="b39ff-115">대리자는 F # 값, 및 정적 첨부할 수 또는 인스턴스 메서드.</span><span class="sxs-lookup"><span data-stu-id="b39ff-115">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="b39ff-116">F # 값 대리 생성자에 인수로 직접 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-116">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="b39ff-117">정적 메서드에 대 한 클래스 및 메서드 이름을 사용 하 여 대리자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-117">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="b39ff-118">인스턴스 메서드를 개체 인스턴스와 메서드 하나의 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-118">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="b39ff-119">두 경우 모두, 멤버 액세스 연산자 (`.`) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-119">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="b39ff-120">`Invoke` 대리자 형식의 메서드는 캡슐화 된 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-120">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="b39ff-121">또한 대리자는 괄호 없이 Invoke 메서드 이름을 참조 하 여 함수 값으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-121">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="b39ff-122">다음 코드는 클래스의 다양 한 메서드를 나타내는 대리자를 만드는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-122">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="b39ff-123">메서드는 정적 메서드 또는 인스턴스 메서드를 인지 및 인수에 튜플 형식 또는 변환된 형식 있는지에 따라 선언 하 고 대리자를 할당 하는 구문은 약간 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-123">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="b39ff-124">다음 코드에서는 작업할 수 있는 대리자 다양 한 방법으로 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-124">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="b39ff-125">이전 코드 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b39ff-125">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="b39ff-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b39ff-126">See Also</span></span>
[<span data-ttu-id="b39ff-127">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b39ff-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b39ff-128">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="b39ff-128">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="b39ff-129">이벤트</span><span class="sxs-lookup"><span data-stu-id="b39ff-129">Events</span></span>](members/events.md)
