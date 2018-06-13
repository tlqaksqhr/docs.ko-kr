---
title: ICLRRuntimeInfo::GetInterface 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4924f373270a30b593e27c334d383963fc4a7cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435853"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="f5df3-102">ICLRRuntimeInfo::GetInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="f5df3-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="f5df3-103">현재 프로세스에 CLR을 로드 하 고 런타임 인터페이스 포인터와 같은 반환 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), 및 [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="f5df3-104">이 메서드를 모두 대체는 `CorBindTo`\*의 함수는 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 섹션.</span><span class="sxs-lookup"><span data-stu-id="f5df3-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5df3-105">구문</span><span class="sxs-lookup"><span data-stu-id="f5df3-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5df3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5df3-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="f5df3-107">[in] Coclass에 대 한 CLSID 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="f5df3-108">[in] 요청 된 IID `rclsid` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="f5df3-109">[out] 쿼리 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5df3-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="f5df3-110">Return Value</span></span>  
 <span data-ttu-id="f5df3-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f5df3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5df3-112">HRESULT</span></span>|<span data-ttu-id="f5df3-113">설명</span><span class="sxs-lookup"><span data-stu-id="f5df3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5df3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5df3-114">S_OK</span></span>|<span data-ttu-id="f5df3-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="f5df3-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f5df3-116">E_POINTER</span></span>|<span data-ttu-id="f5df3-117">`ppUnk`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="f5df3-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="f5df3-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f5df3-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f5df3-119">요청을 처리할 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="f5df3-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="f5df3-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="f5df3-121">각기 다른 런타임 레거시 CLR 버전 2 정품 인증 정책에 이미 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5df3-122">설명</span><span class="sxs-lookup"><span data-stu-id="f5df3-122">Remarks</span></span>  
 <span data-ttu-id="f5df3-123">이 메서드를 사용 하면 CLR 로드 되지만 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="f5df3-124">다음 표에서 지원 되는 조합을 `rclsid` 및 `riid`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="f5df3-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="f5df3-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="f5df3-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f5df3-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="f5df3-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="f5df3-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="f5df3-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f5df3-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="f5df3-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f5df3-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="f5df3-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f5df3-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="f5df3-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f5df3-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="f5df3-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f5df3-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="f5df3-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="f5df3-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="f5df3-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="f5df3-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="f5df3-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="f5df3-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="f5df3-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f5df3-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="f5df3-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f5df3-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="f5df3-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f5df3-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5df3-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5df3-139">Requirements</span></span>  
 <span data-ttu-id="f5df3-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5df3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5df3-141">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f5df3-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f5df3-142">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f5df3-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5df3-143">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5df3-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5df3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5df3-144">See Also</span></span>  
 [<span data-ttu-id="f5df3-145">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5df3-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="f5df3-146">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5df3-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="f5df3-147">호스팅</span><span class="sxs-lookup"><span data-stu-id="f5df3-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
