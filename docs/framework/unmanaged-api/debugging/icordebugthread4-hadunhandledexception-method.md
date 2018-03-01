---
title: "ICorDebugThread4::HadUnhandledException 메서드"
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
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a79d06f0a65facfbaa821d3dd6af547fd3d0305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="6d266-102">ICorDebugThread4::HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="6d266-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="6d266-103">스레드가 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d266-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d266-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d266-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d266-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="6d266-106">[out] 순서가 지정 된 열거형의 주소에 대 한 포인터 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d266-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6d266-107">Return Value</span></span>  
 <span data-ttu-id="6d266-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6d266-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d266-109">HRESULT</span></span>|<span data-ttu-id="6d266-110">설명</span><span class="sxs-lookup"><span data-stu-id="6d266-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d266-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d266-111">S_OK</span></span>|<span data-ttu-id="6d266-112">스레드가는 만들어진 이후 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="6d266-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6d266-113">S_FALSE</span></span>|<span data-ttu-id="6d266-114">스레드가 처리 되지 않은 예외가 적입니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d266-115">설명</span><span class="sxs-lookup"><span data-stu-id="6d266-115">Remarks</span></span>  
 <span data-ttu-id="6d266-116">이 메서드는 스레드에서 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="6d266-117">예외로 인해 콜백 트리거될 때까지 또는 네이티브 JIT 연결가 시작 되 면이 메서드는 항상 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="6d266-118">하지만 다 하는 [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) 메서드는 처리 되지 않은 예외를 반환 하는 경우 프로세스 하지 아직 계속 된 예외로 인해 콜백을 받은 후 또는 시 됩니다; 네이티브 JIT 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="6d266-119">또한 것 가능 없지만 둘 이상의 스레드가 네이티브 JIT 연결 트리거될 때 처리 되지 않은 예외와 함께 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="6d266-120">이러한 경우 JIT 연결을 트리거한 예외를 확인할 수 없습니다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d266-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d266-121">Requirements</span></span>  
 <span data-ttu-id="6d266-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d266-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d266-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d266-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d266-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d266-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d266-125">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d266-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d266-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d266-126">See Also</span></span>  
 [<span data-ttu-id="6d266-127">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d266-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="6d266-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d266-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6d266-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="6d266-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
