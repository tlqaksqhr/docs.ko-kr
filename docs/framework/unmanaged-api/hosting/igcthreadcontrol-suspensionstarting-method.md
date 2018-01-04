---
title: "IGCThreadControl::SuspensionStarting 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6da39ec675cafcd51a5d748d4cbe8f9fd376eff8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="7c6c3-102">IGCThreadControl::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="7c6c3-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="7c6c3-103">가비지 수집 스레드 일시 중단 또는 기타 일시 중단 작업 런타임이 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7c6c3-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c6c3-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="7c6c3-105">설명</span><span class="sxs-lookup"><span data-stu-id="7c6c3-105">Remarks</span></span>  
 <span data-ttu-id="7c6c3-106">모든 스레드는 동안 다시 예약 하지 않습니다는 `SuspensionStarting` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6c3-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6c3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c6c3-107">Requirements</span></span>  
 <span data-ttu-id="7c6c3-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6c3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6c3-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c6c3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c6c3-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7c6c3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c6c3-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6c3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c6c3-112">See Also</span></span>  
 [<span data-ttu-id="7c6c3-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c6c3-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
