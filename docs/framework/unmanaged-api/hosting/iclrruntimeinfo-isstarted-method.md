---
title: "ICLRRuntimeInfo::IsStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsStarted
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6bcaf6e0d10bd935e7ba4a2bb79941be1af6950
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="5febf-102">ICLRRuntimeInfo::IsStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5febf-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="5febf-103">런타임이 시작 되었는지 여부를 나타냅니다 (즉, 여부는 [iclrruntimehost:: Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 이 호출 되었고, 성공).</span><span class="sxs-lookup"><span data-stu-id="5febf-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5febf-104">구문</span><span class="sxs-lookup"><span data-stu-id="5febf-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5febf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5febf-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="5febf-106">[out] `true` 이 런타임을 시작 상태가 아니면, `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="5febf-107">[out] 런타임을 시작 하는 데 사용 된 플래그를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5febf-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5febf-108">Return Value</span></span>  
 <span data-ttu-id="5febf-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5febf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5febf-110">HRESULT</span></span>|<span data-ttu-id="5febf-111">설명</span><span class="sxs-lookup"><span data-stu-id="5febf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5febf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5febf-112">S_OK</span></span>|<span data-ttu-id="5febf-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5febf-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5febf-114">E_NOTIMPL</span></span>|<span data-ttu-id="5febf-115">공용 언어 런타임 (CLR) 버전의 CLR 버전 보다 이전 인지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5febf-116">설명</span><span class="sxs-lookup"><span data-stu-id="5febf-116">Remarks</span></span>  
 <span data-ttu-id="5febf-117">이 메서드는 사용 하지 CLR 버전의 CLR 버전 보다 이전 버전의 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5febf-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5febf-118">Requirements</span></span>  
 <span data-ttu-id="5febf-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5febf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5febf-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5febf-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5febf-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5febf-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5febf-122">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5febf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5febf-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5febf-123">See Also</span></span>  
 [<span data-ttu-id="5febf-124">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5febf-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="5febf-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5febf-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5febf-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="5febf-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
