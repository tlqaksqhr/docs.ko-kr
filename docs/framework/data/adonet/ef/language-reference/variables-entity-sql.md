---
title: "변수(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 551b6d6feab6829c9a2f6f2e89e1918acf463411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variables-entity-sql"></a><span data-ttu-id="148a8-102">변수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="148a8-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="148a8-103">변수</span><span class="sxs-lookup"><span data-stu-id="148a8-103">Variable</span></span>  
 <span data-ttu-id="148a8-104">변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="148a8-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="148a8-105">변수 참조는 유효 해야 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식별자에 정의 된 대로 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="148a8-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="148a8-106">다음 예제에서는 식에서 변수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="148a8-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="148a8-107">FROM 절의 `c`는 변수 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="148a8-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="148a8-108">SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="148a8-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="148a8-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="148a8-109">See Also</span></span>  
 [<span data-ttu-id="148a8-110">식별자</span><span class="sxs-lookup"><span data-stu-id="148a8-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [<span data-ttu-id="148a8-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="148a8-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [<span data-ttu-id="148a8-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="148a8-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
