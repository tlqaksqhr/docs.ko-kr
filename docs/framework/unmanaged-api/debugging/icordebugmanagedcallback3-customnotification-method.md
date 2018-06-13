---
title: ICorDebugManagedCallback3::CustomNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 098e140b7bffb7798a37b1881f2cb2ced36bcf1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416487"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="05eaa-102">ICorDebugManagedCallback3::CustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="05eaa-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="05eaa-103">사용자 지정 디버거 알림이 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05eaa-104">구문</span><span class="sxs-lookup"><span data-stu-id="05eaa-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05eaa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05eaa-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="05eaa-106">[in] 알림을 발생 하는 스레드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="05eaa-107">[in] 알림을 발생 하는 스레드를 포함 하는 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05eaa-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="05eaa-108">Return Value</span></span>  
 <span data-ttu-id="05eaa-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="05eaa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05eaa-110">HRESULT</span></span>|<span data-ttu-id="05eaa-111">설명</span><span class="sxs-lookup"><span data-stu-id="05eaa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05eaa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="05eaa-112">S_OK</span></span>|<span data-ttu-id="05eaa-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="05eaa-114">예외</span><span class="sxs-lookup"><span data-stu-id="05eaa-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05eaa-115">설명</span><span class="sxs-lookup"><span data-stu-id="05eaa-115">Remarks</span></span>  
 <span data-ttu-id="05eaa-116">후속 호출에는 [icordebugthread4:: Getcurrentcustomdebuggernotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) 에 전달 된 스레드 개체를 검색 하는 메서드는 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="05eaa-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05eaa-117">스레드 개체의 형식을 해야 이전에 설정한 호출 하 여는 [icordebugprocess3:: Setenablecustomnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="05eaa-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="05eaa-118">디버거가는 thread 개체의 필드에서 특정 형식의 매개 변수를 읽을 수 있습니다 및 필드에 응답을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="05eaa-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스에서는 정책을 적용 하지 알림 나 내용 유형 및에서 알림의 의미 체계는 엄격 하 게 디버거, 응용 프로그램 및.NET Framework 사이의 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05eaa-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05eaa-120">Requirements</span></span>  
 <span data-ttu-id="05eaa-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05eaa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05eaa-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05eaa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05eaa-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05eaa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05eaa-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05eaa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05eaa-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05eaa-125">See Also</span></span>  
 [<span data-ttu-id="05eaa-126">ICorDebugManagedCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05eaa-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [<span data-ttu-id="05eaa-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05eaa-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="05eaa-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="05eaa-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
