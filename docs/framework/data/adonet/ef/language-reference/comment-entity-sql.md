---
title: "-- (주석)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 483e1c69aea94375983acd840f84512de54bc746
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="517ba-102">-- (주석)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="517ba-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="517ba-103"> 쿼리에는 주석이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-103"> queries can contain comments.</span></span> <span data-ttu-id="517ba-104">주석 줄은 대시 두 개(`--`)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="517ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="517ba-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="517ba-106">인수</span><span class="sxs-lookup"><span data-stu-id="517ba-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="517ba-107">주석의 텍스트를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="517ba-108">예</span><span class="sxs-lookup"><span data-stu-id="517ba-108">Example</span></span>  
 <span data-ttu-id="517ba-109">다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="517ba-110">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="517ba-111">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="517ba-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="517ba-112">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="517ba-113">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="517ba-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="517ba-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="517ba-114">See Also</span></span>  
 [<span data-ttu-id="517ba-115">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="517ba-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="517ba-116">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="517ba-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
