---
title: "ICorDebugDataTarget 인터페이스"
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
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5d3a3b190cfa606bd4239e24c5defdaff9f4257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="4638a-102">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4638a-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="4638a-103">특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4638a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4638a-104">Methods</span></span>  
  
|<span data-ttu-id="4638a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4638a-105">Method</span></span>|<span data-ttu-id="4638a-106">설명</span><span class="sxs-lookup"><span data-stu-id="4638a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4638a-107">GetPlatform 메서드</span><span class="sxs-lookup"><span data-stu-id="4638a-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="4638a-108">프로세서 아키텍처와 대상 프로세스가 실행 되는 운영 체제를 포함 하는 플랫폼에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="4638a-109">ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="4638a-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="4638a-110">지정된 된 주소에서 시작 하는 인접 한 메모리 블록을 가져오고 제공된 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="4638a-111">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="4638a-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="4638a-112">지정된 된 스레드에 대 한 현재 스레드 컨텍스트를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4638a-113">설명</span><span class="sxs-lookup"><span data-stu-id="4638a-113">Remarks</span></span>  
 <span data-ttu-id="4638a-114">`ICorDebugDataTarget`및 해당 메서드는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
-   <span data-ttu-id="4638a-115">디버깅 서비스의 메모리와 대상 프로세스의 다른 데이터를 액세스 하려면이 인터페이스에서 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
-   <span data-ttu-id="4638a-116">디버거 클라이언트 (예를 들어 활성 프로세스 또는 메모리 덤프) 특정 대상에 따라이 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
-   <span data-ttu-id="4638a-117">`ICorDebugDataTarget` 또 다른 구현 된 메서드 내 에서만 메서드를 호출할 수 있습니다 `ICorDebug*` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="4638a-118">이렇게 하면 디버거 클라이언트에 특정 스레드에서 호출 시기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
-   <span data-ttu-id="4638a-119">`ICorDebugDataTarget` 구현 항상 대상에 대 한 최신 정보를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="4638a-120">대상 프로세스를 중지 하는 동안 어떤 식으로든에서 변경 되지 `ICorDebug*` 인터페이스 (및 따라서 `ICorDebugDataTarget` 메서드) 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="4638a-121">대상이 활성 프로세스 및 해당 상태의 변경 내용을 인 경우는 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드가 대체 ICorDebugProcess 인스턴스를 제공 하기 위해 다시 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4638a-122">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4638a-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4638a-123">Requirements</span></span>  
 <span data-ttu-id="4638a-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4638a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4638a-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4638a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4638a-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4638a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4638a-127">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4638a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4638a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4638a-128">See Also</span></span>  
 [<span data-ttu-id="4638a-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4638a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4638a-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="4638a-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
