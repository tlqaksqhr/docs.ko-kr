---
title: "ICorDebugStackWalk::GetContext 메서드"
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
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 080ce39422faee4e1228bd87bf994080fab4de71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="c21dd-102">ICorDebugStackWalk::GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c21dd-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="c21dd-103">현재 프레임에 대 한 컨텍스트를 반환 된 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="c21dd-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c21dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c21dd-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="c21dd-106">[in] (WinNT.h에 정의 됨)은 컨텍스트 버퍼의 요청 된 콘텐츠를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="c21dd-107">[in] 컨텍스트 버퍼의 할당 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c21dd-108">[out] 컨텍스트의 실제 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-108">[out] The actual size of the context.</span></span> <span data-ttu-id="c21dd-109">이 값은 컨텍스트 버퍼의 크기 보다 작거나 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="c21dd-110">[out] 상황에 맞는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c21dd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c21dd-111">Return Value</span></span>  
 <span data-ttu-id="c21dd-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c21dd-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c21dd-113">HRESULT</span></span>|<span data-ttu-id="c21dd-114">설명</span><span class="sxs-lookup"><span data-stu-id="c21dd-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c21dd-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c21dd-115">S_OK</span></span>|<span data-ttu-id="c21dd-116">현재 프레임에 대 한 컨텍스트가 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="c21dd-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c21dd-117">E_FAIL</span></span>|<span data-ttu-id="c21dd-118">컨텍스트를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="c21dd-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="c21dd-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="c21dd-120">상황에 맞는 버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="c21dd-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="c21dd-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="c21dd-122">프레임 포인터는 이미; 스택의 끝 따라서 추가 프레임 없음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c21dd-123">예외</span><span class="sxs-lookup"><span data-stu-id="c21dd-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c21dd-124">설명</span><span class="sxs-lookup"><span data-stu-id="c21dd-124">Remarks</span></span>  
 <span data-ttu-id="c21dd-125">예 비휘발성 레지스터: 레지스터의 하위 집합만 복원 해제 때문에 컨텍스트가 다 레지스터 상태 호출 시.</span><span class="sxs-lookup"><span data-stu-id="c21dd-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21dd-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c21dd-126">Requirements</span></span>  
 <span data-ttu-id="c21dd-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c21dd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21dd-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c21dd-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c21dd-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c21dd-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c21dd-130">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21dd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21dd-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c21dd-131">See Also</span></span>  
 [<span data-ttu-id="c21dd-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c21dd-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c21dd-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="c21dd-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
