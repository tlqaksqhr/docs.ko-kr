---
title: "CorBindToRuntimeByCfg 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeByCfg
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeByCfg
helpviewer_keywords: CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dccd777ef20f68d091cfdd7939c57a1f8d42ad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="411b5-102">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="411b5-103">XML 파일에서 읽을 수 있는 버전 정보를 사용 하 여 공용 언어 런타임 (CLR) 프로세스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="411b5-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="411b5-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="411b5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="411b5-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="411b5-107">[in] 에 대 한 포인터는 `IStream` XML 파일을 읽는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="411b5-108">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-108">[in] Reserved for future use.</span></span> <span data-ttu-id="411b5-109">값으로 0 (영)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="411b5-110">[in] 값은 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) CLR의 시작 동작을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="411b5-111">[in] `CLSID` 중 하나를 구현 하는 coclass의는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="411b5-112">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="411b5-113">[in] `IID` 의 `ICorRuntimeHost` 또는 `ICLRRuntimeHost` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="411b5-114">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="411b5-115">[out] 반환 되는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="411b5-116">설명</span><span class="sxs-lookup"><span data-stu-id="411b5-116">Remarks</span></span>  
 <span data-ttu-id="411b5-117">XML 파일의 형식은 표준 응용 프로그램 구성 파일에 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="411b5-118">XML 파일에 대 한 자세한 내용은 참조 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="411b5-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="411b5-119">Requirements</span></span>  
 <span data-ttu-id="411b5-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="411b5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411b5-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="411b5-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="411b5-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="411b5-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="411b5-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411b5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411b5-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="411b5-124">See Also</span></span>  
 [<span data-ttu-id="411b5-125">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="411b5-126">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="411b5-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="411b5-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="411b5-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="411b5-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="411b5-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="411b5-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
