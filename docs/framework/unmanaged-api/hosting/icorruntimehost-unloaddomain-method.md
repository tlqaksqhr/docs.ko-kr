---
title: "ICorRuntimeHost::UnloadDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.UnloadDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 067b60b9da02300e9e7316712d0058a61ab8a697
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="6a59e-102">ICorRuntimeHost::UnloadDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="6a59e-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="6a59e-103">현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a59e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a59e-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a59e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a59e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6a59e-106">[in] 형식의 포인터 <xref:System._AppDomain?displayProperty=nameWithType> 언로드되려고 할 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a59e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6a59e-107">Return Value</span></span>  
  
|<span data-ttu-id="6a59e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a59e-108">HRESULT</span></span>|<span data-ttu-id="6a59e-109">설명</span><span class="sxs-lookup"><span data-stu-id="6a59e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a59e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a59e-110">S_OK</span></span>|<span data-ttu-id="6a59e-111">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-111">The operation was successful.</span></span>|  
|<span data-ttu-id="6a59e-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6a59e-112">S_FALSE</span></span>|<span data-ttu-id="6a59e-113">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6a59e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a59e-114">E_FAIL</span></span>|<span data-ttu-id="6a59e-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6a59e-116">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6a59e-117">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a59e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a59e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a59e-119">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a59e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a59e-120">Requirements</span></span>  
 <span data-ttu-id="6a59e-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a59e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a59e-122">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a59e-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a59e-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6a59e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a59e-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6a59e-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a59e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a59e-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="6a59e-126">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a59e-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
