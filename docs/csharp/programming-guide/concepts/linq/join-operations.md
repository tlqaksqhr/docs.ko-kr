---
title: "조인 작업(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df2f88f2988a4c91730bcfc4e39f10e3471e4ddf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="join-operations-c"></a><span data-ttu-id="ea1ce-102">조인 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="ea1ce-102">Join Operations (C#)</span></span>
<span data-ttu-id="ea1ce-103">두 데이터 소스를 *조인*하는 것은 한 데이터 소스의 개체를 공통 특성을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="ea1ce-104">서로 간의 관계를 직접 적용할 수 없는 데이터 소스를 대상으로 하는 쿼리에서는 조인이 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="ea1ce-105">개체 지향 프로그래밍에서 데이터 소스 간의 관계를 직접 적용할 수 없다는 것은 모델링되지 않은 개체 간에 상관 관계가 있음을 의미할 수 있습니다(예: 단방향 관계에서 반대 방향을 사용).</span><span class="sxs-lookup"><span data-stu-id="ea1ce-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="ea1ce-106">단방향 관계의 예로는 Customer 클래스가 City 형식 속성을 포함하는데 City 클래스는 Customer 개체의 컬렉션인 속성을 포함하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="ea1ce-107">City 개체 목록이 있는 경우 각 구/군/시의 모든 고객을 찾으려면 조인 작업을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="ea1ce-108">LINQ 프레임워크에 제공되는 조인 메서드는 <xref:System.Linq.Enumerable.Join%2A> 및 <xref:System.Linq.Enumerable.GroupJoin%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="ea1ce-109">이러한 메서드는 키가 같은지 여부에 따라 두 데이터 소스의 일치 여부를 확인하는 조인인 동등 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="ea1ce-110">비교를 위해 Transact-SQL에서는 '같음'이 아닌 '보다 작음' 연산자와 같은 조인 연산자를 지원합니다. 관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>은 내부 조인을 구현합니다. 내부 조인은 다른 데이터 집합에 일치하는 항목이 있는 개체만 반환하는 유형의 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="ea1ce-111"><xref:System.Linq.Enumerable.GroupJoin%2A> 메서드에는 관계형 데이터베이스 측면에 직접 상응하는 기능이 없지만 내부 조인 및 왼쪽 우선 외부 조인의 상위 집합을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="ea1ce-112">왼쪽 우선 외부 조인은 다른 데이터 소스에 서로 관련된 요소가 없더라도 첫 번째(왼쪽) 데이터 소스의 각 요소를 반환하는 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="ea1ce-113">다음 그림에서는 내부 조인 또는 왼쪽 우선 외부 조인에 포함된 두 집합 및 해당 집합 내의 요소를 개념적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="ea1ce-114">![내부&#47;외부를 보여 주는 두 개의 겹치는 원](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="ea1ce-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea1ce-115">메서드</span><span class="sxs-lookup"><span data-stu-id="ea1ce-115">Methods</span></span>  
  
|<span data-ttu-id="ea1ce-116">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="ea1ce-116">Method Name</span></span>|<span data-ttu-id="ea1ce-117">설명</span><span class="sxs-lookup"><span data-stu-id="ea1ce-117">Description</span></span>|<span data-ttu-id="ea1ce-118">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="ea1ce-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="ea1ce-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ea1ce-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ea1ce-120">Join</span><span class="sxs-lookup"><span data-stu-id="ea1ce-120">Join</span></span>|<span data-ttu-id="ea1ce-121">키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 값 쌍을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|<span data-ttu-id="ea1ce-122">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="ea1ce-122">GroupJoin</span></span>|<span data-ttu-id="ea1ce-123">키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 결과로 생성된 일치 항목을 요소마다 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="ea1ce-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="ea1ce-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea1ce-124">See Also</span></span>  
 <span data-ttu-id="ea1ce-125"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="ea1ce-125"><xref:System.Linq></span></span>   
 <span data-ttu-id="ea1ce-126">[표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-126">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="ea1ce-127">[무명 형식](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-127">[Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="ea1ce-128">[조인 및 교차곱 쿼리 작성](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-128">[Formulate Joins and Cross-Product Queries](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span></span>  
 <span data-ttu-id="ea1ce-129">[join 절](../../../../csharp/language-reference/keywords/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-129">[join clause](../../../../csharp/language-reference/keywords/join-clause.md) </span></span>  
 <span data-ttu-id="ea1ce-130">[방법: 복합 키를 사용하여 조인](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-130">[How to: Join by Using Composite Keys](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span></span>  
 <span data-ttu-id="ea1ce-131">[방법: 서로 다른 파일의 콘텐츠 조인(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-131">[How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span></span>  
 <span data-ttu-id="ea1ce-132">[방법: Join 절 결과를 순서대로 정렬](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-132">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 <span data-ttu-id="ea1ce-133">[방법: 사용자 지정 조인 작업 수행](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-133">[How to: Perform Custom Join Operations](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md) </span></span>  
 <span data-ttu-id="ea1ce-134">[방법: 그룹화 조인 수행](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-134">[How to: Perform Grouped Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span></span>  
 <span data-ttu-id="ea1ce-135">[방법: 내부 조인 수행](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-135">[How to: Perform Inner Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span></span>  
 <span data-ttu-id="ea1ce-136">[방법: 왼쪽 우선 외부 조인 수행](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span><span class="sxs-lookup"><span data-stu-id="ea1ce-136">[How to: Perform Left Outer Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span></span>  
 [<span data-ttu-id="ea1ce-137">방법: 여러 소스로 개체 컬렉션 채우기(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="ea1ce-137">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)

