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
ms.workload: dotnet
ms.openlocfilehash: f1d2bb2ecc4ae7edb4edbaa3ff36650c70c82daf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="243eb-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 메서드</span><span class="sxs-lookup"><span data-stu-id="243eb-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="243eb-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="243eb-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="243eb-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="243eb-105">Return Value</span></span>  
  
|<span data-ttu-id="243eb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="243eb-106">HRESULT</span></span>|<span data-ttu-id="243eb-107">설명</span><span class="sxs-lookup"><span data-stu-id="243eb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="243eb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="243eb-108">S_OK</span></span>|<span data-ttu-id="243eb-109">`SetEagerSerializeGrantSets`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="243eb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="243eb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="243eb-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="243eb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="243eb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="243eb-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-113">The call timed out.</span></span>|  
|<span data-ttu-id="243eb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="243eb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="243eb-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="243eb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="243eb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="243eb-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="243eb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="243eb-118">E_FAIL</span></span>|<span data-ttu-id="243eb-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="243eb-120">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="243eb-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="243eb-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="243eb-122">Requirements</span></span>  
 <span data-ttu-id="243eb-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="243eb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="243eb-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="243eb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="243eb-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="243eb-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="243eb-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="243eb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243eb-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="243eb-127">See Also</span></span>  
 [<span data-ttu-id="243eb-128">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="243eb-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="243eb-129">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="243eb-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
