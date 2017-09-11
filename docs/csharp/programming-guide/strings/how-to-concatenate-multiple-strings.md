---
title: "방법: 여러 문자열 연결(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
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
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="1d372-102">방법: 여러 문자열 연결(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1d372-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="1d372-103">*연결*은 한 문자열을 다른 문자열의 끝에 추가하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="1d372-104">`+` 연산자를 사용하여 문자열 리터럴 또는 문자열 상수를 연결하면 컴파일러가 단일 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="1d372-105">런타임 연결은 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-105">No run time concatenation occurs.</span></span> <span data-ttu-id="1d372-106">하지만 문자열 변수는 런타임에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="1d372-107">이 경우 다양한 접근 방식이 성능에 미치는 영향을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d372-108">예제</span><span class="sxs-lookup"><span data-stu-id="1d372-108">Example</span></span>  
 <span data-ttu-id="1d372-109">다음 예제에서는 소스 코드의 가독성을 향상하기 위해 긴 문자열 리터럴을 작은 문자열로 분할하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="1d372-110">분할된 문자열은 컴파일 시간에 단일 문자열로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="1d372-111">이 경우 처리되는 문자열 수가 런타임 성능에 미치는 영향은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="1d372-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d372-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d372-113">예제</span><span class="sxs-lookup"><span data-stu-id="1d372-113">Example</span></span>  
 <span data-ttu-id="1d372-114">문자열 변수를 연결하려면 `+` 또는 `+=` 연산자를 사용하거나 <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> 또는 <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="1d372-115">`+` 연산자는 사용하기 쉽고 직관적인 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="1d372-116">하나의 문에서 여러 + 연산자를 사용해도 문자열 콘텐츠는 한 번만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="1d372-117">하지만 루프에서와 같이 이 작업을 여러 번 반복할 경우 효율성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="1d372-118">예를 들어 다음 코드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="1d372-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d372-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d372-120">문자열 연결 연산에서 C# 컴파일러는 null 문자열을 빈 문자열과 같은 것으로 처리하지만 원래 null 문자열의 값을 변환하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="1d372-121">루프에서와 같이 많은 수의 문자열을 연결하는 경우가 아니라면 이 코드의 성능 저하는 그리 크지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="1d372-122">이는 <xref:System.String.Concat%2A?displayProperty=fullName> 및 <xref:System.String.Format%2A?displayProperty=fullName> 메서드에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="1d372-123">그러나 성능이 중요할 경우 항상 <xref:System.Text.StringBuilder> 클래스를 사용하여 문자열을 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="1d372-124">다음 코드는 <xref:System.Text.StringBuilder> 클래스의 <xref:System.Text.StringBuilder.Append%2A> 메서드를 사용하여 `+` 연산자의 체이닝 효과 없이 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1d372-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="1d372-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d372-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d372-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d372-126">See Also</span></span>  
 <span data-ttu-id="1d372-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="1d372-127"><xref:System.String></span></span>   
 <span data-ttu-id="1d372-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="1d372-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="1d372-129">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d372-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="1d372-130">문자열</span><span class="sxs-lookup"><span data-stu-id="1d372-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

