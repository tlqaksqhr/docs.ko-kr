---
title: "C# 대리자 - C# 언어 둘러보기"
description: "C# 대리자를 사용한 런타임에 바인딩 알아보기"
keywords: ".NET, c샵, 대리자, 람다, 런타임에 바인딩"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bb304b2e5c762a44aab931b5e8f7fe9c99805eba
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="delegates"></a><span data-ttu-id="6f695-104">대리자</span><span class="sxs-lookup"><span data-stu-id="6f695-104">Delegates</span></span>

<span data-ttu-id="6f695-105">***대리자***는 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-105">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="6f695-106">대리자는 메서드를 변수에 할당되고 매개 변수로 전달될 수 있는 엔터티로 취급할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-106">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="6f695-107">또한 대리자는 다른 언어에 나오는 함수 포인터의 개념과 비슷하지만 함수 포인터와 달리 대리자는 개체 지향적이며 형식 안전 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-107">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="6f695-108">다음 예제에서는 `Function`라는 대리자 형식을 선언하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-108">The following example declares and uses a delegate type named `Function`.</span></span>

<span data-ttu-id="6f695-109">[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]</span><span class="sxs-lookup"><span data-stu-id="6f695-109">[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]</span></span>

<span data-ttu-id="6f695-110">`Function` 대리자 형식의 인스턴스는 `double` 인수를 사용하고 `double` 값을 반환하는 메서드를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-110">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="6f695-111">`Apply` 메서드는 `double[]`의 요소에 지정된 함수를 적용하여 결과가 있는 `double[]`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-111">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="6f695-112">`Main` 메서드에서 `Apply`는 세 가지 다른 함수를 `double[]`에 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-112">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="6f695-113">대리자는 정적 메서드(예: 이전 예제의 `Square` 또는 `Math.Sin`) 또는 인스턴스 메서드(예: 이전 예제의 `m.Multiply`)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-113">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="6f695-114">인스턴스 메서드를 참조하는 대리자는 특정 개체도 참조하며, 인스턴스 메서드가 대리자를 통해 호출되는 경우 해당 개체도 이 호출에서 `this`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-114">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="6f695-115">또한 즉석에서 만들어지는 "인라인 메서드"인 익명 함수를 사용하여 대리자를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-115">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="6f695-116">익명 함수는 주변 메서드의 지역 변수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-116">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="6f695-117">따라서 위의 승수 예제는 Multiplier 클래스를 사용하지 않고 좀 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-117">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

<span data-ttu-id="6f695-118">[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]</span><span class="sxs-lookup"><span data-stu-id="6f695-118">[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]</span></span>

<span data-ttu-id="6f695-119">대리자의 흥미롭고 유용한 속성은 참조하는 메서드의 클래스를 알지 못하거나 관심을 두지 않는다는 것입니다. 참조되는 메서드가 대리자와 동일한 매개 변수 및 반환 형식을 갖는다는 것만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6f695-119">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6f695-120">[이전](enums.md)
[다음](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="6f695-120">[Previous](enums.md)
[Next](attributes.md)</span></span>

