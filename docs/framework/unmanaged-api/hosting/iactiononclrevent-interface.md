---
title: "IActionOnCLREvent 인터페이스"
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
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b51784f07a90faa9eeb29c18a784d4fbc2c4654
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="eed9a-102">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eed9a-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="eed9a-103">제공 된 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 이벤트에 대 한 호출을 사용 하 여 등록 된 콜백을 수행 하는 메서드는 [iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 메서드 합니다.</span><span class="sxs-lookup"><span data-stu-id="eed9a-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eed9a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="eed9a-104">Methods</span></span>  
  
|<span data-ttu-id="eed9a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eed9a-105">Method</span></span>|<span data-ttu-id="eed9a-106">설명</span><span class="sxs-lookup"><span data-stu-id="eed9a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eed9a-107">OnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="eed9a-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="eed9a-108">등록 된 이벤트에 대 한 콜백을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eed9a-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eed9a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eed9a-109">Requirements</span></span>  
 <span data-ttu-id="eed9a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eed9a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed9a-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eed9a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eed9a-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eed9a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eed9a-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eed9a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed9a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eed9a-114">See Also</span></span>  
 [<span data-ttu-id="eed9a-115">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="eed9a-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="eed9a-116">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eed9a-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="eed9a-117">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eed9a-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="eed9a-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eed9a-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
