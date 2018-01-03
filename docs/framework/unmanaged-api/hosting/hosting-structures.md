---
title: "호스팅 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e59353272856525b7d72f322694d15a42ab7b32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-structures"></a><span data-ttu-id="49ee3-102">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-102">Hosting Structures</span></span>
<span data-ttu-id="49ee3-103">이 섹션에서는 호스팅 API에 사용 되는 관리 되지 않는 구조체를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49ee3-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="49ee3-104">In This Section</span></span>  
 [<span data-ttu-id="49ee3-105">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="49ee3-106">참조 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="49ee3-107">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="49ee3-108">이벤트와 연결 된 현재 예외에 대 한 이벤트 및 매개 변수 형식 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="49ee3-109">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="49ee3-110">공용 언어 런타임 (CLR)의 가비지 수집 메커니즘에 대 한 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="49ee3-111">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="49ee3-112">가비지 수집에 관련 된 스레드 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="49ee3-113">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="49ee3-114">오류 보고에 사용자 지정 덤프에 추가할 항목에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="49ee3-115">MDAInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="49ee3-116">에 대 한 세부 정보를 제공는 `Event_MDAFired` 관리 디버깅 도우미 (MDA) 만들기를 트리거하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="49ee3-117">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="49ee3-118">참조 된 모듈 및 포함 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="49ee3-119">StackOverflowInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="49ee3-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="49ee3-120">오버플로로 인해 throw 된 예외에 발생 한 오버플로 종류 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ee3-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="49ee3-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="49ee3-121">Related Sections</span></span>  
 [<span data-ttu-id="49ee3-122">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="49ee3-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="49ee3-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49ee3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="49ee3-124">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="49ee3-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="49ee3-125">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="49ee3-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
