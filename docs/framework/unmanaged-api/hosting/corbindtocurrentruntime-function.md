---
title: "CorBindToCurrentRuntime 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: HeaderDef
f1_keywords: CorBindToCurrentRuntime
helpviewer_keywords: CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fed8829f8f14833724d1770273ff905d6f5eabf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="51fd3-102">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="51fd3-103">XML 파일에 저장 된 버전 정보를 사용 하 여 공용 언어 런타임 (CLR) 프로세스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="51fd3-104">XML 파일의 형식은 표준 응용 프로그램 구성 파일에 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="51fd3-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51fd3-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="51fd3-106">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="51fd3-107">참조 [공용 언어 런타임 프로세스에 로드](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)합니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51fd3-108">구문</span><span class="sxs-lookup"><span data-stu-id="51fd3-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51fd3-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51fd3-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="51fd3-110">[in] 로드 하기 위해 CLR의 버전을 지정 하는 응용 프로그램 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="51fd3-111">파일 이름이 정규화 된 디렉터리가 아닙니다 전화 통화를 걸기 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="51fd3-112">로드할 런타임 버전을 version 특성에 의해 설명 된 [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="51fd3-113">버전이 지정 되지, 아니면는 `<requiredRuntime>` 요소를 찾을 수 없습니다, 최신 버전의 컴퓨터에 설치 된 CLR 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="51fd3-114">[in] `CLSID` 중 하나를 구현 하는 coclass의는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="51fd3-115">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="51fd3-116">[in] `IID` 요청 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="51fd3-117">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="51fd3-118">[out] 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51fd3-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51fd3-119">Requirements</span></span>  
 <span data-ttu-id="51fd3-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51fd3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51fd3-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51fd3-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51fd3-122">**Library:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51fd3-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51fd3-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fd3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fd3-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51fd3-124">See Also</span></span>  
 [<span data-ttu-id="51fd3-125">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="51fd3-126">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="51fd3-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="51fd3-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="51fd3-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51fd3-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="51fd3-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="51fd3-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
