---
title: "IHostSecurityContext 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d3c616ced761b696f50e9207e6fad312f06c31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="b01ff-102">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01ff-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="b01ff-103">공용 언어 런타임을 (CLR) 호스트에서 구현 하는 보안 컨텍스트 정보를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b01ff-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b01ff-104">Methods</span></span>  
  
|<span data-ttu-id="b01ff-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b01ff-105">Method</span></span>|<span data-ttu-id="b01ff-106">설명</span><span class="sxs-lookup"><span data-stu-id="b01ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b01ff-107">Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="b01ff-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="b01ff-108">복제본을 가져옵니다는 `IHostSecurityContext` 에 대 한 호출에서 반환 된 인스턴스 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b01ff-109">설명</span><span class="sxs-lookup"><span data-stu-id="b01ff-109">Remarks</span></span>  
 <span data-ttu-id="b01ff-110">호스트는 CLR 및 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="b01ff-111">전체 보안 되도록 할 수도 있습니다 컨텍스트 정보는 비동기 작업이 나 코드 액세스를 제한 하는 코드 포인트 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="b01ff-112">`IHostSecurityContext`런타임에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="b01ff-113">런타임에서 사용 하 여이 정보를 캡처합니다 `Capture`를 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성자로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b01ff-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b01ff-114">Requirements</span></span>  
 <span data-ttu-id="b01ff-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b01ff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b01ff-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b01ff-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b01ff-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b01ff-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b01ff-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b01ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01ff-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b01ff-119">See Also</span></span>  
 [<span data-ttu-id="b01ff-120">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01ff-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="b01ff-121">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01ff-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="b01ff-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01ff-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
