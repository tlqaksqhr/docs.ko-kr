---
title: "C# 열거형 - C# 언어 둘러보기"
description: "C#의 열거형, 명명된 개별 상수에 대해 자세히 알아보기"
keywords: ".NET, c샵"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 77d315dd87d9cab32605de415674d146eb9115fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="enums"></a><span data-ttu-id="c56ea-104">열거형</span><span class="sxs-lookup"><span data-stu-id="c56ea-104">Enums</span></span>

<span data-ttu-id="c56ea-105">***열거형 형식***은 명명된 상수 집합을 갖는 고유 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-105">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="c56ea-106">개별 값 집합을 가질 수 있는 형식을 정의해야 할 경우 열거형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-106">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="c56ea-107">정수 값 형식 중 하나를 기본 저장소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-107">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="c56ea-108">또한 개별 값에 대해 의미 체계 의미를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-108">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="c56ea-109">다음 예제에서는 3개의 상수 값, 즉 `Red`, `Green` 및 `Blue`를 갖는 `Color`라는 `enum` 형식을 선언하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-109">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="c56ea-110">각 `enum` 형식에는 `enum` 형식의 ***내부 형식***이라고 하는 정수 계열 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-110">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="c56ea-111">내부 형식을 명시적으로 선언하지 않는 `enum` 형식의 내부 형식은 `int`입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-111">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="c56ea-112">`enum` 형식의 저장소 형식 및 가능한 값 범위는 내부 형식에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-112">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="c56ea-113">`enum` 형식에 적용될 수 있는 값 집합은 해당 `enum` 멤버로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-113">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="c56ea-114">특히 `enum`의 모든 내부 형식 값은 `enum` 형식으로 캐스팅될 수 있으며 해당 `enum` 형식을 갖는 유효한 고유 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-114">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="c56ea-115">다음 예제에서는 `sbyte`의 내부 형식을 사용하여 `Alignment`라는 `enum` 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-115">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="c56ea-116">앞의 예제와 같이 `enum` 멤버 선언에는 멤버의 값을 지정하는 상수 식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-116">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="c56ea-117">각 `enum` 멤버의 상수 값은 `enum`의 내부 형식 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-117">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="c56ea-118">`enum` 멤버 선언이 값을 명시적으로 지정하지 않으면 멤버에는 값 0(`enum` 형식의 첫 번째 멤버인 경우) 또는 이전 `enum` 멤버 값 앞에 1을 더한 값이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-118">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="c56ea-119">형식 캐스팅을 사용하여 `Enum` 값을 정수로, 그 반대로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-119">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="c56ea-120">예:</span><span class="sxs-lookup"><span data-stu-id="c56ea-120">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="c56ea-121">`enum` 형식의 기본값은 `enum` 형식으로 변환된 정수 계열 값 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-121">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="c56ea-122">변수가 자동으로 기본값으로 초기화되는 경우 `enum` 형식의 변수에 이 값이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-122">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="c56ea-123">`enum` 형식의 기본값을 쉽게 사용하도록 하기 위해 리터럴 `0`이 `enum` 형식으로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-123">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="c56ea-124">따라서 다음이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ea-124">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
<span data-ttu-id="c56ea-125">[이전](interfaces.md)
[다음](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="c56ea-125">[Previous](interfaces.md)
[Next](delegates.md)</span></span>
