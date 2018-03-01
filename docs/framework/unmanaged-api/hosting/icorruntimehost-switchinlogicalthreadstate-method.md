---
title: "ICorRuntimeHost::SwitchInLogicalThreadState 메서드"
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
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 065a2347be2587265471d707988e90a01482c5a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="f4701-102">ICorRuntimeHost::SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="f4701-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="f4701-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4701-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4701-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4701-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4701-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4701-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="f4701-106">[in] 사용 하려면 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="f4701-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4701-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4701-107">Requirements</span></span>  
 <span data-ttu-id="f4701-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4701-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4701-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4701-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4701-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f4701-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4701-111">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="f4701-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4701-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4701-112">See Also</span></span>  
 [<span data-ttu-id="f4701-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4701-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
