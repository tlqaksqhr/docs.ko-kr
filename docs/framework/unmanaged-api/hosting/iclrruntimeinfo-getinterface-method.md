---
title: "ICLRRuntimeInfo::GetInterface 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c5150a10a813da85fc035c7bfa43a7647fac308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="d0b0c-102">ICLRRuntimeInfo::GetInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="d0b0c-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="d0b0c-103">현재 프로세스에 CLR을 로드 하 고 런타임 인터페이스 포인터와 같은 반환 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), 및 [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="d0b0c-104">이 메서드를 모두 대체는 `CorBindTo`*의 함수는 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 섹션.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-104">This method supersedes all the `CorBindTo`* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b0c-105">구문</span><span class="sxs-lookup"><span data-stu-id="d0b0c-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0b0c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0b0c-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="d0b0c-107">[in] Coclass에 대 한 CLSID 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="d0b0c-108">[in] 요청 된 IID `rclsid` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="d0b0c-109">[out] 쿼리 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0b0c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="d0b0c-110">Return Value</span></span>  
 <span data-ttu-id="d0b0c-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d0b0c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0b0c-112">HRESULT</span></span>|<span data-ttu-id="d0b0c-113">설명</span><span class="sxs-lookup"><span data-stu-id="d0b0c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0b0c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0b0c-114">S_OK</span></span>|<span data-ttu-id="d0b0c-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="d0b0c-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d0b0c-116">E_POINTER</span></span>|<span data-ttu-id="d0b0c-117">`ppUnk`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="d0b0c-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="d0b0c-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0b0c-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d0b0c-119">요청을 처리할 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="d0b0c-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="d0b0c-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="d0b0c-121">각기 다른 런타임 레거시 CLR 버전 2 정품 인증 정책에 이미 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0b0c-122">설명</span><span class="sxs-lookup"><span data-stu-id="d0b0c-122">Remarks</span></span>  
 <span data-ttu-id="d0b0c-123">이 메서드를 사용 하면 CLR 로드 되지만 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="d0b0c-124">다음 표에서 지원 되는 조합을 `rclsid` 및 `riid`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="d0b0c-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d0b0c-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="d0b0c-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d0b0c-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="d0b0c-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="d0b0c-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="d0b0c-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d0b0c-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="d0b0c-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d0b0c-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="d0b0c-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d0b0c-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="d0b0c-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d0b0c-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="d0b0c-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d0b0c-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="d0b0c-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="d0b0c-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="d0b0c-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="d0b0c-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="d0b0c-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="d0b0c-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="d0b0c-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="d0b0c-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="d0b0c-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d0b0c-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="d0b0c-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d0b0c-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0b0c-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0b0c-139">Requirements</span></span>  
 <span data-ttu-id="d0b0c-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b0c-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b0c-141">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d0b0c-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d0b0c-142">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d0b0c-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0b0c-143">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b0c-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b0c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0b0c-144">See Also</span></span>  
 [<span data-ttu-id="d0b0c-145">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b0c-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="d0b0c-146">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b0c-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d0b0c-147">호스팅</span><span class="sxs-lookup"><span data-stu-id="d0b0c-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
