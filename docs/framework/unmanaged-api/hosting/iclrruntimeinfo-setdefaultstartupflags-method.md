---
title: "ICLRRuntimeInfo::SetDefaultStartupFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="65025-102">ICLRRuntimeInfo::SetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="65025-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="65025-103">런타임을 시작 하는 호스트 구성 파일 및 시작 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65025-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="65025-104">이 메서드를 사용 하는 대체는 `startupFlags` 에서 매개 변수는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="65025-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65025-105">구문</span><span class="sxs-lookup"><span data-stu-id="65025-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65025-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65025-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="65025-107">[in] 호스트 시작 플래그 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="65025-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="65025-108">와 동일한 플래그를 사용 하 여는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 및 [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="65025-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="65025-109">[in] 설정 하려면 호스트 구성 파일의 디렉터리 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="65025-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65025-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="65025-110">Return Value</span></span>  
 <span data-ttu-id="65025-111">이 메서드는 다음과 같은 특정 HRESULT를 반환 합니다. 메서드 오류를 나타내는 HRESULT 오류도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65025-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65025-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65025-112">HRESULT</span></span>|<span data-ttu-id="65025-113">설명</span><span class="sxs-lookup"><span data-stu-id="65025-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65025-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="65025-114">S_OK</span></span>|<span data-ttu-id="65025-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65025-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65025-116">설명</span><span class="sxs-lookup"><span data-stu-id="65025-116">Remarks</span></span>  
 <span data-ttu-id="65025-117">다중 스레드는 호스트는이 메서드의 호출을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65025-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="65025-118">그렇지 않으면 스레드 A 호출 수는 `SetStartupFlags` 메서드 스레드 B에 대 한 호출을 완료 한 후 `SetStartupFlags` 스레드 B는 런타임을 시작 되기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="65025-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65025-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65025-119">Requirements</span></span>  
 <span data-ttu-id="65025-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65025-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65025-121">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="65025-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="65025-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="65025-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65025-123">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65025-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65025-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65025-124">See Also</span></span>  
 [<span data-ttu-id="65025-125">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65025-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="65025-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65025-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="65025-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="65025-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
