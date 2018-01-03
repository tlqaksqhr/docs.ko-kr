---
title: "ICorDebugRegisterSet::GetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fba96f9d86f1df5c0800c8cafb9c7fd1b0a6f8c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="f8fa0-102">ICorDebugRegisterSet::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="f8fa0-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="f8fa0-103">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fa0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8fa0-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8fa0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8fa0-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="f8fa0-106">[in] 를 바이트 단위로 크기의는 `context` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="f8fa0-107">[out에서] Win32를 구성 하는 바이트 배열을 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8fa0-108">설명</span><span class="sxs-lookup"><span data-stu-id="f8fa0-108">Remarks</span></span>  
 <span data-ttu-id="f8fa0-109">디버거에서 Win32 대신이 함수를 호출 해야 `GetThreadContext` 스레드 컨텍스트에 일시적으로 변경 하는 "도용된" 상태에 있을 수 때문에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="f8fa0-110">반환 되는 데이터는 Win32 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="f8fa0-111">리프가 아닌 프레임에 대 한 클라이언트를 사용 하 여 있는 레지스터 올바른지 확인 해야 [icordebugregisterset:: Getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8fa0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8fa0-112">Requirements</span></span>  
 <span data-ttu-id="f8fa0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8fa0-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8fa0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8fa0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8fa0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8fa0-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8fa0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fa0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8fa0-117">See Also</span></span>  
 [<span data-ttu-id="f8fa0-118">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8fa0-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="f8fa0-119">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8fa0-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
