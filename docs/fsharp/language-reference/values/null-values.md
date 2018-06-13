---
title: Null 값(F#)
description: 'F # 프로그래밍 언어에서 null 값이 사용 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 7367b35cb6e910f926179e52992d5533e5cdda0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563911"
---
# <a name="null-values"></a><span data-ttu-id="79d45-103">Null 값</span><span class="sxs-lookup"><span data-stu-id="79d45-103">Null Values</span></span>

<span data-ttu-id="79d45-104">이 항목에서는 F #에서 null 값이 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-104">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="79d45-105">Null 값</span><span class="sxs-lookup"><span data-stu-id="79d45-105">Null Value</span></span>
<span data-ttu-id="79d45-106">Null 값은 사용 되지 않습니다 일반적으로 F #에서 값 또는 변수.</span><span class="sxs-lookup"><span data-stu-id="79d45-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="79d45-107">그러나 특정 상황에서 비정상적인 값으로 null이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="79d45-108">F #에 형식이 정의 되어, null은 허용 되지 않습니다 일반 값으로 하지 않는 한는 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) 특성 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="79d45-109">일부 다른.NET 언어에는 형식이 정의 되어, null은 가능한 값을 및 이러한 유형과 상호 운용, 하는 경우 F # 코드에서는 null 값이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="79d45-110">형식의 정의 F # 및 F #에서 엄격 하 게 사용, 사용 하는 유일한 방법은 직접 F # 라이브러리를 사용 하 여 null 값을 만들 수는 [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) 또는 [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="79d45-111">그러나 다른.NET 언어에서 사용 되는 F # 형식에 대 한 또는 F #으로.NET Framework 같은 기록 되지 않습니다는 API를 통해 해당 형식을 사용 하는 경우에 null 값 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="79d45-112">사용할 수는 `option` F # 가능한 값이 다른.NET 언어에서 null 인 참조 변수를 사용할 수 있는 경우의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="79d45-113">F # null 대신 `option` 형식 옵션 값을 사용 하 여 `None` 개체가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="79d45-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="79d45-114">옵션 값을 사용 하 여 `Some(obj)` 개체와 `obj` 개체 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="79d45-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="79d45-115">자세한 내용은 참조 [옵션](../options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-115">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="79d45-116">`null` 키워드는 유효한 F # 언어, 키워드 및.NET Framework Api 또는 다른.NET 언어에서 작성 된 다른 Api를 사용 하 여 작업할 때 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-116">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="79d45-117">Null 값을 할 수 있는 두 가지 경우는.NET API를 호출 하 고, 인수로 null 값을 전달 하는 경우 반환 값 또는.NET 메서드 호출에서 출력 매개 변수를 해석할 때 되며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-117">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="79d45-118">.NET 메서드를 null 값을 전달 하려면 사용 하는 `null` 호출 코드에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-118">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="79d45-119">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-119">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="79d45-120">.NET 메서드에서 가져온 null 값을 해석, 가능 하면 패턴 일치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-120">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="79d45-121">다음 코드 예제에서는에서 반환 되는 null 값을 해석 하려면 패턴 일치를 사용 하는 방법을 보여 줍니다. `ReadLine` 입력 스트림의 끝을 지나서 읽으려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-121">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="79d45-122">F # 형식에 대 한 null 값 사용 하는 경우와 같은 다른 방법으로 생성할 수도 있습니다 `Array.zeroCreate`, 되는 호출 `Unchecked.defaultof`합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-122">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="79d45-123">캡슐화 된 null 값을 유지 하려면이 코드로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-123">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="79d45-124">만 위한 F # 라이브러리에서는 모든 함수에 null 값을 검사할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-124">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="79d45-125">다른.NET 언어와의 상호 운용성에 대 한 라이브러리를 작성 하는 경우 null에 대 한 검사 입력 매개 변수 및 throw를 추가 해야 할 수 있습니다 있습니다는 `ArgumentNullException`것 처럼 C# 또는 Visual Basic 코드에서 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-125">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="79d45-126">임의의 값이 null 인지 확인 하려면 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79d45-126">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="79d45-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79d45-127">See Also</span></span>
[<span data-ttu-id="79d45-128">값</span><span class="sxs-lookup"><span data-stu-id="79d45-128">Values</span></span>](index.md)

[<span data-ttu-id="79d45-129">일치 식</span><span class="sxs-lookup"><span data-stu-id="79d45-129">Match Expressions</span></span>](../match-expressions.md)
