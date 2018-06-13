---
title: LockClrVersion 함수
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6956d73be0380baef96d94584f007e0683331784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446092"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="2025c-102">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="2025c-102">LockClrVersion Function</span></span>
<span data-ttu-id="2025c-103">호스트가 명시적으로 CLR을 초기화 하기 전에 프로세스에서 사용할 공용 언어 런타임 (CLR)의 버전은 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="2025c-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2025c-105">구문</span><span class="sxs-lookup"><span data-stu-id="2025c-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2025c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2025c-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="2025c-107">[in] 초기화 시 CLR에서 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="2025c-108">[in] 해당 초기화 CLR 알리기 위해 호스트에 의해 호출 될 함수를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="2025c-109">[in] 호출할 함수를 CLR 알리기 위해 호스트에 의해 초기화 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2025c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2025c-110">Return Value</span></span>  
 <span data-ttu-id="2025c-111">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2025c-112">반환 코드</span><span class="sxs-lookup"><span data-stu-id="2025c-112">Return code</span></span>|<span data-ttu-id="2025c-113">설명</span><span class="sxs-lookup"><span data-stu-id="2025c-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2025c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2025c-114">S_OK</span></span>|<span data-ttu-id="2025c-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="2025c-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2025c-116">E_INVALIDARG</span></span>|<span data-ttu-id="2025c-117">인수 중 하나 이상이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2025c-118">설명</span><span class="sxs-lookup"><span data-stu-id="2025c-118">Remarks</span></span>  
 <span data-ttu-id="2025c-119">호스트에서는 `LockClrVersion` CLR을 초기화 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="2025c-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="2025c-120">`LockClrVersion` 모두 형식의 콜백을 세 개의 매개 변수 [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="2025c-121">이 형식은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="2025c-122">다음 단계는 런타임 초기화할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="2025c-123">호스트에서는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 다른 런타임 초기화 함수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="2025c-124">또는 호스트 COM 개체 활성화를 사용 하 여 런타임을 초기화할 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="2025c-125">런타임에서 호출 하 여 지정 된 함수는 `hostCallback` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="2025c-126">지정 된 함수의 `hostCallback` 다음과 같은 호출 시퀀스를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="2025c-127">에 지정 된 함수는 `pBeginHostSetup` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   <span data-ttu-id="2025c-128">`CorBindToRuntimeEx` (또는 다른 런타임 초기화 함수)입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="2025c-129">[Iclrruntimehost:: Sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="2025c-130">[Iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="2025c-131">에 지정 된 함수는 `pEndHostSetup` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="2025c-132">로부터의 모든 호출은 `pBeginHostSetup` 를 `pEndHostSetup` 단일 스레드 또는 파이버 동일한 논리 스택에서 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="2025c-133">이 스레드는 스레드가 서로 다를 수 `hostCallback` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2025c-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2025c-134">Requirements</span></span>  
 <span data-ttu-id="2025c-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2025c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2025c-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2025c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2025c-137">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2025c-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2025c-138">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2025c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2025c-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2025c-139">See Also</span></span>  
 [<span data-ttu-id="2025c-140">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2025c-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
