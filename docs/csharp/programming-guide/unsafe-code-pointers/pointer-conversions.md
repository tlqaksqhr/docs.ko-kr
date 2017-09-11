---
title: "포인터 변환(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="09bfd-102">포인터 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="09bfd-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="09bfd-103">다음 표에서는 미리 정의된 암시적 포인터 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="09bfd-104">암시적 변환은 메서드 호출, 할당 문을 비롯한 대부분의 경우에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="09bfd-105">암시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="09bfd-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="09bfd-106">시작</span><span class="sxs-lookup"><span data-stu-id="09bfd-106">From</span></span>|<span data-ttu-id="09bfd-107">후</span><span class="sxs-lookup"><span data-stu-id="09bfd-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="09bfd-108">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-108">Any pointer type</span></span>|<span data-ttu-id="09bfd-109">void*</span><span class="sxs-lookup"><span data-stu-id="09bfd-109">void*</span></span>|  
|<span data-ttu-id="09bfd-110">null</span><span class="sxs-lookup"><span data-stu-id="09bfd-110">null</span></span>|<span data-ttu-id="09bfd-111">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="09bfd-112">명시적 포인터 변환은 캐스트 식을 통해 암시적 변환이 없는 변환을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="09bfd-113">다음 표에는 이러한 변환이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="09bfd-114">명시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="09bfd-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="09bfd-115">시작</span><span class="sxs-lookup"><span data-stu-id="09bfd-115">From</span></span>|<span data-ttu-id="09bfd-116">후</span><span class="sxs-lookup"><span data-stu-id="09bfd-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="09bfd-117">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-117">Any pointer type</span></span>|<span data-ttu-id="09bfd-118">다른 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-118">Any other pointer type</span></span>|  
|<span data-ttu-id="09bfd-119">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="09bfd-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="09bfd-120">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-120">Any pointer type</span></span>|  
|<span data-ttu-id="09bfd-121">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="09bfd-121">Any pointer type</span></span>|<span data-ttu-id="09bfd-122">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="09bfd-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09bfd-123">예제</span><span class="sxs-lookup"><span data-stu-id="09bfd-123">Example</span></span>  
 <span data-ttu-id="09bfd-124">다음 예제에서 `int`에 대한 포인터는 `byte`에 대한 포인터로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="09bfd-125">포인터는 변수의 최하위 주소 지정 바이트를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="09bfd-126">`int` 크기(4바이트)까지 결과를 연속적으로 증가할 경우 변수의 나머지 바이트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bfd-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="09bfd-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="09bfd-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="09bfd-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="09bfd-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09bfd-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09bfd-129">See Also</span></span>  
 <span data-ttu-id="09bfd-130">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="09bfd-131">[포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="09bfd-132">[포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="09bfd-133">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="09bfd-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="09bfd-135">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="09bfd-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="09bfd-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="09bfd-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

