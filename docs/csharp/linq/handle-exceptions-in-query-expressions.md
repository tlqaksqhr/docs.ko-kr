---
title: 쿼리 식의 예외 처리(C#의 LINQ)
description: C#에서 LINQ 쿼리 식의 예외를 처리하는 방법을 알아봅니다.
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 344d11129814516a5ed3dcf0eba73a5ecbb96981
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403841"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="9eb12-103">쿼리 식의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="9eb12-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="9eb12-104">쿼리 식의 컨텍스트에서 모든 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="9eb12-105">그러나 데이터 소스의 내용을 수정하거나 예외를 throw하는 것과 같은 부작용이 생길 수 있는 쿼리 식에서는 메서드를 호출하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="9eb12-106">이 예제에서는 예외 처리에 대한 일반적인 .NET 지침을 위반하지 않고 쿼리 식에서 메서드를 호출할 때 예외 발생을 방지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="9eb12-107">해당 지침에 의하면 특정 컨텍스트에서 예외가 throw된 이유를 이해할 경우 이 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="9eb12-108">자세한 내용은 [최선의 예외 구현 방법](../../standard/exceptions/best-practices-for-exceptions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9eb12-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="9eb12-109">마지막 예제에서는 쿼리 실행 중에 예외를 throw해야 할 경우 사례를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="9eb12-110">예</span><span class="sxs-lookup"><span data-stu-id="9eb12-110">Example</span></span>

<span data-ttu-id="9eb12-111">다음 예제에서는 예외 처리 코드를 쿼리 식 외부로 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="9eb12-112">이 작업은 메서드가 쿼리에 로컬인 변수에 의존하지 않는 경우에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="9eb12-113">예</span><span class="sxs-lookup"><span data-stu-id="9eb12-113">Example</span></span>

<span data-ttu-id="9eb12-114">몇몇 경우에는 쿼리 내에서 throw된 예외에 대한 가장 좋은 응답은 쿼리 실행을 즉시 중지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="9eb12-115">다음 예제에서는 쿼리 본문 내부에서 throw된 예외를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="9eb12-116">`SomeMethodThatMightThrow`가 잠재적으로 쿼리 실행을 중지해야 하는 예외를 일으킬 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="9eb12-117">`try` 블록은 쿼리 자체가 아니라 `foreach` 루프를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="9eb12-118">이는 쿼리가 실제로 실행되는 지점이 `foreach` 루프이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb12-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="9eb12-119">자세한 내용은 [LINQ 쿼리 소개](../programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9eb12-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="9eb12-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9eb12-120">See also</span></span>

[<span data-ttu-id="9eb12-121">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="9eb12-121">Language Integrated Query (LINQ)</span></span>](index.md)  
