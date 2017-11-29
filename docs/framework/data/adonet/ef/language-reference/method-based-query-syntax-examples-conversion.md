---
title: "메서드 기반 쿼리 구문 예제: 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4c1d7ad217d863e55943ea99c1623060bac89d12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="6a903-102">메서드 기반 쿼리 구문 예제: 변환</span><span class="sxs-lookup"><span data-stu-id="6a903-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="6a903-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다는 <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> 및 <xref:System.Linq.Enumerable.ToList%2A> 를 쿼리 하는 메서드는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a903-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="6a903-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a903-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6a903-105">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="6a903-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="6a903-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="6a903-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a903-107">예제</span><span class="sxs-lookup"><span data-stu-id="6a903-107">Example</span></span>  
 <span data-ttu-id="6a903-108">다음 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드로 시퀀스를 즉시 계산하여 배열에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6a903-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="6a903-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="6a903-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a903-110">예제</span><span class="sxs-lookup"><span data-stu-id="6a903-110">Example</span></span>  
 <span data-ttu-id="6a903-111">다음 예제에서는 <xref:System.Linq.Enumerable.ToDictionary%2A> 메서드로 시퀀스 및 관련 키 식을 즉시 계산하여 사전에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6a903-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="6a903-112">ToList</span><span class="sxs-lookup"><span data-stu-id="6a903-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a903-113">예제</span><span class="sxs-lookup"><span data-stu-id="6a903-113">Example</span></span>  
 <span data-ttu-id="6a903-114">다음 예제에서는 <xref:System.Linq.Enumerable.ToList%2A> 메서드로 시퀀스를 즉시 계산하여 <xref:System.Collections.Generic.List%601>에 넣습니다. 여기서 `T`는 <xref:System.Data.DataRow> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6a903-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="6a903-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a903-115">See Also</span></span>  
 [<span data-ttu-id="6a903-116">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="6a903-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
