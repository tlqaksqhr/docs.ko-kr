---
title: C# 배열 - C# 언어 둘러보기
description: 배열은 C# 언어에서 가장 기본적인 컬렉션 형식입니다.
ms.date: 08/10/2016
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: c0fe65348ab2d41852ed9150571dcb0e5b8553f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351007"
---
# <a name="arrays"></a><span data-ttu-id="3dfb7-103">배열</span><span class="sxs-lookup"><span data-stu-id="3dfb7-103">Arrays</span></span>

<span data-ttu-id="3dfb7-104">***배열***은 계산된 인덱스를 통해 액세스되는 여러 변수를 포함하는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-104">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="3dfb7-105">배열에 포함된 변수, 즉 배열의 ***요소***라고도 하는 배열은 모두 같은 형식이며, 이 형식을 배열의 ***요소 형식***이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-105">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="3dfb7-106">배열 형식은 참조 형식이고 배열 변수의 선언은 배열 인스턴스에 대한 참조를 위한 공간을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-106">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="3dfb7-107">실제 배열 인스턴스는 new 연산자를 사용하여 런타임에 동적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-107">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="3dfb7-108">새 작업은 새 배열 인스턴스의 ***길이***(인스턴스 수명 동안 고정됨)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-108">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="3dfb7-109">배열 요소의 인덱스 범위는 `0`에서 `Length - 1` 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-109">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="3dfb7-110">`new` 연산자는 배열의 요소를 모든 숫자 형식에 대해 0이고, 모든 참조 형식에 대해 `null`인 기본값으로 자동으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-110">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="3dfb7-111">다음 예제에서는 `int` 요소의 배열을 만들고, 배열을 초기화하고, 배열의 콘텐츠를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-111">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

<span data-ttu-id="3dfb7-112">이 예제에서는 ***1차원 배열***을 만들고 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-112">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="3dfb7-113">C#에서는 ***다차원 배열s***을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-113">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="3dfb7-114">배열 형식의 ***순위***라고도 하는 배열 형식의 차원 수는 배열 형식의 대괄호 사이에 사용된 쉼표 수에 1을 더한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-114">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="3dfb7-115">다음 예제에서는 1차원, 2차원 및 3차원 배열을 각각 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-115">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

<span data-ttu-id="3dfb7-116">`a1` 배열에는 10개의 요소가 들어 있고 `a2` 배열에는 50(10 × 5)개의 요소가 들어 있고 `a3` 배열에는 100(10 × 5 × 2)개 요소가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-116">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="3dfb7-117">배열의 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-117">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="3dfb7-118">배열 형식의 요소가 있는 배열을 ***가변 배열***이라고도 합니다. 요소 배열의 길이가 항상 동일할 필요는 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-118">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays do not all have to be the same.</span></span> <span data-ttu-id="3dfb7-119">다음 예제에서는 `int` 배열의 배열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-119">The following example allocates an array of arrays of `int`:</span></span>

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

<span data-ttu-id="3dfb7-120">첫 번째 줄은 형식이 `int[]`이고 초기 값이 `null`인 3개 요소가 있는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-120">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="3dfb7-121">다음 줄은 가변 길이의 개별 배열 인스턴스에 대한 참조로 3개 요소를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-121">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="3dfb7-122">new 연산자는 ***배열 이니셜라이저***를 사용하여 구분 기호 `{` 및 `}` 사이에 기록된 식 목록에 해당하는 배열 요소의 초기 값이 지정되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-122">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="3dfb7-123">다음 예제에서는 3개 요소로 `int[]`를 할당하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-123">The following example allocates and initializes an `int[]` with three elements.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

<span data-ttu-id="3dfb7-124">배열의 길이는 {와 } 사이의 식 수에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-124">Note that the length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="3dfb7-125">지역 변수 및 필드 선언은 배열 형식을 다시 시작할 필요가 없도록 좀 더 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-125">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

<span data-ttu-id="3dfb7-126">앞의 두 예제는 다음 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfb7-126">Both of the previous examples are equivalent to the following:</span></span>

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
<span data-ttu-id="3dfb7-127">[이전](structs.md)
[다음](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="3dfb7-127">[Previous](structs.md)
[Next](interfaces.md)</span></span>
