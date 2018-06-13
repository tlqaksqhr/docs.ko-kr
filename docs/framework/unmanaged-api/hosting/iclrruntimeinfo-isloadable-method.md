---
title: ICLRRuntimeInfo::IsLoadable 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e60c3b06453e0f447249bddf5d4da5c240576577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432962"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="ff83e-102">ICLRRuntimeInfo::IsLoadable 메서드</span><span class="sxs-lookup"><span data-stu-id="ff83e-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="ff83e-103">이 인터페이스와 연결 된 런타임을 고려 하는 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다. 이미 프로세스에 로드 될 수 있는 다른 런타임과 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff83e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff83e-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff83e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff83e-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="ff83e-106">[out] `true` 현재 프로세스에 로드 되 고, 그렇지 않으면이 런타임 수 있으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff83e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff83e-107">Return Value</span></span>  
 <span data-ttu-id="ff83e-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ff83e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff83e-109">HRESULT</span></span>|<span data-ttu-id="ff83e-110">설명</span><span class="sxs-lookup"><span data-stu-id="ff83e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff83e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff83e-111">S_OK</span></span>|<span data-ttu-id="ff83e-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ff83e-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ff83e-113">E_POINTER</span></span>|<span data-ttu-id="ff83e-114">`pbLoadable`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="ff83e-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff83e-115">설명</span><span class="sxs-lookup"><span data-stu-id="ff83e-115">Remarks</span></span>  
 <span data-ttu-id="ff83e-116">다른 런타임 프로세스에 이미 로드 하 고이 인터페이스와 연결 된 런타임 종속 프로세스-병렬 실행을 위해 로드할 수 있습니다 `pbLoadable` 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="ff83e-117">두 개의 런타임-함께 in-process로 실행할 수 없는 경우 `pbLoadable` 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="ff83e-118">예를 들어, 공용 언어 런타임 (CLR) 버전 4 나란히 CLR 버전 2.0과 같은 프로세스에서 또는 CLR 버전 1.1 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="ff83e-119">그러나 CLR 버전 1.1과 CLR 버전 2.0-병렬 프로세스를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="ff83e-120">경우에 런타임이 프로세스에 로드 됩니다,이 메서드는 항상 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff83e-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff83e-121">Requirements</span></span>  
 <span data-ttu-id="ff83e-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff83e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff83e-123">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ff83e-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ff83e-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ff83e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff83e-125">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff83e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff83e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff83e-126">See Also</span></span>  
 [<span data-ttu-id="ff83e-127">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff83e-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="ff83e-128">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff83e-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ff83e-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="ff83e-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
