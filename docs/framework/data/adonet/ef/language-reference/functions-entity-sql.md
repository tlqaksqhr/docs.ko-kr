---
title: "함수(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9008360a4af0a669a223a2e56ee5152b23c6ebe4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="functions-entity-sql"></a><span data-ttu-id="c5604-102">함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c5604-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="c5604-103">Entity SQL에서는 사용자 정의 함수, 정식 함수 및 공급자 특정 함수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="c5604-104">사용자 정의 함수는 개념적 모델에 지정되거나 쿼리에 인라인으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="c5604-105">자세한 내용은 참조 [사용자 정의 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="c5604-106">정식 함수는 Entity Framework에 미리 정의되어 있으며 데이터 공급자의 지원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="c5604-107">공급자가 지원하지 않는 함수를 사용자가 호출하는 경우 Entity SQL 명령은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="c5604-108">따라서, 일반적으로 정식 함수는 공급자 특정 네임스페이스에 들어 있는 저장소 특정 함수의 경우에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="c5604-109">자세한 내용은 참조 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="c5604-110">Microsoft SQL 클라이언트 관리 공급자에서는 공급자 특정 함수 집합이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="c5604-111">자세한 내용은 참조 [엔터티 프레임 워크 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5604-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5604-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c5604-112">In This Section</span></span>  
 [<span data-ttu-id="c5604-113">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="c5604-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="c5604-114">함수 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="c5604-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="c5604-115">집계 함수</span><span class="sxs-lookup"><span data-stu-id="c5604-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5604-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5604-116">See Also</span></span>  
 [<span data-ttu-id="c5604-117">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="c5604-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
