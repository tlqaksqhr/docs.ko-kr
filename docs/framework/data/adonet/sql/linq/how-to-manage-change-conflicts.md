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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 87d895c8d5531d091d773e9f2d51b89408169022
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="404e5-102">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="404e5-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="404e5-103">검색, 평가 및 동시성 충돌을 해결할 수 있도록 Api의 컬렉션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="404e5-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="404e5-104">In This Section</span></span>  
 [<span data-ttu-id="404e5-105">방법: 검색 및 전송 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="404e5-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="404e5-106">동시성 충돌을 검색하고 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="404e5-107">방법: 동시성 예외가 Throw 되는 시기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="404e5-108">동시성 충돌에 대해 알림을 받아야 할 경우를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="404e5-109">방법: 동시성 충돌에 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="404e5-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="404e5-110">동시성 충돌 확인 여부를 지정하기 위해 멤버에 특성을 부여하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="404e5-111">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="404e5-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="404e5-112">엔터티 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="404e5-113">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="404e5-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="404e5-114">멤버 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="404e5-115">방법: 데이터베이스 값을 유지 하 여 충돌을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="404e5-116">현재 값을 데이터베이스 값에 덮어쓰는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="404e5-117">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="404e5-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="404e5-118">데이터베이스 값을 덮어써 현재 값을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="404e5-119">방법: 데이터베이스 값과 병합 하 여 충돌을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="404e5-120">데이터베이스와 현재 값을 병합하여 충돌을 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="404e5-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="404e5-121">Related Sections</span></span>  
 [<span data-ttu-id="404e5-122">낙관적 동시성: 개요</span><span class="sxs-lookup"><span data-stu-id="404e5-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="404e5-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성에 적용하는 용어를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="404e5-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
