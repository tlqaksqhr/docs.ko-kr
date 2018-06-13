---
title: ICorDebugStepper::StepOut 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419168"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="c6d07-102">ICorDebugStepper::StepOut 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d07-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="c6d07-103">단일 단계를 완료 하는 현재 프레임 호출 프레임으로 제어를 반환 하 고 포함 스레드를 통해이 ICorDebugStepper 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d07-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6d07-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6d07-105">설명</span><span class="sxs-lookup"><span data-stu-id="c6d07-105">Remarks</span></span>  
 <span data-ttu-id="c6d07-106">A `StepOut` 작업 호출 프레임을 현재 프레임에서 정상적으로 반환 된 후 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="c6d07-107">경우 `StepOut` 때 호출 되는 현재 프레임을 호출한 관리 코드에 반환 될 때 관리 되지 않는 코드 단계 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="c6d07-108">.NET Framework 버전 2.0에서는 사용 하지 마십시오 `StepOut` 가 실패 플래그가 설정 된 STOP_UNMANAGED와 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="c6d07-109">(사용 하 여 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 단계별 실행에 대 한 플래그를 설정할 수 있습니다.) Interop 디버거 나가야 네이티브 코드에 자신입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d07-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6d07-110">Requirements</span></span>  
 <span data-ttu-id="c6d07-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d07-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d07-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d07-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
