---
title: "IHostSecurityManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="94abe-102">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94abe-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="94abe-103">에 대 한 액세스 및 현재 실행 중인 스레드의 보안 컨텍스트를 제어할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94abe-104">메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-104">Methods</span></span>  
  
|<span data-ttu-id="94abe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-105">Method</span></span>|<span data-ttu-id="94abe-106">설명</span><span class="sxs-lookup"><span data-stu-id="94abe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94abe-107">GetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="94abe-108">요청 된 가져옵니다 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 호스트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="94abe-109">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="94abe-110">요청이 현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="94abe-111">OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="94abe-112">현재 스레드와 연결 된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="94abe-113">RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="94abe-114">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="94abe-115">SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="94abe-116">현재 실행 중인 스레드에 대 한 보안 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="94abe-117">SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="94abe-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="94abe-118">현재 실행 중인 스레드에 대 한 핸들을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94abe-119">설명</span><span class="sxs-lookup"><span data-stu-id="94abe-119">Remarks</span></span>  
 <span data-ttu-id="94abe-120">호스트는 공용 언어 런타임 (CLR) 및 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="94abe-121">전체 보안 되도록 할 수도 있습니다 컨텍스트 정보는 비동기 작업이 나 코드 액세스를 제한 하는 코드 포인트 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="94abe-122">`IHostSecurityContext`CLR에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="94abe-123">CLR에서 관리 되는 스레드 컨텍스트를 내부적으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="94abe-124">프로세스 관련 쿼리하여 `IHostSecurityManager` 다음과 같은 경우:</span><span class="sxs-lookup"><span data-stu-id="94abe-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="94abe-125">종료자 스레드 종료 자가 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="94abe-126">클래스 및 모듈 생성자 실행 중</span><span class="sxs-lookup"><span data-stu-id="94abe-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="94abe-127">에 대 한 호출에서 작업자 스레드에서 비동기 시점에서 [ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="94abe-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="94abe-128">에 I/O 완료 포트 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94abe-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94abe-129">Requirements</span></span>  
 <span data-ttu-id="94abe-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94abe-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94abe-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94abe-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94abe-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="94abe-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94abe-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94abe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94abe-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94abe-134">See Also</span></span>  
 [<span data-ttu-id="94abe-135">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94abe-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="94abe-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94abe-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
