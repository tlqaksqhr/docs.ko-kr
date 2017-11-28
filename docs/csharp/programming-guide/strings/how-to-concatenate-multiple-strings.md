---
title: "방법: 여러 문자열 연결(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="4efe0-102">방법: 여러 문자열 연결(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4efe0-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="4efe0-103">*연결*은 한 문자열을 다른 문자열의 끝에 추가하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="4efe0-104">`+` 연산자를 사용하여 문자열 리터럴 또는 문자열 상수를 연결하면 컴파일러가 단일 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="4efe0-105">런타임 연결은 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-105">No run time concatenation occurs.</span></span> <span data-ttu-id="4efe0-106">하지만 문자열 변수는 런타임에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="4efe0-107">이 경우 다양한 접근 방식이 성능에 미치는 영향을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4efe0-108">예제</span><span class="sxs-lookup"><span data-stu-id="4efe0-108">Example</span></span>  
 <span data-ttu-id="4efe0-109">다음 예제에서는 소스 코드의 가독성을 향상하기 위해 긴 문자열 리터럴을 작은 문자열로 분할하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="4efe0-110">분할된 문자열은 컴파일 시간에 단일 문자열로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="4efe0-111">이 경우 처리되는 문자열 수가 런타임 성능에 미치는 영향은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="4efe0-112">예제</span><span class="sxs-lookup"><span data-stu-id="4efe0-112">Example</span></span>  
 <span data-ttu-id="4efe0-113">문자열 변수를 연결하려면 `+` 또는 `+=` 연산자를 사용하거나 <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-113">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="4efe0-114">`+` 연산자는 사용하기 쉽고 직관적인 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-114">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="4efe0-115">하나의 문에서 여러 + 연산자를 사용해도 문자열 콘텐츠는 한 번만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-115">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="4efe0-116">하지만 루프에서와 같이 이 작업을 여러 번 반복할 경우 효율성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-116">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="4efe0-117">예를 들어 다음 코드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-117">For example, note the following code:</span></span>  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="4efe0-118">문자열 연결 연산에서 C# 컴파일러는 null 문자열을 빈 문자열과 같은 것으로 처리하지만 원래 null 문자열의 값을 변환하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-118">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="4efe0-119">루프에서와 같이 많은 수의 문자열을 연결하는 경우가 아니라면 이 코드의 성능 저하는 그리 크지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-119">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="4efe0-120">이는 <xref:System.String.Concat%2A?displayProperty=nameWithType> 및 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-120">The same is true for the <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType> methods.</span></span>  
  
 <span data-ttu-id="4efe0-121">그러나 성능이 중요할 경우 항상 <xref:System.Text.StringBuilder> 클래스를 사용하여 문자열을 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-121">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="4efe0-122">다음 코드는 <xref:System.Text.StringBuilder> 클래스의 <xref:System.Text.StringBuilder.Append%2A> 메서드를 사용하여 `+` 연산자의 체이닝 효과 없이 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4efe0-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4efe0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4efe0-123">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="4efe0-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4efe0-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4efe0-125">문자열</span><span class="sxs-lookup"><span data-stu-id="4efe0-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
