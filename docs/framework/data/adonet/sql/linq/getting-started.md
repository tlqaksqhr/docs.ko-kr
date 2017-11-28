---
title: "시작"
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
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0c6db401f710c470ea890a7a7ac090fabef5d64c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started"></a><span data-ttu-id="5ae02-102">시작</span><span class="sxs-lookup"><span data-stu-id="5ae02-102">Getting Started</span></span>
<span data-ttu-id="5ae02-103">사용 하 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용할 수 있습니다는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 기술 SQL 액세스 하는 메모리 내 컬렉션에 액세스 하는 것 처럼 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="5ae02-104">예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `Customers`에서 `London`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="5ae02-105">루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="5ae02-106">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5ae02-106">Next Steps</span></span>  
 <span data-ttu-id="5ae02-107">삽입 및 업데이트를 비롯 한 몇 가지 추가 예를 참조 하세요. [무엇 있습니다 수 수행 된 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="5ae02-108">그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5ae02-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5ae02-109">참조 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="5ae02-110">마지막으로, 직접 시작 하는 방법에 알아봅니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 읽어 프로젝트 [를 사용 하 여 LINQ to SQL 위한 일반 단계](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae02-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae02-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ae02-111">See Also</span></span>  
 [<span data-ttu-id="5ae02-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5ae02-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="5ae02-113">LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="5ae02-113">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="5ae02-114">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="5ae02-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
