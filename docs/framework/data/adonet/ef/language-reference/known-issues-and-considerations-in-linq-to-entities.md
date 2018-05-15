---
title: LINQ to Entities에서 알려진 문제 및 고려 사항
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 6b54f75afd52b5179693c5a92ebce2e8aa02f122
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="8da66-102">LINQ to Entities에서 알려진 문제 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8da66-102">Known Issues and Considerations in LINQ to Entities</span></span>
<span data-ttu-id="8da66-103">이 단원에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리와 관련하여 알려진 문제에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-103">This section provides information about known issues with [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
-   [<span data-ttu-id="8da66-104">LINQ 쿼리를 캐시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-104">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
-   [<span data-ttu-id="8da66-105">순서 정보 손실</span><span class="sxs-lookup"><span data-stu-id="8da66-105">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
-   [<span data-ttu-id="8da66-106">부호 없는 정수 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="8da66-106">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
-   [<span data-ttu-id="8da66-107">형식 변환 오류</span><span class="sxs-lookup"><span data-stu-id="8da66-107">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
-   [<span data-ttu-id="8da66-108">지원 되지 않는 스칼라가 아닌 변수 참조</span><span class="sxs-lookup"><span data-stu-id="8da66-108">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
-   [<span data-ttu-id="8da66-109">SQL Server 2000과 중첩된 쿼리가 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="8da66-109">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
-   [<span data-ttu-id="8da66-110">익명 형식으로 프로젝션</span><span class="sxs-lookup"><span data-stu-id="8da66-110">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="8da66-111">캐시할 수 없는 LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="8da66-111">LINQ Queries That cannot be Cached</span></span>  
 <span data-ttu-id="8da66-112">.NET Framework 4.5부터 시작하여 LINQ to Entities 쿼리가 자동으로 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-112">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="8da66-113">그러나 메모리 내 컬렉션에 `Enumerable.Contains` 연산자를 적용하는 LINQ to Entities 쿼리는 자동으로 캐시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-113">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="8da66-114">또한 메모리 내 컬렉션은 컴파일된 LINQ 쿼리에서 매개 변수화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-114">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a><span data-ttu-id="8da66-115">순서 정보 손실</span><span class="sxs-lookup"><span data-stu-id="8da66-115">Ordering Information Lost</span></span>  
 <span data-ttu-id="8da66-116">열을 익명 형식으로 프로젝션하면 호환성 수준 "80"에서 [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] 데이터베이스에 대해 실행되는 일부 쿼리에서 순서 정보가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-116">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] database set to a compatibility level of "80".</span></span>  <span data-ttu-id="8da66-117">이런 현상은 다음 예제와 같이 정렬 순서 목록에 있는 열 이름이 선택기의 열 이름과 일치할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-117">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="8da66-118">부호 없는 정수 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="8da66-118">Unsigned Integers Not Supported</span></span>  
 <span data-ttu-id="8da66-119">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]에서 부호 없는 정수가 지원되지 않으므로 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 쿼리에서 부호 없는 정수 형식을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-119">Specifying an unsigned integer type in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is not supported because the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not support unsigned integers.</span></span> <span data-ttu-id="8da66-120">부호 없는 정수를 지정 하는 경우는 <xref:System.ArgumentException> 다음 예제와 같이 쿼리 식 변환 하는 동안 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-120">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="8da66-121">다음 예제에서는 ID 48000인 주문을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-121">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a><span data-ttu-id="8da66-122">형식 변환 오류</span><span class="sxs-lookup"><span data-stu-id="8da66-122">Type Conversion Errors</span></span>  
 <span data-ttu-id="8da66-123">Visual Basic에서 `CByte` 함수를 사용하여 값이 1인 SQL Server 비트 형식의 열에 속성이 매핑되면 "산술 오버플로 오류" 메시지와 함께 <xref:System.Data.SqlClient.SqlException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-123">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="8da66-124">다음 예제는 AdventureWorks 샘플 데이터베이스의 `Product.MakeFlag` 열을 쿼리하며, 쿼리 결과가 반복되면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-124">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="8da66-125">스칼라가 아닌 변수 참조는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="8da66-125">Referencing Non-Scalar Variables Not Supported</span></span>  
 <span data-ttu-id="8da66-126">엔터티와 같이 스칼라가 아닌 변수를 쿼리에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-126">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="8da66-127">이러한 쿼리가 실행되면 <xref:System.NotSupportedException> 예외가 throw되고 "`EntityType` 형식의 상수 값을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-127">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="8da66-128">이 컨텍스트에서는 기본 형식('Int32, String 및 Guid')만 지원됩니다."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-128">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8da66-129">스칼라 변수 컬렉션 참조가 지원됨</span><span class="sxs-lookup"><span data-stu-id="8da66-129">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="8da66-130">SQL Server 2000에서 중첩 쿼리가 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="8da66-130">Nested Queries May Fail with SQL Server 2000</span></span>  
 <span data-ttu-id="8da66-131">SQL Server 2000을 사용할 경우 세 수준 이상으로 중첩된 Transact-SQL 쿼리를 생성하는 LINQ to Entities 쿼리가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-131">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="8da66-132">익명 형식으로 프로젝션</span><span class="sxs-lookup"><span data-stu-id="8da66-132">Projecting to an Anonymous Type</span></span>  
 <span data-ttu-id="8da66-133"><xref:System.Data.Objects.ObjectQuery%601.Include%2A>에서 <xref:System.Data.Objects.ObjectQuery%601> 메서드를 사용하여 관련 개체를 포함하도록 초기 쿼리 경로를 정의한 다음 LINQ를 사용하여 반환된 개체를 익명 형식으로 프로젝션하면 Include 메서드에 지정된 개체가 쿼리 결과에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-133">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="8da66-134">관련 개체를 가져오려면 반환된 형식을 익명 형식으로 프로젝션하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8da66-134">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="8da66-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8da66-135">See Also</span></span>  
 [<span data-ttu-id="8da66-136">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8da66-136">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
