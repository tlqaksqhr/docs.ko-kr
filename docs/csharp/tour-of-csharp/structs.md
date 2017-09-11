---
title: "C# 구조체 - C# 언어 둘러보기"
description: "구조체라고 하는 C# 값 형식의 기본 사항에 대해 알아보기"
keywords: ".NET, C#, 구조체, 값 형식"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9d435fd87a6103d505c14219499eeea9aee045fb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="structs"></a><span data-ttu-id="460e9-104">구조체</span><span class="sxs-lookup"><span data-stu-id="460e9-104">Structs</span></span>

<span data-ttu-id="460e9-105">***구조체***는 클래스처럼 데이터 멤버 및 함수 멤버를 포함할 수 있는 데이터 구조이지만 값 형식이며 힙 할당이 필요하지 않다는 점이 클래스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="460e9-106">구조체 형식의 변수는 구조체의 데이터를 직접 저장하지만 클래스 형식의 변수는 동적으로 할당된 개체에 대한 참조를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="460e9-107">구조체 형식은 사용자 지정 상속을 지원하지 않으며 모든 구조체 형식은 <xref:System.ValueType> 형식에서 암시적으로 상속되고, 이 형식은 다시 `object`에서 암시적으로 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="460e9-108">구조체는 값 의미 체계를 갖는 작은 데이터 구조에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="460e9-109">복소수, 좌표계의 점 또는 사전의 키-값 쌍이 모두 구조체의 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="460e9-110">작은 데이터 구조에 클래스 대신 구조체를 사용하는 것은 응용 프로그램이 사용하는 메모리 할당 수에서 큰 차이를 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="460e9-111">예를 들어 다음 프로그램은 100개의 점 배열을 만들고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="460e9-112">`Point`가 클래스로 구현될 경우 배열에 대해 1개, 100개 요소에 대해 각각 1개씩 101개의 별도 개체가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

<span data-ttu-id="460e9-113">[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]</span><span class="sxs-lookup"><span data-stu-id="460e9-113">[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]</span></span>

<span data-ttu-id="460e9-114">또 다른 방법은 Point를 구조체로 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-114">An alternative is to make Point a struct.</span></span>

<span data-ttu-id="460e9-115">[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]</span><span class="sxs-lookup"><span data-stu-id="460e9-115">[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]</span></span>

<span data-ttu-id="460e9-116">이제 1개의 개체만 인스턴스화되고(배열에 대해 1개) `Point` 인스턴스는 배열에 인라인으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-116">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="460e9-117">구조체 생성자는 새 연산자로 호출되지만 메모리가 할당된다는 것을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-117">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="460e9-118">개체를 동적으로 할당하고 그에 대한 참조를 반환하는 대신, 구조체 생성자는 단순히 구조체 값 자체(일반적으로 스택의 임시 위치에 있음)를 반환하며 이 값은 필요할 때 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-118">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="460e9-119">클래스에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-119">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="460e9-120">구조체에서는 변수 각각에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-120">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="460e9-121">예를 들어 다음 코드 조각에서 생성하는 출력은 Point가 클래스인지 또는 구조체인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-121">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

<span data-ttu-id="460e9-122">[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]</span><span class="sxs-lookup"><span data-stu-id="460e9-122">[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]</span></span>

<span data-ttu-id="460e9-123">`Point`가 클래스이면 a와 b가 같은 개체를 참조하므로 20이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-123">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="460e9-124">Point가 구조체이면 `a`를 `b`에 대입할 때 값의 복사본이 만들어지고 이 복사본은 `a.x`로의 후속 대입에 의해 영향을 받지 않으므로 10이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-124">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="460e9-125">이전 예제에는 구조체의 제한 사항 중 두 가지를 집중적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-125">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="460e9-126">첫째, 일반적으로 전체 구조체를 복사하는 것이 개체 참조를 복사하는 것보다 덜 효율적이므로 대입 및 값 매개 변수 전달이 참조 형식보다 덜 경제적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-126">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="460e9-127">둘째, `ref` 및 `out` 매개 변수를 제외하고, 구조체에 대한 참조를 만들 수 없으므로 다양한 상황에서 사용하는 것이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="460e9-127">Second, except for `ref` and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="460e9-128">[이전](classes-and-objects.md)
[다음](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="460e9-128">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>

