---
title: "방법: 관련 데이터 검색의 양 제어"
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
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3beb6f6b019535e273df7103e2e22f1be669797a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="b9619-102">방법: 관련 데이터 검색의 양 제어</span><span class="sxs-lookup"><span data-stu-id="b9619-102">How to: Control How Much Related Data Is Retrieved</span></span>
<span data-ttu-id="b9619-103"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 메서드를 사용하여 동시에 검색되어야 하는 주 대상과 관련된 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="b9619-104">예를 들어 고객 주문에 대한 정보가 필요한 경우 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>를 사용하여 주문 정보와 고객 정보가 검색되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="b9619-105">이 접근 방법은 두 가지 정보에 대한 데이터베이스에서 원트립만의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9619-106">고객을 대상으로 할 경우 주문을 검색하는 것과 같이 외적을 하나의 큰 프로젝션처럼 검색하여 쿼리의 주 대상과 관련된 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="b9619-107">그러나 이러한 방법에는 종종 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="b9619-108">예를 들어 결과는 엔터티가 아니라 프로젝션이기에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변경되고 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="b9619-109">원하지 않는 많은 데이터가 검색될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9619-110">예</span><span class="sxs-lookup"><span data-stu-id="b9619-110">Example</span></span>  
 <span data-ttu-id="b9619-111">다음 예제에서 쿼리를 실행하면 런던에 살고 있는 모든 `Orders`에 대한 모든 `Customers`가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="b9619-112">따라서 이후에 `Orders` 개체의 `Customer` 속성에 액세스해도 새 데이터베이스 쿼리가 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9619-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b9619-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9619-113">See Also</span></span>  
 [<span data-ttu-id="b9619-114">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="b9619-114">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
