---
title: "ICorRuntimeHost::LocksHeldByLogicalThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7875d78415d06a55c11a6b42476ff806a5cadc78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="2a756-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="2a756-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="2a756-103">현재 스레드에 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a756-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="2a756-104">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a756-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a756-105">구문</span><span class="sxs-lookup"><span data-stu-id="2a756-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a756-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a756-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="2a756-107">[out] 현재 스레드에 있는 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a756-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a756-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a756-108">Requirements</span></span>  
 <span data-ttu-id="2a756-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a756-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a756-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a756-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a756-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2a756-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a756-112">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2a756-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a756-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a756-113">See Also</span></span>  
 [<span data-ttu-id="2a756-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a756-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
