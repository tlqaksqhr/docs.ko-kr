---
title: IHostSecurityContext 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c2500f013584ef4722ceaaaee91d5db54991639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439301"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="8b06d-102">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b06d-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="8b06d-103">공용 언어 런타임을 (CLR) 호스트에서 구현 하는 보안 컨텍스트 정보를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b06d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8b06d-104">Methods</span></span>  
  
|<span data-ttu-id="8b06d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8b06d-105">Method</span></span>|<span data-ttu-id="8b06d-106">설명</span><span class="sxs-lookup"><span data-stu-id="8b06d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b06d-107">Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="8b06d-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="8b06d-108">복제본을 가져옵니다는 `IHostSecurityContext` 에 대 한 호출에서 반환 된 인스턴스 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b06d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b06d-109">Remarks</span></span>  
 <span data-ttu-id="8b06d-110">호스트는 CLR 및 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="8b06d-111">전체 보안 되도록 할 수도 있습니다 컨텍스트 정보는 비동기 작업이 나 코드 액세스를 제한 하는 코드 포인트 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="8b06d-112">`IHostSecurityContext` 런타임에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="8b06d-113">런타임에서 사용 하 여이 정보를 캡처합니다 `Capture`를 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성자로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b06d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b06d-114">Requirements</span></span>  
 <span data-ttu-id="8b06d-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b06d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b06d-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b06d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b06d-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8b06d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b06d-118">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b06d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b06d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b06d-119">See Also</span></span>  
 [<span data-ttu-id="8b06d-120">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b06d-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="8b06d-121">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b06d-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="8b06d-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b06d-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
