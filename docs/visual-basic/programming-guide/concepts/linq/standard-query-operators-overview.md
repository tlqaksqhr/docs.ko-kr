---
title: "표준 쿼리 연산자 개요 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229b63db761f2a1ed5333fd6f8e4eb9b5c0b75de
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a><span data-ttu-id="009ff-102">표준 쿼리 연산자 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-102">Standard Query Operators Overview (Visual Basic)</span></span>
<span data-ttu-id="009ff-103">*표준 쿼리 연산자* 메서드를 LINQ 패턴을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="009ff-104">이러한 메서드의 대부분 시퀀스, 여기서 시퀀스는 형식이 구현 하는 개체에서 동작의 <xref:System.Collections.Generic.IEnumerable%601>인터페이스 또는 <xref:System.Linq.IQueryable%601>인터페이스.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="009ff-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="009ff-105">표준 쿼리 연산자는 필터링, 프로젝션, 집계, 정렬 등을 포함 하 여 쿼리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="009ff-106">형식 <xref:System.Collections.Generic.IEnumerable%601>및 기타 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> 유형의 개체에서 작동 하</xref:System.Collections.Generic.IEnumerable%601> 는 개체에 대해 작동 하는 LINQ 표준 쿼리 연산자의 두 집합이</span><span class="sxs-lookup"><span data-stu-id="009ff-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="009ff-107">각 집합을 구성 하는 메서드는 정적 멤버는 <xref:System.Linq.Enumerable>및 <xref:System.Linq.Queryable>클래스 각각.</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="009ff-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="009ff-108">로 정의 된 *확장 메서드* 에서 동작 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="009ff-109">즉, 정적 메서드 구문 또는 인스턴스 메서드 구문을 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="009ff-110">여러 표준 쿼리 연산자 메서드 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 기반 하는 것 이외의 형식에서 작동 하는 또한</span><span class="sxs-lookup"><span data-stu-id="009ff-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="009ff-111"><xref:System.Linq.Enumerable>이러한 두 메서드를 정의 하는 형식 <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> 유형의 개체에서 동작 하는</xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="009ff-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="009ff-112">이러한 메서드를 <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>및 <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>를 LINQ 패턴에서 쿼리할 매개 변수가 없는, 또는 제네릭이 아닌 컬렉션을 사용 하도록 설정 합니다.</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29></span><span class="sxs-lookup"><span data-stu-id="009ff-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="009ff-113">이렇게 강력한 형식의 개체 컬렉션을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-113">They do this by creating a strongly-typed collection of objects.</span></span> <span data-ttu-id="009ff-114"><xref:System.Linq.Queryable>클래스 <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>및 <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> <xref:System.Linq.Queryable>.</xref:System.Linq.Queryable> 유형의 개체에서 작동 하</xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> 는 유사한 메서드를 정의 합니다.</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="009ff-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="009ff-115">표준 쿼리 연산자에서 반환 된 단일 값 또는 값의 시퀀스에 따라 해당 실행의 타이밍 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="009ff-116">Singleton 값을 반환 하는 이러한 메서드 (예를 들어 <xref:System.Linq.Enumerable.Average%2A>및 <xref:System.Linq.Enumerable.Sum%2A>) 쿼리는 즉시 실행 합니다.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="009ff-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="009ff-117">시퀀스를 반환 하는 메서드는 쿼리 실행을 지연 하 고 열거 가능한 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="009ff-118">즉, 이러한 메서드를 확장 하는 메모리 내 컬렉션에 대해 작동 하는 방법의 경우 <xref:System.Collections.Generic.IEnumerable%601>, 반환된 된 열거 가능한 개체를 메서드에 전달 된 인수를 캡처합니다.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="009ff-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="009ff-119">해당 개체를 열거 하는 경우 쿼리 연산자의 논리는 사용 하 고 쿼리 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="009ff-120">반면, 확장 하는 메서드 <xref:System.Linq.IQueryable%601>는 쿼리 동작을 구현 하지 않는 하지만 수행할 쿼리를 나타내는 식 트리를 빌드합니다.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="009ff-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="009ff-121">쿼리 처리는 소스에서 처리 <xref:System.Linq.IQueryable%601>개체.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="009ff-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="009ff-122">쿼리 메서드를 호출 하는 쿼리를 훨씬 더 복잡 해질 수 있는 한 쿼리에서 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="009ff-123">다음 코드 예제에서는 시퀀스에 대 한 정보는 표준 쿼리 연산자를 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```vb  
Dim sentence = "the quick brown fox jumps over the lazy dog"  
' Split the string into individual words to create a collection.  
Dim words = sentence.Split(" "c)  
  
Dim query = From word In words   
            Group word.ToUpper() By word.Length Into gr = Group   
            Order By Length _  
            Select Length, GroupedWords = gr  
  
Dim output As New System.Text.StringBuilder  
For Each obj In query  
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))  
    For Each word As String In obj.GroupedWords  
        output.AppendLine(word)  
    Next  
Next  
  
'Display the output  
MsgBox(output.ToString())  
  
' This code example produces the following output:  
'  
' Words of length 3:  
' THE  
' FOX  
' THE  
' DOG  
' Words of length 4:  
' OVER  
' LAZY  
' Words of length 5:  
' QUICK  
' BROWN  
' JUMPS   
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="009ff-124">쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="009ff-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="009ff-125">더 자주 사용 되는 표준 쿼리 연산자 중 일부는 전용의 일부로 호출할 수 있도록 하는 C# 및 Visual Basic 언어 키워드 구문이 *쿼리* *식*합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="009ff-126">표준 쿼리 연산자가 있는 전용 키워드와 해당 구문에 대 한 자세한 내용은 참조 [표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문을](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="009ff-127">표준 쿼리 연산자 확장</span><span class="sxs-lookup"><span data-stu-id="009ff-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="009ff-128">대상 도메인 또는 기술에 대 한 적절 한 만드는 도메인 관련 메서드를 통해 표준 쿼리 연산자 집합을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="009ff-129">또한 원격 평가, 쿼리 변환 및 최적화와 같은 추가 서비스를 제공 하는 고유한 구현으로 표준 쿼리 연산자를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="009ff-130">참조 <xref:System.Linq.Enumerable.AsEnumerable%2A>예제를 보려면.</xref:System.Linq.Enumerable.AsEnumerable%2A></span><span class="sxs-lookup"><span data-stu-id="009ff-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="009ff-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="009ff-131">Related Sections</span></span>  
 <span data-ttu-id="009ff-132">다음 링크 기능에 따라 다양 한 표준 쿼리 연산자에 대 한 추가 정보를 제공 하는 항목으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="009ff-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="009ff-133">데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="009ff-133">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [<span data-ttu-id="009ff-134">집합 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-134">Set Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [<span data-ttu-id="009ff-135">데이터 필터링 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-135">Filtering Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [<span data-ttu-id="009ff-136">수량자 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-136">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [<span data-ttu-id="009ff-137">프로젝션 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-137">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [<span data-ttu-id="009ff-138">데이터 분할 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-138">Partitioning Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [<span data-ttu-id="009ff-139">조인 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-139">Join Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [<span data-ttu-id="009ff-140">데이터 그룹화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-140">Grouping Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [<span data-ttu-id="009ff-141">생성 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-141">Generation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [<span data-ttu-id="009ff-142">같음 연산 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-142">Equality Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [<span data-ttu-id="009ff-143">요소 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-143">Element Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [<span data-ttu-id="009ff-144">데이터 형식 (Visual Basic) 변환</span><span class="sxs-lookup"><span data-stu-id="009ff-144">Converting Data Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [<span data-ttu-id="009ff-145">연결 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-145">Concatenation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [<span data-ttu-id="009ff-146">집계 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="009ff-146">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="009ff-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="009ff-147">See Also</span></span>  
 <span data-ttu-id="009ff-148"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="009ff-148"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="009ff-149"><xref:System.Linq.Queryable></xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="009ff-149"><xref:System.Linq.Queryable></span></span>   
<span data-ttu-id="009ff-150"> [LINQ (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="009ff-150"> [Introduction to LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="009ff-151"> [표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span><span class="sxs-lookup"><span data-stu-id="009ff-151"> [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span></span>  
<span data-ttu-id="009ff-152"> [실행 (Visual Basic) 방식에 따라 표준 쿼리 연산자 분류](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span><span class="sxs-lookup"><span data-stu-id="009ff-152"> [Classification of Standard Query Operators by Manner of Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span></span>  
<span data-ttu-id="009ff-153"> [확장명 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="009ff-153"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
