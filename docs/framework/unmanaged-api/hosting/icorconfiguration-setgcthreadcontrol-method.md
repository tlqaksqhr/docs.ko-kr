---
title: "ICorConfiguration::SetGCThreadControl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b6b28b67f924df4d7f587d0364bce2a853f60b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="7d857-102">ICorConfiguration::SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="7d857-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="7d857-103">가비지 컬렉션에 대 한 차단 될 런타임 외 작업에 대 한 스레드를 예약 하기 위한 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d857-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d857-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d857-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d857-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d857-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="7d857-106">[in] 에 대 한 포인터는 [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) 개체 런타임 외 작업에 대 한 스레드 일시 중단 하는 방법에 대 한 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7d857-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d857-107">설명</span><span class="sxs-lookup"><span data-stu-id="7d857-107">Remarks</span></span>  
 <span data-ttu-id="7d857-108">호스트 내에서 선택할 수 있습니다는 [igcthreadcontrol:: Threadisblockingforsuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) 콜백 스레드 일정을 변경 하려면 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="7d857-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d857-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d857-109">Requirements</span></span>  
 <span data-ttu-id="7d857-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d857-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d857-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d857-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d857-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7d857-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d857-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d857-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d857-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d857-114">See Also</span></span>  
 [<span data-ttu-id="7d857-115">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d857-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
