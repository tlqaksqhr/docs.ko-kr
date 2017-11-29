---
title: "ICLRHostProtectionManager::SetEagerSerializeGrantSets 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9b1e314f7af6edf3d8db00780105dff95868a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="8d19b-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 메서드</span><span class="sxs-lookup"><span data-stu-id="8d19b-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="8d19b-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d19b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d19b-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d19b-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="8d19b-105">Return Value</span></span>  
  
|<span data-ttu-id="8d19b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d19b-106">HRESULT</span></span>|<span data-ttu-id="8d19b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8d19b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d19b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d19b-108">S_OK</span></span>|<span data-ttu-id="8d19b-109">`SetEagerSerializeGrantSets`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="8d19b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d19b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d19b-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d19b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d19b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d19b-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-113">The call timed out.</span></span>|  
|<span data-ttu-id="8d19b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d19b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d19b-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d19b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d19b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d19b-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d19b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d19b-118">E_FAIL</span></span>|<span data-ttu-id="8d19b-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d19b-120">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d19b-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d19b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d19b-122">Requirements</span></span>  
 <span data-ttu-id="8d19b-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d19b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d19b-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d19b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d19b-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8d19b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d19b-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d19b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d19b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d19b-127">See Also</span></span>  
 [<span data-ttu-id="8d19b-128">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d19b-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8d19b-129">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d19b-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
