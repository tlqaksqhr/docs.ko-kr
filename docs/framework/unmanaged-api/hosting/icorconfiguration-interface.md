---
title: "ICorConfiguration 인터페이스"
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
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af9a7d4bb1d38fd4a81e954074b074325409ee5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="0cd90-102">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cd90-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="0cd90-103">공용 언어 런타임 (CLR)를 구성 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cd90-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-104">Methods</span></span>  
  
|<span data-ttu-id="0cd90-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-105">Method</span></span>|<span data-ttu-id="0cd90-106">설명</span><span class="sxs-lookup"><span data-stu-id="0cd90-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cd90-107">AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="0cd90-108">디버깅 서비스에 특정 스레드를 계속 디버거가 응용 프로그램을 중지 하는 동안 관리 되거나 관리 되지 않는 디버깅 시나리오는 동시 실행 수 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="0cd90-109">SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="0cd90-110">디버깅 서비스 디버깅을 위한 CLR 스레드를 차단 하 여 차단 해제를 호출 하는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="0cd90-111">SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="0cd90-112">콜백 인터페이스를 호스트에 가상 메모리의 한계를 변경 하도록 요청 하는 가비지 수집기에서 사용할 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="0cd90-113">SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="0cd90-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="0cd90-114">가비지 컬렉션에 대 한 차단 될 런타임 외 작업에 대 한 스레드를 예약 하기 위한 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0cd90-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cd90-115">Requirements</span></span>  
 <span data-ttu-id="0cd90-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd90-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd90-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0cd90-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cd90-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0cd90-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cd90-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd90-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd90-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cd90-120">See Also</span></span>  
 [<span data-ttu-id="0cd90-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cd90-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="0cd90-122">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="0cd90-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
