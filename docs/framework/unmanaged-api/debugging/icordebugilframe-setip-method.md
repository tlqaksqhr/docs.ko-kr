---
title: "ICorDebugILFrame::SetIP 메서드"
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
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="96944-102">ICorDebugILFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="96944-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="96944-103">Microsoft MSIL (intermediate language) 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96944-104">구문</span><span class="sxs-lookup"><span data-stu-id="96944-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96944-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96944-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="96944-106">MSIL 코드 내의 오프셋된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="96944-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96944-107">설명</span><span class="sxs-lookup"><span data-stu-id="96944-107">Remarks</span></span>  
 <span data-ttu-id="96944-108">에 대 한 호출이 `SetIP` 즉시 모든 프레임 및 현재 스레드에 대 한 체인을 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="96944-109">디버거를 호출한 후 프레임 정보가 필요한 경우 `SetIP`, 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="96944-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="96944-111">그러나 경우에 프레임 유효한 상태, 초기화 되지 않은 지역 변수와 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96944-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="96944-112">호출자가 실행 중인 프로그램의 일관성이 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="96944-113">64 비트 플랫폼에서 명령 포인터 없습니다에서 이동할 수는 `catch` 또는 `finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="96944-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="96944-114">경우 `SetIP` 호출 되는 64 비트 플랫폼에서 이러한 이동 되도록 오류를 나타내는 HRESULT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96944-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96944-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96944-115">Requirements</span></span>  
 <span data-ttu-id="96944-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96944-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96944-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96944-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96944-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96944-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96944-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96944-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
