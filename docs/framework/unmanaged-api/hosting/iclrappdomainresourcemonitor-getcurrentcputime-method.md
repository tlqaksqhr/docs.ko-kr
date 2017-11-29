---
title: "ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2483165de54cd5ec76abad9d8472e0deef28f149
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="a5d06-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드</span><span class="sxs-lookup"><span data-stu-id="a5d06-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="a5d06-103">응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d06-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5d06-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5d06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5d06-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="a5d06-106">[in] 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="a5d06-107">[out] 응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="a5d06-108">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5d06-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a5d06-109">Return Value</span></span>  
  
|<span data-ttu-id="a5d06-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5d06-110">HRESULT</span></span>|<span data-ttu-id="a5d06-111">설명</span><span class="sxs-lookup"><span data-stu-id="a5d06-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5d06-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5d06-112">S_OK</span></span>|<span data-ttu-id="a5d06-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a5d06-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="a5d06-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="a5d06-115">응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="a5d06-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5d06-116">E_FAIL</span></span>|<span data-ttu-id="a5d06-117">응용 프로그램 도메인 리소스 모니터링은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="a5d06-118">또는</span><span class="sxs-lookup"><span data-stu-id="a5d06-118">-or-</span></span><br /><br /> <span data-ttu-id="a5d06-119">기타 모든 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5d06-120">설명</span><span class="sxs-lookup"><span data-stu-id="a5d06-120">Remarks</span></span>  
 <span data-ttu-id="a5d06-121">이 메서드는 관리 되는 관리 되지 않는 버전 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5d06-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5d06-122">Requirements</span></span>  
 <span data-ttu-id="a5d06-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d06-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d06-124">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a5d06-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5d06-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a5d06-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5d06-126">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d06-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d06-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5d06-127">See Also</span></span>  
 [<span data-ttu-id="a5d06-128">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5d06-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="a5d06-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5d06-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a5d06-130">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="a5d06-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="a5d06-131">호스팅</span><span class="sxs-lookup"><span data-stu-id="a5d06-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
