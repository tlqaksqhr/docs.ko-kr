---
title: "조인 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
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
ms.openlocfilehash: 5b561f66069b042f3216c80c7b8b3a13df63647e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="join-operations-visual-basic"></a><span data-ttu-id="d163d-102">조인 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d163d-102">Join Operations (Visual Basic)</span></span>
<span data-ttu-id="d163d-103">A *조인* 두 데이터 소스의 개체를 다른 데이터 소스에서 공통 특성을 공유 하는 개체와 하나 이상의 데이터 원본에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="d163d-104">서로 간의 관계를 직접 적용할 수 없는 데이터 소스를 대상으로 하는 쿼리에서는 조인이 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="d163d-105">개체 지향 프로그래밍에서 데이터 소스 간의 관계를 직접 적용할 수 없다는 것은 모델링되지 않은 개체 간에 상관 관계가 있음을 의미할 수 있습니다(예: 단방향 관계에서 반대 방향을 사용).</span><span class="sxs-lookup"><span data-stu-id="d163d-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="d163d-106">단방향 관계의 예로는 Customer 클래스가 City 형식 속성을 포함하는데 City 클래스는 Customer 개체의 컬렉션인 속성을 포함하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="d163d-107">City 개체 목록이 있는 경우 각 구/군/시의 모든 고객을 찾으려면 조인 작업을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="d163d-108"><xref:System.Linq.Enumerable.Join%2A>및 <xref:System.Linq.Enumerable.GroupJoin%2A>.</xref:System.Linq.Enumerable.GroupJoin%2A> </xref:System.Linq.Enumerable.Join%2A> LINQ 프레임 워크에서 제공 하는 조인 메서드는</span><span class="sxs-lookup"><span data-stu-id="d163d-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="d163d-109">이러한 메서드는 해당 키가 같은지 여부에 따라 두 데이터 소스는 조인 또는 동등 조인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="d163d-110">비교를 위해 Transact-SQL에서는 '같음'이 아닌 '보다 작음' 연산자와 같은 조인 연산자를 지원합니다. 관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>는 유형의 조인 내부 조인을 구현에서 다른 데이터 집합에는 일치 항목이 있는 개체만 반환 됩니다.</xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="d163d-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="d163d-111"><xref:System.Linq.Enumerable.GroupJoin%2A>메서드에, 관계형 데이터베이스에서에서 직접 해당 하는 않지만 내부 조인 및 왼쪽된 우선 외부 조인의 상위 집합을 구현 합니다.</xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="d163d-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="d163d-112">왼쪽된 우선 외부 조인을 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째 (왼쪽된) 데이터 소스의 각 요소를 반환 하는 조인이입니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="d163d-113">다음 그림에서는 내부 조인 또는 왼쪽 우선 외부 조인에 포함된 두 집합 및 해당 집합 내의 요소를 개념적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="d163d-114">![내부/외부를 보여 주는 두 개의 겹치는 원입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="d163d-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d163d-115">메서드</span><span class="sxs-lookup"><span data-stu-id="d163d-115">Methods</span></span>  
  
|<span data-ttu-id="d163d-116">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="d163d-116">Method Name</span></span>|<span data-ttu-id="d163d-117">설명</span><span class="sxs-lookup"><span data-stu-id="d163d-117">Description</span></span>|<span data-ttu-id="d163d-118">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="d163d-118">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d163d-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d163d-119">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d163d-120">Join</span><span class="sxs-lookup"><span data-stu-id="d163d-120">Join</span></span>|<span data-ttu-id="d163d-121">키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 값 쌍을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`From x In …, y In … Where x.a = y.a`<br /><br /> <span data-ttu-id="d163d-122">또는</span><span class="sxs-lookup"><span data-stu-id="d163d-122">-or-</span></span><br /><br /> `Join … [As …]In … On …`|<span data-ttu-id="d163d-123"><xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d163d-123"><xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="d163d-124"><xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d163d-124"><xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d163d-125">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="d163d-125">GroupJoin</span></span>|<span data-ttu-id="d163d-126">키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 결과로 생성된 일치 항목을 요소마다 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="d163d-126">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`Group Join … In … On …`|<span data-ttu-id="d163d-127"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d163d-127"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="d163d-128"><xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d163d-128"><xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d163d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d163d-129">See Also</span></span>  
 <span data-ttu-id="d163d-130"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="d163d-130"><xref:System.Linq></span></span>   
<span data-ttu-id="d163d-131"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d163d-131"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="d163d-132"> [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="d163d-132"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="d163d-133"> [방법: 조인 및 교차곱 쿼리 작성](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span><span class="sxs-lookup"><span data-stu-id="d163d-133"> [Formulate Joins and Cross-Product Queries](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span></span>  
<span data-ttu-id="d163d-134"> [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="d163d-134"> [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) </span></span>  
<span data-ttu-id="d163d-135"> [방법: 서로 다른 파일 (Visual Basic) (LINQ)의 콘텐츠 조인](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span><span class="sxs-lookup"><span data-stu-id="d163d-135"> [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span></span>  
<span data-ttu-id="d163d-136"> [방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)</span><span class="sxs-lookup"><span data-stu-id="d163d-136"> [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)</span></span>
