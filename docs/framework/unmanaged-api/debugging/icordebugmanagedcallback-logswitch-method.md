---
title: ICorDebugManagedCallback::LogSwitch 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d5284cf6072aa5c1c11cc83355a3e9fa5c96837
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415924"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="8fc23-102">ICorDebugManagedCallback::LogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="8fc23-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="8fc23-103">공용 언어 런타임 (CLR) 관리 되는 스레드에서의 메서드를 호출 했습니다 디버거에 알립니다는 <xref:System.Diagnostics.Switch> 클래스를 만들거나 수정 하거나 디버깅/추적 스위치를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc23-104">구문</span><span class="sxs-lookup"><span data-stu-id="8fc23-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fc23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8fc23-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="8fc23-106">[in] ICorDebugAppDomain 생성/수정 / 디버깅/추적 스위치를 삭제 하는 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="8fc23-107">[in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="8fc23-108">[in] 이벤트 로그에 작성 된 설명 하는 메시지의 심각도 수준을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="8fc23-109">[in] 값은 [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) 디버깅/추적 스위치에 수행 후 작업을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="8fc23-110">[in] 디버깅/추적 스위치의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="8fc23-111">[in] 디버깅/추적 스위치에 대 한 부모 노드의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc23-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fc23-112">Requirements</span></span>  
 <span data-ttu-id="8fc23-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc23-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc23-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fc23-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fc23-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fc23-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fc23-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc23-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc23-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fc23-117">See Also</span></span>  
 [<span data-ttu-id="8fc23-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fc23-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
