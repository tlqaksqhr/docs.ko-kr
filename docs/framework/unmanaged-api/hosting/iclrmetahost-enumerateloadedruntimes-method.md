---
title: "ICLRMetaHost::EnumerateLoadedRuntimes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.EnumerateLoadedRuntimes
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0724bf44eaf82b39262876ea4a44509b6c7d576
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="c3fa1-102">ICLRMetaHost::EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="c3fa1-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="c3fa1-103">올바른 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 지정된 된 프로세스에 로드 된 공용 언어 런타임 (CLR)의 각 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="c3fa1-104">이 메서드를 대체는 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3fa1-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3fa1-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3fa1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3fa1-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="c3fa1-107">[in] 로드 된 런타임을 검사 하는 프로세스의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="c3fa1-108">[out] <!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown` 열거 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 에 해당 하는 프로세스에 의해 로드 된 각 CLR 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-108">[out] An <!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown` enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3fa1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3fa1-109">Return Value</span></span>  
 <span data-ttu-id="c3fa1-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c3fa1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3fa1-111">HRESULT</span></span>|<span data-ttu-id="c3fa1-112">설명</span><span class="sxs-lookup"><span data-stu-id="c3fa1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3fa1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3fa1-113">S_OK</span></span>|<span data-ttu-id="c3fa1-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c3fa1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c3fa1-115">E_POINTER</span></span>|<span data-ttu-id="c3fa1-116">`ppEnumerator`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="c3fa1-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3fa1-117">설명</span><span class="sxs-lookup"><span data-stu-id="c3fa1-117">Remarks</span></span>  
 <span data-ttu-id="c3fa1-118">와 같은 사용 되지 않는 함수를 사용 하 여 불러온은 경우에이 메서드는 모두 로드 나열 런타임 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3fa1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3fa1-119">Requirements</span></span>  
 <span data-ttu-id="c3fa1-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fa1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3fa1-121">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c3fa1-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c3fa1-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c3fa1-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3fa1-123">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3fa1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3fa1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3fa1-124">See Also</span></span>  
 [<span data-ttu-id="c3fa1-125">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3fa1-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="c3fa1-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="c3fa1-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
