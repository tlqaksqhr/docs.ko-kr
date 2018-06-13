---
title: IGCThreadControl::SuspensionEnding 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0986645a8ce4076c27f39f2ae8004ef20bb4bdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437754"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="baed0-102">IGCThreadControl::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="baed0-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="baed0-103">런타임 스레드를 다시 시작 가비지 컬렉션이 나 다른 일시 중단 작업 후 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="baed0-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baed0-104">구문</span><span class="sxs-lookup"><span data-stu-id="baed0-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="baed0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baed0-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="baed0-106">[in] 가비지 수집을 수행한 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="baed0-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baed0-107">설명</span><span class="sxs-lookup"><span data-stu-id="baed0-107">Remarks</span></span>  
 <span data-ttu-id="baed0-108">모든 스레드는 동안 다시 예약 하지 않습니다는 `SuspensionEnding` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed0-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baed0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="baed0-109">Requirements</span></span>  
 <span data-ttu-id="baed0-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="baed0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baed0-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="baed0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baed0-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="baed0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baed0-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baed0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baed0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baed0-114">See Also</span></span>  
 [<span data-ttu-id="baed0-115">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baed0-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
