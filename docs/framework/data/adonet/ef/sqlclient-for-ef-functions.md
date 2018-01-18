---
title: "Entity Framework용 SqlClient 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71a3613c-b94e-494c-8ad8-90cf86ae0b87
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6fb244d25a61f0c842455d6f1d2e5eb2fd9ff6f9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="sqlclient-for-entity-framework-functions"></a><span data-ttu-id="42075-102">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="42075-102">SqlClient for Entity Framework Functions</span></span>
<span data-ttu-id="42075-103">Entity Framework용 .NET Framework Data Provider for SQL Server(SqlClient)에서는 수치 및 집계 계산을 수행할 함수 집합과 `System.DateTime` 및 `string` 연산을 수행할 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42075-103">The .NET Framework Data Provider for SQL Server (SqlClient) for the Entity Framework provides a set of functions to perform mathematical and aggregation calculations, as well as functions to perform `System.DateTime` and `string` operations.</span></span> <span data-ttu-id="42075-104">이러한 함수는 `SQLServer` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42075-104">These functions are in the `SQLServer` namespace.</span></span>  
  
 <span data-ttu-id="42075-105">모든 공급자와 작동 해야 하는 함수의 목록에 대 한 참조 [정식 함수](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42075-105">For a list of functions that should work with any provider, see [Canonical Functions](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="42075-106">SQL Server 함수와 어떻게 정식 함수 지도 대 한 정보를 참조 하십시오. [개념적 모델 정식 SQL Server 함수 매핑](../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42075-106">For information about how canonical functions map to SQL Server functions, see [Conceptual Model Canonical to SQL Server Functions Mapping](../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42075-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="42075-107">In This Section</span></span>  
 [<span data-ttu-id="42075-108">개념적 모델 정식 함수와 SQL Server 함수 매핑</span><span class="sxs-lookup"><span data-stu-id="42075-108">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
  
 [<span data-ttu-id="42075-109">집계 함수</span><span class="sxs-lookup"><span data-stu-id="42075-109">Aggregate Functions</span></span>](../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
 [<span data-ttu-id="42075-110">날짜 및 시간 함수</span><span class="sxs-lookup"><span data-stu-id="42075-110">Date and Time Functions</span></span>](../../../../../docs/framework/data/adonet/ef/date-and-time-functions.md)  
  
 [<span data-ttu-id="42075-111">수학 함수</span><span class="sxs-lookup"><span data-stu-id="42075-111">Mathematical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/mathematical-functions.md)  
  
 [<span data-ttu-id="42075-112">문자열 함수</span><span class="sxs-lookup"><span data-stu-id="42075-112">String Functions</span></span>](../../../../../docs/framework/data/adonet/ef/string-functions.md)  
  
 [<span data-ttu-id="42075-113">시스템 함수</span><span class="sxs-lookup"><span data-stu-id="42075-113">System Functions</span></span>](../../../../../docs/framework/data/adonet/ef/system-functions.md)  
  
## <a name="see-also"></a><span data-ttu-id="42075-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42075-114">See Also</span></span>  
 [<span data-ttu-id="42075-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="42075-115">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="42075-116">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="42075-116">Entity SQL Overview</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
