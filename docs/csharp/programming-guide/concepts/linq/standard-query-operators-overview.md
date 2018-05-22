---
title: 표준 쿼리 연산자 개요(C#)
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 36bd5927e64ffacb97beac28b8e7790204e08c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="518d0-102">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-102">Standard Query Operators Overview (C#)</span></span>
<span data-ttu-id="518d0-103">*표준 쿼리 연산자*는 LINQ 패턴을 형성하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="518d0-104">이 메서드 중 대부분은 시퀀스에서 작동합니다. 여기서 시퀀스란 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 <xref:System.Linq.IQueryable%601> 인터페이스를 구현하는 형식의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="518d0-105">표준 쿼리 연산자는 필터링, 프로젝션, 집계, 정렬 등을 포함하여 쿼리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="518d0-106"><xref:System.Collections.Generic.IEnumerable%601> 형식의 개체에 대해 작동하는 연산자와 <xref:System.Linq.IQueryable%601> 형식의 개체에 대해 작동하는 연산자 등 두 가지 LINQ 표준 쿼리 연산자 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="518d0-107">각 집합을 구성하는 메서드는 각각 <xref:System.Linq.Enumerable> 및 <xref:System.Linq.Queryable> 클래스의 정적 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="518d0-108">작동하는 형식의 *확장 메서드*로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="518d0-109">즉, 정적 메서드 구문 또는 인스턴스 메서드 구문을 사용하여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="518d0-110">또한 여러 표준 쿼리 연산자 메서드는 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>을 기반으로 하는 형식이 아닌 다른 형식에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="518d0-111"><xref:System.Linq.Enumerable> 형식은 <xref:System.Collections.IEnumerable> 형식의 개체에서 작동하는 이러한 두 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="518d0-112">두 메서드 <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> 및 <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>을 사용하면 LINQ 패턴에서 매개 변수가 없는 컬렉션이나 제네릭이 아닌 컬렉션을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="518d0-113">이 작업을 위해 강력한 형식의 개체 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-113">They do this by creating a strongly-typed collection of objects.</span></span> <span data-ttu-id="518d0-114"><xref:System.Linq.Queryable> 클래스는 <xref:System.Linq.Queryable> 형식의 개체에서 작동하는 두 개의 유사한 메서드 <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> 및 <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="518d0-115">표준 쿼리 연산자는 단일 값 또는 값 시퀀스를 반환하는지에 따라 실행 타이밍이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="518d0-116">singleton 값(예: <xref:System.Linq.Enumerable.Average%2A> 및 <xref:System.Linq.Enumerable.Sum%2A>)을 반환하는 이러한 메서드는 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="518d0-117">시퀀스를 반환하는 메서드는 쿼리 실행을 지연하고 열거 가능한 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="518d0-118">메모리 내 컬렉션에 대해 작동하는 메서드, 즉 <xref:System.Collections.Generic.IEnumerable%601>을 확장하는 메서드의 경우 반환된 열거 가능한 개체는 메서드에 전달된 인수를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="518d0-119">해당 개체를 열거하는 경우 쿼리 연산자의 논리가 사용되며 쿼리 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="518d0-120">반면, <xref:System.Linq.IQueryable%601>을 확장하는 메서드는 쿼리 동작을 구현하지 않고 수행할 쿼리를 나타내는 식 트리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="518d0-121">쿼리 처리는 소스 <xref:System.Linq.IQueryable%601> 개체에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="518d0-122">한 쿼리에서 쿼리 메서드 호출을 연결하여 쿼리가 임의로 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="518d0-123">다음 코드 예제에서는 표준 쿼리 연산자를 사용하여 시퀀스에 대한 정보를 가져올 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS   
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="518d0-124">쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="518d0-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="518d0-125">자주 사용되는 표준 쿼리 연산자 중 일부에는 *쿼리* *식*의 일부로 호출할 수 있는 전용 C# 및 Visual Basic 언어 키워드 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="518d0-126">전용 키워드와 해당 구문이 있는 표준 쿼리 연산자에 대한 자세한 내용은 [표준 쿼리 연산자에 대한 쿼리 식 구문(C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="518d0-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="518d0-127">표준 쿼리 연산자 확장</span><span class="sxs-lookup"><span data-stu-id="518d0-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="518d0-128">대상 도메인 또는 기술에 적합한 도메인 특정 메서드를 만들어 표준 쿼리 연산자 집합을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="518d0-129">또한 원격 평가, 쿼리 변환, 최적화 등의 추가 서비스를 제공하는 고유한 구현으로 표준 쿼리 연산자를 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="518d0-130">예제는 <xref:System.Linq.Enumerable.AsEnumerable%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="518d0-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="518d0-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="518d0-131">Related Sections</span></span>  
 <span data-ttu-id="518d0-132">다음 링크는 기능에 따라 다양한 표준 쿼리 연산자에 대한 추가 정보를 제공하는 항목으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="518d0-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="518d0-133">데이터 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-133">Sorting Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)  
  
 [<span data-ttu-id="518d0-134">집합 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-134">Set Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/set-operations.md)  
  
 [<span data-ttu-id="518d0-135">데이터 필터링(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-135">Filtering Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/filtering-data.md)  
  
 [<span data-ttu-id="518d0-136">수량자 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-136">Quantifier Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [<span data-ttu-id="518d0-137">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-137">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
  
 [<span data-ttu-id="518d0-138">데이터 분할(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-138">Partitioning Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/partitioning-data.md)  
  
 [<span data-ttu-id="518d0-139">조인 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-139">Join Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/join-operations.md)  
  
 [<span data-ttu-id="518d0-140">데이터 그룹화(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-140">Grouping Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/grouping-data.md)  
  
 [<span data-ttu-id="518d0-141">생성 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-141">Generation Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/generation-operations.md)  
  
 [<span data-ttu-id="518d0-142">같음 연산(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-142">Equality Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/equality-operations.md)  
  
 [<span data-ttu-id="518d0-143">요소 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-143">Element Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/element-operations.md)  
  
 [<span data-ttu-id="518d0-144">데이터 형식 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-144">Converting Data Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md)  
  
 [<span data-ttu-id="518d0-145">연결 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-145">Concatenation Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [<span data-ttu-id="518d0-146">집계 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-146">Aggregation Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="518d0-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="518d0-147">See Also</span></span>  
 <xref:System.Linq.Enumerable>  
 <xref:System.Linq.Queryable>  
 [<span data-ttu-id="518d0-148">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-148">Introduction to LINQ Queries (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [<span data-ttu-id="518d0-149">표준 쿼리 연산자의 쿼리 식 구문(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-149">Query Expression Syntax for Standard Query Operators (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)  
 [<span data-ttu-id="518d0-150">실행 방식에 따라 표준 쿼리 연산자 분류(C#)</span><span class="sxs-lookup"><span data-stu-id="518d0-150">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)  
 [<span data-ttu-id="518d0-151">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="518d0-151">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
