---
title: "ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2b69f2f8e8273c07d277ff7460ad977fade89ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="2c46b-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="2c46b-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="2c46b-103">가비지 수집 된 메모리를 제외 하지 않고 만들어진 후 응용 프로그램 도메인에서 실행 된 모든 메모리 할당의 바이트의 총 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c46b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c46b-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c46b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c46b-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="2c46b-106">[in] 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="2c46b-107">[out] 모든 메모리 할당의 총 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c46b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2c46b-108">Return Value</span></span>  
 <span data-ttu-id="2c46b-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2c46b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c46b-110">HRESULT</span></span>|<span data-ttu-id="2c46b-111">설명</span><span class="sxs-lookup"><span data-stu-id="2c46b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c46b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c46b-112">S_OK</span></span>|<span data-ttu-id="2c46b-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2c46b-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="2c46b-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="2c46b-115">응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c46b-116">설명</span><span class="sxs-lookup"><span data-stu-id="2c46b-116">Remarks</span></span>  
 <span data-ttu-id="2c46b-117">이 메서드는 관리 되는 관리 되지 않는 버전 <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c46b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c46b-118">Requirements</span></span>  
 <span data-ttu-id="2c46b-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c46b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c46b-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2c46b-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2c46b-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2c46b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c46b-122">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c46b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c46b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c46b-123">See Also</span></span>  
 [<span data-ttu-id="2c46b-124">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c46b-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="2c46b-125">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="2c46b-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="2c46b-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c46b-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="2c46b-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="2c46b-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
