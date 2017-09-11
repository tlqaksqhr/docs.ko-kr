---
title: "foreach, in(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
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
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="9b1e3-102">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9b1e3-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="9b1e3-103">`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 구현하는 배열 또는 개체 컬렉션의 각 요소에 대해 포함 문의 그룹을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="9b1e3-104">`foreach` 문은 컬렉션을 반복하여 원하는 정보를 얻는 데 사용되지만, 예측할 수 없는 부작용을 방지하지 위해 소스 컬렉션에서 항목을 추가하거나 제거하는 데 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="9b1e3-105">소스 컬렉션에서 항목을 추가하거나 제거해야 하는 경우 [for](../../../csharp/language-reference/keywords/for.md) 루프를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="9b1e3-106">포함된 문은 배열이나 컬렉션의 각 요소에 대해 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="9b1e3-107">컬렉션의 모든 요소에 대해 반복이 완료되면 제어가 `foreach` 블록 다음 문으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="9b1e3-108">`foreach` 블록 내 원하는 지점에서 [break](../../../csharp/language-reference/keywords/break.md) 키워드를 사용하여 루프를 중단하거나 [continue](../../../csharp/language-reference/keywords/continue.md) 키워드를 사용하여 루프의 다음 반복을 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="9b1e3-109">또한 `foreach` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="9b1e3-110">`foreach` 키워드 및 코드 샘플에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="9b1e3-111">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="9b1e3-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="9b1e3-112">방법: foreach를 사용하여 컬렉션 클래스 액세스</span><span class="sxs-lookup"><span data-stu-id="9b1e3-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="9b1e3-113">예제</span><span class="sxs-lookup"><span data-stu-id="9b1e3-113">Example</span></span>  
 <span data-ttu-id="9b1e3-114">다음 코드에서는 세 가지 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b1e3-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="9b1e3-115">정수 배열의 내용을 표시하는 일반적인 `foreach` 루프</span><span class="sxs-lookup"><span data-stu-id="9b1e3-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="9b1e3-116">동일한 작업을 수행하는 [for](../../../csharp/language-reference/keywords/for.md) 루프</span><span class="sxs-lookup"><span data-stu-id="9b1e3-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="9b1e3-117">배열의 요소 수를 유지 관리하는 `foreach` 루프</span><span class="sxs-lookup"><span data-stu-id="9b1e3-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="9b1e3-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b1e3-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9b1e3-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9b1e3-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b1e3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b1e3-120">See Also</span></span>  
 <span data-ttu-id="9b1e3-121">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b1e3-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9b1e3-122">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b1e3-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9b1e3-123">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b1e3-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9b1e3-124">[반복 문](../../../csharp/language-reference/keywords/iteration-statements.md) </span><span class="sxs-lookup"><span data-stu-id="9b1e3-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="9b1e3-125">for</span><span class="sxs-lookup"><span data-stu-id="9b1e3-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

