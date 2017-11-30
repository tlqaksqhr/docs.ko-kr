---
title: "foreach, in(C# 참조)"
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="db4a8-102">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="db4a8-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="db4a8-103">`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 배열 또는 개체 컬렉션의 각 요소에 대해 포함 문의 그룹을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="db4a8-104">`foreach` 문을 컬렉션을 반복하여 원하는 정보를 가져오는 데 사용되지만 예측할 수 없는 결과를 방지하지 위해 소스 컬렉션에서 항목을 추가하거나 제거하는 데 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="db4a8-105">소스 컬렉션에서 항목을 추가하거나 제거해야 하는 경우 [for](for.md) 루프를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="db4a8-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="db4a8-106">포함된 문은 배열이나 컬렉션의 각 요소에 대해 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="db4a8-107">컬렉션의 모든 요소에 대해 반복이 완료되면 제어가 `foreach` 블록 다음 문으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="db4a8-108">`foreach` 블록 내 원하는 지점에서 [break](break.md) 키워드를 사용하여 루프를 중단하거나 [continue](continue.md) 키워드를 사용하여 루프의 다음 반복을 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="db4a8-109">또한 `foreach` 루프는 [goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="db4a8-110">`foreach` 키워드 및 코드 샘플에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db4a8-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="db4a8-111">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="db4a8-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="db4a8-112">방법: foreach를 사용하여 컬렉션 클래스 액세스</span><span class="sxs-lookup"><span data-stu-id="db4a8-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="db4a8-113">예제</span><span class="sxs-lookup"><span data-stu-id="db4a8-113">Example</span></span>
 <span data-ttu-id="db4a8-114">다음 코드는 세 가지 예제를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="db4a8-115">구문을 사용 하 여 실험 및 사용 사례에 비슷한 다른 용도로 시도 하기 위해 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="db4a8-116">"코드를 실행 하려면" 실행 키를 누릅니다. 다음 편집 하며 키를 눌러 ""을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="db4a8-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="db4a8-117">정수 배열의 내용을 표시하는 일반적인 `foreach` 루프</span><span class="sxs-lookup"><span data-stu-id="db4a8-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="db4a8-118">동일한 작업을 수행하는 [for](../../../csharp/language-reference/keywords/for.md) 루프</span><span class="sxs-lookup"><span data-stu-id="db4a8-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="db4a8-119">배열의 요소 수를 유지 관리하는 `foreach` 루프</span><span class="sxs-lookup"><span data-stu-id="db4a8-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="db4a8-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="db4a8-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="db4a8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db4a8-121">See Also</span></span>  

[<span data-ttu-id="db4a8-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="db4a8-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="db4a8-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="db4a8-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="db4a8-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="db4a8-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="db4a8-125">반복 문</span><span class="sxs-lookup"><span data-stu-id="db4a8-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="db4a8-126">for</span><span class="sxs-lookup"><span data-stu-id="db4a8-126">for</span></span>](for.md)
