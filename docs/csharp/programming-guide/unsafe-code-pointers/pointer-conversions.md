---
title: 포인터 변환(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: e0c3a409d76468a6e214a96e8bb326a9d906fe18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322694"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="174fd-102">포인터 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="174fd-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="174fd-103">다음 표에서는 미리 정의된 암시적 포인터 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="174fd-104">암시적 변환은 메서드 호출, 할당 문을 비롯한 대부분의 경우에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="174fd-105">암시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="174fd-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="174fd-106">시작</span><span class="sxs-lookup"><span data-stu-id="174fd-106">From</span></span>|<span data-ttu-id="174fd-107">대상</span><span class="sxs-lookup"><span data-stu-id="174fd-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="174fd-108">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-108">Any pointer type</span></span>|<span data-ttu-id="174fd-109">void\*</span><span class="sxs-lookup"><span data-stu-id="174fd-109">void\*</span></span>|  
|<span data-ttu-id="174fd-110">null</span><span class="sxs-lookup"><span data-stu-id="174fd-110">null</span></span>|<span data-ttu-id="174fd-111">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="174fd-112">명시적 포인터 변환은 캐스트 식을 통해 암시적 변환이 없는 변환을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="174fd-113">다음 표에는 이러한 변환이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="174fd-114">명시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="174fd-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="174fd-115">시작</span><span class="sxs-lookup"><span data-stu-id="174fd-115">From</span></span>|<span data-ttu-id="174fd-116">대상</span><span class="sxs-lookup"><span data-stu-id="174fd-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="174fd-117">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-117">Any pointer type</span></span>|<span data-ttu-id="174fd-118">다른 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-118">Any other pointer type</span></span>|  
|<span data-ttu-id="174fd-119">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="174fd-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="174fd-120">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-120">Any pointer type</span></span>|  
|<span data-ttu-id="174fd-121">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-121">Any pointer type</span></span>|<span data-ttu-id="174fd-122">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="174fd-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="174fd-123">예</span><span class="sxs-lookup"><span data-stu-id="174fd-123">Example</span></span>  
 <span data-ttu-id="174fd-124">다음 예제에서 `int`에 대한 포인터는 `byte`에 대한 포인터로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="174fd-125">포인터는 변수의 최하위 주소 지정 바이트를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="174fd-126">`int` 크기(4바이트)까지 결과를 연속적으로 증가할 경우 변수의 나머지 바이트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="174fd-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="174fd-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="174fd-127">See Also</span></span>  
 [<span data-ttu-id="174fd-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="174fd-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="174fd-129">포인터 식</span><span class="sxs-lookup"><span data-stu-id="174fd-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="174fd-130">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="174fd-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="174fd-131">유형</span><span class="sxs-lookup"><span data-stu-id="174fd-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="174fd-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="174fd-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="174fd-133">fixed 문</span><span class="sxs-lookup"><span data-stu-id="174fd-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="174fd-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="174fd-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
