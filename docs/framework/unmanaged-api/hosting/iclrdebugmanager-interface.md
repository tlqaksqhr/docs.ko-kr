---
title: "ICLRDebugManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e712f22156e96cfc58e9c1a835077ba21ecd184
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="c737e-102">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c737e-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="c737e-103">호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c737e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-104">Methods</span></span>  
  
|<span data-ttu-id="c737e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-105">Method</span></span>|<span data-ttu-id="c737e-106">설명</span><span class="sxs-lookup"><span data-stu-id="c737e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c737e-107">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="c737e-108">식별자 및 이름을 사용 하 여 작업을 연결 하는 호스트와 디버거 사이 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c737e-109">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="c737e-110">작업 목록 및 식별자 및 이름을 사이의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c737e-111">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="c737e-112">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="c737e-113">IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="c737e-114">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="c737e-115">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="c737e-116">연결 목록이 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 라는 이름과 식별자를 사용 하 여 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c737e-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c737e-117">SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="c737e-118">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="c737e-119">SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="c737e-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="c737e-120">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="c737e-121">정책을 호출 스택의 줄 번호와 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c737e-122">설명</span><span class="sxs-lookup"><span data-stu-id="c737e-122">Remarks</span></span>  
 <span data-ttu-id="c737e-123">디버깅 시나리오에서는 호스트 자체 프로그래밍 논리에 따라 작업을 그룹화 할 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="c737e-124">예를 들어 그룹화 하는 프로세스에서 실행 중인 모든 작업을 보는 대신 개발자의 Api에 필요한 작업에만 표시 되도록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="c737e-125">`ICLRDebugManager`이러한 그룹화를 구현 하는 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c737e-126">세 가지 `ICLRDebugManager` 메서드 `BeginConnection`, `SetConnectionTasks` 및 `EndConnection`, 서로 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="c737e-127">예상 대로 작동 하는 지정 된 순서로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="c737e-128">그룹화 식별자 및 호스트 그룹화에 할당 하는 공용 언어 런타임 (CLR)에 대 한 아무런 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="c737e-129">CLR는 단순히 디버거에 따라 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c737e-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c737e-130">Requirements</span></span>  
 <span data-ttu-id="c737e-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c737e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c737e-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c737e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c737e-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c737e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c737e-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c737e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c737e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c737e-135">See Also</span></span>  
 [<span data-ttu-id="c737e-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c737e-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
