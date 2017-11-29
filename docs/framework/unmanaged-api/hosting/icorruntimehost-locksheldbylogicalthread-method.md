---
title: "ICorRuntimeHost::LocksHeldByLogicalThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.LocksHeldByLogicalThread
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fa031e4842d81f7ddec3e7eeb64c9d7b02e566
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="6e44d-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="6e44d-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="6e44d-103">현재 스레드에 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e44d-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="6e44d-104">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e44d-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e44d-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e44d-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e44d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e44d-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="6e44d-107">[out] 현재 스레드에 있는 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e44d-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e44d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e44d-108">Requirements</span></span>  
 <span data-ttu-id="6e44d-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e44d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e44d-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e44d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e44d-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6e44d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e44d-112">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6e44d-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e44d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e44d-113">See Also</span></span>  
 [<span data-ttu-id="6e44d-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e44d-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
