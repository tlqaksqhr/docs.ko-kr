---
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 6d1746bb51af4795f09c47f808cf9a29d0370f18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="unsupported-expressions"></a><span data-ttu-id="9d5da-102">지원 되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="9d5da-102">Unsupported expressions</span></span>

<span data-ttu-id="9d5da-103">이 항목에서는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 지원되지 않는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="9d5da-104">자세한 내용은 참조 [Entity SQL 차이점 transact-sql에서](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="9d5da-105">정규화 된 조건자</span><span class="sxs-lookup"><span data-stu-id="9d5da-105">Quantified predicates</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="9d5da-106">에서는 다음 폼을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-106"> allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="9d5da-107">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="9d5da-108">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal > e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="9d5da-109">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="9d5da-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="9d5da-110">에서는 모든 열이 프로젝션되어야 함을 나타내도록 SELECT 절에서 \* 연산자를 사용하도록 지원합니다. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5da-110"> supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="9d5da-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="9d5da-111">See also</span></span>

[<span data-ttu-id="9d5da-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="9d5da-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
[<span data-ttu-id="9d5da-113">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="9d5da-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
