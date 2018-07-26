---
title: 쿼리 결과를 메모리에 저장
description: 결과 저장 방법
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 52d502a841c428bd90a26c803ba577e76c17197c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404303"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="67349-103">쿼리 결과를 메모리에 저장</span><span class="sxs-lookup"><span data-stu-id="67349-103">Store the results of a query in memory</span></span>

<span data-ttu-id="67349-104">쿼리는 기본적으로 데이터를 검색하고 구성하는 방법에 대한 명령 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="67349-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="67349-105">쿼리는 결과의 각 후속 항목이 요청될 때 지연 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67349-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="67349-106">`foreach`를 사용하여 결과를 반복하는 경우 항목이 액세스될 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="67349-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="67349-107">쿼리를 평가한 후 `foreach` 루프를 실행하지 않고 결과를 저장하려면 쿼리 변수에 대해 다음 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="67349-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="67349-108">쿼리 결과를 저장하는 경우 다음 예제와 같이 반환된 컬렉션 개체를 새 변수에 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67349-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="67349-109">예</span><span class="sxs-lookup"><span data-stu-id="67349-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="67349-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67349-110">See also</span></span>

[<span data-ttu-id="67349-111">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="67349-111">Language Integrated Query (LINQ)</span></span>](index.md)