---
title: IGCThreadControl::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f4b767fe7134833ee2e404be30bb51bf1385ec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437039"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="2a1ee-102">IGCThreadControl::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="2a1ee-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="2a1ee-103">호출 하는 스레드를 위해 차단 가비지 컬렉션이 나 다른 일시 중단 작업을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2a1ee-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a1ee-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a1ee-105">설명</span><span class="sxs-lookup"><span data-stu-id="2a1ee-105">Remarks</span></span>  
 <span data-ttu-id="2a1ee-106">호스트 내에서 선택할 수 있습니다는 `ThreadIsBlockingForSuspension` 콜백 스레드 일정을 변경 하려면 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="2a1ee-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a1ee-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a1ee-107">Requirements</span></span>  
 <span data-ttu-id="2a1ee-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1ee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a1ee-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a1ee-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a1ee-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2a1ee-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a1ee-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a1ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1ee-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a1ee-112">See Also</span></span>  
 [<span data-ttu-id="2a1ee-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a1ee-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
