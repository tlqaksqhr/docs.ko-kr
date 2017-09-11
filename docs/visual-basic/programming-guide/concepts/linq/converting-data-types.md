---
title: "데이터 형식 (Visual Basic) 변환 | Microsoft 문서"
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
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
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
ms.openlocfilehash: 948779e1648291b00a68bfd83d57750d48a9a6d8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="4f48d-102">데이터 형식 (Visual Basic) 변환</span><span class="sxs-lookup"><span data-stu-id="4f48d-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="4f48d-103">변환 메서드는 입력된 개체의 형식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="4f48d-104">LINQ 쿼리에서 변환 작업은 다양 한 응용 프로그램에에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="4f48d-105">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="4f48d-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>메서드는 표준 쿼리 연산자의 형식의 사용자 지정 구현을 숨길 데 사용할 수 있습니다.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="4f48d-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>LINQ 쿼리에 대 한 매개 변수가 없는 컬렉션을 사용 하도록 설정 하려면 메서드를 사용할 수 있습니다.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="4f48d-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, 및 <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>쿼리 열거 될 때까지 연기 하는 대신 쿼리를 즉시 실행 하려면 메서드를 사용할 수 있습니다.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f48d-109">메서드</span><span class="sxs-lookup"><span data-stu-id="4f48d-109">Methods</span></span>  
 <span data-ttu-id="4f48d-110">다음 표에서 데이터 형식 변환을 수행 하는 표준 쿼리 연산자 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="4f48d-111">이름이 "As"로 시작 합니다.이 테이블의 변환 메서드는 소스 컬렉션의 정적 형식을 바뀌지만 열거 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="4f48d-112">이름이 "소스 컬렉션을 열거 하 고 해당 컬렉션에 항목을 추가"를로 시작 하는 메서드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="4f48d-113">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="4f48d-113">Method Name</span></span>|<span data-ttu-id="4f48d-114">설명</span><span class="sxs-lookup"><span data-stu-id="4f48d-114">Description</span></span>|<span data-ttu-id="4f48d-115">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="4f48d-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4f48d-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4f48d-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="4f48d-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="4f48d-117">AsEnumerable</span></span>|<span data-ttu-id="4f48d-118"><xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 로 형식화 된 입력을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="4f48d-119">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-119">Not applicable.</span></span>|<span data-ttu-id="4f48d-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="4f48d-121">AsQueryable</span></span>|<span data-ttu-id="4f48d-122">(일반) <xref:System.Collections.IEnumerable>(일반) <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> 에</xref:System.Collections.IEnumerable> 변환</span><span class="sxs-lookup"><span data-stu-id="4f48d-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="4f48d-123">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-123">Not applicable.</span></span>|<span data-ttu-id="4f48d-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-125">Cast</span><span class="sxs-lookup"><span data-stu-id="4f48d-125">Cast</span></span>|<span data-ttu-id="4f48d-126">지정 된 형식 컬렉션의 요소를 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-126">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<span data-ttu-id="4f48d-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="4f48d-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-129">OfType</span><span class="sxs-lookup"><span data-stu-id="4f48d-129">OfType</span></span>|<span data-ttu-id="4f48d-130">지정된 된 형식으로 캐스팅할 수에 따라 값을 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="4f48d-131">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-131">Not applicable.</span></span>|<span data-ttu-id="4f48d-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="4f48d-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-134">ToArray</span><span class="sxs-lookup"><span data-stu-id="4f48d-134">ToArray</span></span>|<span data-ttu-id="4f48d-135">배열에 컬렉션으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-135">Converts a collection to an array.</span></span> <span data-ttu-id="4f48d-136">이 메서드는 쿼리 실행이 되도록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-136">This method forces query execution.</span></span>|<span data-ttu-id="4f48d-137">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-137">Not applicable.</span></span>|<span data-ttu-id="4f48d-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-139">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="4f48d-139">ToDictionary</span></span>|<span data-ttu-id="4f48d-140">에 요소 배치는 <xref:System.Collections.Generic.Dictionary%602>키 선택기 함수에 따라.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="4f48d-140">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="4f48d-141">이 메서드는 쿼리 실행이 되도록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-141">This method forces query execution.</span></span>|<span data-ttu-id="4f48d-142">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-142">Not applicable.</span></span>|<span data-ttu-id="4f48d-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-144">ToList</span><span class="sxs-lookup"><span data-stu-id="4f48d-144">ToList</span></span>|<span data-ttu-id="4f48d-145"><xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> 컬렉션으로 변환</span><span class="sxs-lookup"><span data-stu-id="4f48d-145">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="4f48d-146">이 메서드는 쿼리 실행이 되도록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-146">This method forces query execution.</span></span>|<span data-ttu-id="4f48d-147">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-147">Not applicable.</span></span>|<span data-ttu-id="4f48d-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="4f48d-149">ToLookup</span><span class="sxs-lookup"><span data-stu-id="4f48d-149">ToLookup</span></span>|<span data-ttu-id="4f48d-150">에 요소 배치는 <xref:System.Linq.Lookup%602>키 선택기 함수에 따라 (예: 일 대 다 사전).</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="4f48d-150">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="4f48d-151">이 메서드는 쿼리 실행이 되도록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-151">This method forces query execution.</span></span>|<span data-ttu-id="4f48d-152">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4f48d-152">Not applicable.</span></span>|<span data-ttu-id="4f48d-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f48d-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="4f48d-154">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="4f48d-154">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="4f48d-155">다음 코드 예제에서는 `From As` 절은 하위 형식 에서만 사용할 수 있는 멤버에 액세스 하기 전에 하위 형식에 형식을 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48d-155">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f48d-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f48d-156">See Also</span></span>  
 <span data-ttu-id="4f48d-157"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="4f48d-157"><xref:System.Linq></span></span>   
<span data-ttu-id="4f48d-158"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4f48d-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="4f48d-159"> [From 절](../../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="4f48d-159"> [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="4f48d-160"> [방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="4f48d-160"> [How to: Query an ArrayList with LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span></span>
