---
title: "방법: 변경 내용 충돌 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: caacb4c3b877ce6bf7ba11001f602a76ad7f9734
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="534cf-102">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="534cf-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="534cf-103">검색, 평가 및 동시성 충돌을 해결할 수 있도록 Api의 컬렉션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="534cf-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="534cf-104">In This Section</span></span>  
 [<span data-ttu-id="534cf-105">방법: 전송 충돌 검색 및 해결</span><span class="sxs-lookup"><span data-stu-id="534cf-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="534cf-106">동시성 충돌을 검색하고 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="534cf-107">방법: 동시성 예외가 Throw되는 시기 지정</span><span class="sxs-lookup"><span data-stu-id="534cf-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="534cf-108">동시성 충돌에 대해 알림을 받아야 할 경우를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="534cf-109">방법: 동시성 충돌에 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="534cf-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="534cf-110">동시성 충돌 확인 여부를 지정하기 위해 멤버에 특성을 부여하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="534cf-111">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="534cf-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="534cf-112">엔터티 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="534cf-113">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="534cf-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="534cf-114">멤버 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="534cf-115">방법: 데이터베이스 값을 보존하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="534cf-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="534cf-116">현재 값을 데이터베이스 값에 덮어쓰는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="534cf-117">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="534cf-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="534cf-118">데이터베이스 값을 덮어써 현재 값을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="534cf-119">방법: 데이터베이스 값을 병합하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="534cf-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="534cf-120">데이터베이스와 현재 값을 병합하여 충돌을 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="534cf-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="534cf-121">Related Sections</span></span>  
 [<span data-ttu-id="534cf-122">낙관적 동시성: 개요</span><span class="sxs-lookup"><span data-stu-id="534cf-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="534cf-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성에 적용하는 용어를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="534cf-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
