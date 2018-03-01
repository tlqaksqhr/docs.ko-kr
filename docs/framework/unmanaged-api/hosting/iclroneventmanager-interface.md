---
title: "ICLROnEventManager 인터페이스"
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
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02a19a3daf72cdfa493b09fa984fe7b50865ed30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="19c79-102">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c79-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="19c79-103">등록 하 고 공용 언어 런타임 (CLR) 이벤트에 대 한 콜백을 등록을 취소 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c79-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19c79-104">메서드</span><span class="sxs-lookup"><span data-stu-id="19c79-104">Methods</span></span>  
  
|<span data-ttu-id="19c79-105">메서드</span><span class="sxs-lookup"><span data-stu-id="19c79-105">Method</span></span>|<span data-ttu-id="19c79-106">설명</span><span class="sxs-lookup"><span data-stu-id="19c79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19c79-107">RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="19c79-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="19c79-108">지정된 된 이벤트에 대 한 콜백 포인터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="19c79-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="19c79-109">UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="19c79-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="19c79-110">지정된 된 이벤트에 대 한 이전에 등록 된 콜백 포인터를 등록 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="19c79-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c79-111">설명</span><span class="sxs-lookup"><span data-stu-id="19c79-111">Remarks</span></span>  
 <span data-ttu-id="19c79-112">등록 하 고 이벤트 콜백을 등록 취소, 호스트에 대 한 참조를 가져옵니다 `ICLROnEventManager` 호출 하 여는 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="19c79-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c79-113">설명 하는 이벤트 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 서로 다른 스레드의 신호를 보내는 언로드 또는 CLR의 비활성화 하 고 두 번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c79-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c79-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19c79-114">Requirements</span></span>  
 <span data-ttu-id="19c79-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19c79-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c79-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19c79-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19c79-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="19c79-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19c79-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c79-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19c79-119">See Also</span></span>  
 [<span data-ttu-id="19c79-120">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="19c79-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="19c79-121">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c79-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="19c79-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c79-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="19c79-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c79-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
