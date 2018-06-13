---
title: '방법: 변경 내용 충돌 관리'
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 7858dc304d281dfb99755d83eec19b421f63d2ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361668"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="895bb-102">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="895bb-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="895bb-103"> 검색, 평가 및 동시성 충돌을 해결할 수 있도록 Api의 컬렉션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="895bb-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="895bb-104">In This Section</span></span>  
 [<span data-ttu-id="895bb-105">방법: 전송 충돌 검색 및 해결</span><span class="sxs-lookup"><span data-stu-id="895bb-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="895bb-106">동시성 충돌을 검색하고 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="895bb-107">방법: 동시성 예외가 Throw되는 시기 지정</span><span class="sxs-lookup"><span data-stu-id="895bb-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="895bb-108">동시성 충돌에 대해 알림을 받아야 할 경우를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="895bb-109">방법: 동시성 충돌에 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="895bb-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="895bb-110">동시성 충돌 확인 여부를 지정하기 위해 멤버에 특성을 부여하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="895bb-111">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="895bb-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="895bb-112">엔터티 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="895bb-113">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="895bb-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="895bb-114">멤버 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="895bb-115">방법: 데이터베이스 값을 보존하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="895bb-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="895bb-116">현재 값을 데이터베이스 값에 덮어쓰는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="895bb-117">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="895bb-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="895bb-118">데이터베이스 값을 덮어써 현재 값을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="895bb-119">방법: 데이터베이스 값을 병합하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="895bb-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="895bb-120">데이터베이스와 현재 값을 병합하여 충돌을 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="895bb-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="895bb-121">Related Sections</span></span>  
 [<span data-ttu-id="895bb-122">낙관적 동시성: 개요</span><span class="sxs-lookup"><span data-stu-id="895bb-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="895bb-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성에 적용하는 용어를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895bb-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
