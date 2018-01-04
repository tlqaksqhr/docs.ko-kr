---
title: "ICorDebugManagedCallback2::ExceptionUnwind 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ExceptionUnwind
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64b85311f625e39dd25c48a60dde2fbaf66a957f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="661f6-102">ICorDebugManagedCallback2::ExceptionUnwind 메서드</span><span class="sxs-lookup"><span data-stu-id="661f6-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="661f6-103">예외 해제 프로세스 중에 상태 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="661f6-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="661f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="661f6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="661f6-106">[in] 예외가 throw 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="661f6-107">[in] 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="661f6-108">[in] 신호를 보내는 콜백을 해제 단계 중 이벤트를 지정 하는 CorDebugExceptionUnwindCallbackType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="661f6-109">[in] 값은 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 예외에 대 한 추가 정보를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="661f6-110">설명</span><span class="sxs-lookup"><span data-stu-id="661f6-110">Remarks</span></span>  
 <span data-ttu-id="661f6-111">`ExceptionUnwind`예외 처리 프로세스의 해제 단계 동안 다양 한 시점에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="661f6-112">`ExceptionUnwind`단일 예외를 해제 하는 동안 두 번 이상 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="661f6-113">경우 `dwEventType` DEBUG_EXCEPTION_INTERCEPTED, = 명령 포인터 앞 시퀀스 지점 스레드의 리프 프레임에 포함 됩니다 (하기 전에 몇 가지 지침 수 있음)는 예외를 발생 시킨 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661f6-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="661f6-114">Requirements</span></span>  
 <span data-ttu-id="661f6-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="661f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="661f6-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="661f6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="661f6-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="661f6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="661f6-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661f6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="661f6-119">See Also</span></span>  
 [<span data-ttu-id="661f6-120">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="661f6-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="661f6-121">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="661f6-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
