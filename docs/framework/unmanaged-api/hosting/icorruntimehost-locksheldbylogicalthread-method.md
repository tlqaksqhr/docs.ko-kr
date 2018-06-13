---
title: ICorRuntimeHost::LocksHeldByLogicalThread 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d46881b76685fd04f8bc5e3a67830e58f85cd774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436678"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="a9912-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="a9912-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="a9912-103">현재 스레드에 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9912-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="a9912-104">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9912-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9912-105">구문</span><span class="sxs-lookup"><span data-stu-id="a9912-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9912-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9912-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="a9912-107">[out] 현재 스레드에 있는 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9912-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9912-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9912-108">Requirements</span></span>  
 <span data-ttu-id="a9912-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9912-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9912-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9912-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9912-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a9912-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9912-112">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a9912-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9912-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9912-113">See Also</span></span>  
 [<span data-ttu-id="a9912-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9912-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
