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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1ed1c70687b1a4aec542aff5046b237fa4710fa4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="4fbbf-102">-- (주석)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4fbbf-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="4fbbf-103"> 쿼리에는 주석이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-103"> queries can contain comments.</span></span> <span data-ttu-id="4fbbf-104">주석 줄은 대시 두 개(`--`)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fbbf-105">구문</span><span class="sxs-lookup"><span data-stu-id="4fbbf-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="4fbbf-106">인수</span><span class="sxs-lookup"><span data-stu-id="4fbbf-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="4fbbf-107">주석의 텍스트를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fbbf-108">예</span><span class="sxs-lookup"><span data-stu-id="4fbbf-108">Example</span></span>  
 <span data-ttu-id="4fbbf-109">다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="4fbbf-110">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4fbbf-111">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4fbbf-112">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4fbbf-113">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4fbbf-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="4fbbf-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fbbf-114">See Also</span></span>  
 [<span data-ttu-id="4fbbf-115">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="4fbbf-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="4fbbf-116">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="4fbbf-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
