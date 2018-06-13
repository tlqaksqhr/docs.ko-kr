---
title: ICorDebugNativeFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed8b6bf60790c10b9869dcc41678be050b8979dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420227"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="4973c-102">ICorDebugNativeFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="4973c-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="4973c-103">네이티브 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4973c-104">구문</span><span class="sxs-lookup"><span data-stu-id="4973c-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4973c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4973c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="4973c-106">[in] 네이티브 코드에 대 한 오프셋된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4973c-107">설명</span><span class="sxs-lookup"><span data-stu-id="4973c-107">Remarks</span></span>  
 <span data-ttu-id="4973c-108">에 대 한 호출이 `SetIP` 즉시 모든 프레임 및 현재 스레드에 대 한 체인을 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="4973c-109">디버거를 호출한 후 프레임 정보가 필요한 경우 `SetIP`, 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="4973c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="4973c-111">그러나 경우에 프레임 유효한 상태에 런타임 측 관련해 서, 초기화 되지 않은 지역 변수, 등과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="4973c-112">호출자가 실행 중인 프로그램의 일관성이 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="4973c-113">64 비트 플랫폼에서 명령 포인터 없습니다에서 이동할 수는 `catch` 또는 `finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="4973c-114">경우 `SetIP` 호출 되는 64 비트 플랫폼에서 이러한 이동 되도록 오류를 나타내는 HRESULT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4973c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4973c-115">Requirements</span></span>  
 <span data-ttu-id="4973c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4973c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4973c-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4973c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4973c-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4973c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4973c-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4973c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4973c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4973c-120">See Also</span></span>  
 
