---
title: "배열을 인수로 전달(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f152173b747a171052ab99f261ed91ced9465fdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="7e4be-102">배열을 인수로 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7e4be-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="7e4be-103">배열을 메서드 매개 변수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="7e4be-104">배열은 참조 형식이므로 메서드를 통해 요소 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="7e4be-105">1차원 배열을 인수로 전달</span><span class="sxs-lookup"><span data-stu-id="7e4be-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="7e4be-106">초기화된 1차원 배열을 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="7e4be-107">예를 들어 다음 문은 인쇄 메서드에 배열을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="7e4be-108">다음 코드는 인쇄 메서드의 부분 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="7e4be-109">다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="7e4be-110">예제</span><span class="sxs-lookup"><span data-stu-id="7e4be-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7e4be-111">설명</span><span class="sxs-lookup"><span data-stu-id="7e4be-111">Description</span></span>  
 <span data-ttu-id="7e4be-112">다음 예제에서는 문자열 배열이 초기화되고 문자열에 대한 `PrintArray` 메서드에 인수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="7e4be-113">메서드가 배열 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-113">The method displays the elements of the array.</span></span> <span data-ttu-id="7e4be-114">그런 다음, `ChangeArray` 및 `ChangeArrayElement` 메서드가 호출되어 배열 인수를 값으로 전송할 경우 배열 요소의 변경이 허용됨을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7e4be-115">코드</span><span class="sxs-lookup"><span data-stu-id="7e4be-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="7e4be-116">다차원 배열을 인수로 전달</span><span class="sxs-lookup"><span data-stu-id="7e4be-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="7e4be-117">초기화된 다차원 배열을 1차원 배열 전달과 동일한 방식으로 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="7e4be-118">다음 코드는 2차원 배열을 해당 인수로 허용하는 인쇄 메서드의 부분 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="7e4be-119">다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="7e4be-120">예제</span><span class="sxs-lookup"><span data-stu-id="7e4be-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7e4be-121">설명</span><span class="sxs-lookup"><span data-stu-id="7e4be-121">Description</span></span>  
 <span data-ttu-id="7e4be-122">다음 예제에서는 정수의 2차원 배열이 초기화되고 `Print2DArray` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="7e4be-123">메서드가 배열 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e4be-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7e4be-124">코드</span><span class="sxs-lookup"><span data-stu-id="7e4be-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7e4be-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e4be-125">See Also</span></span>  
 [<span data-ttu-id="7e4be-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7e4be-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7e4be-127">배열</span><span class="sxs-lookup"><span data-stu-id="7e4be-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="7e4be-128">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="7e4be-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="7e4be-129">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="7e4be-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="7e4be-130">가변 배열</span><span class="sxs-lookup"><span data-stu-id="7e4be-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
