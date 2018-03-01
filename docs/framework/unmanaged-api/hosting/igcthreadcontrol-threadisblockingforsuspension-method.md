---
title: "IGCThreadControl::ThreadIsBlockingForSuspension 메서드"
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
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0cb7cfbab18334f1892c24225311160179920f81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="3a1ea-102">IGCThreadControl::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="3a1ea-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="3a1ea-103">호출 하는 스레드를 위해 차단 가비지 컬렉션이 나 다른 일시 중단 작업을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3a1ea-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a1ea-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a1ea-105">설명</span><span class="sxs-lookup"><span data-stu-id="3a1ea-105">Remarks</span></span>  
 <span data-ttu-id="3a1ea-106">호스트 내에서 선택할 수 있습니다는 `ThreadIsBlockingForSuspension` 콜백 스레드 일정을 변경 하려면 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1ea-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1ea-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a1ea-107">Requirements</span></span>  
 <span data-ttu-id="3a1ea-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a1ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1ea-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a1ea-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a1ea-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3a1ea-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a1ea-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1ea-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a1ea-112">See Also</span></span>  
 [<span data-ttu-id="3a1ea-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a1ea-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
