---
title: "ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드"
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
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14258ef1ae473fc867d86c89ec877ddbf8c80213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="761f7-102">ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="761f7-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="761f7-103">이전에 설정한 제거 주어진된 주소에 중단점.</span><span class="sxs-lookup"><span data-stu-id="761f7-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="761f7-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="761f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="761f7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="761f7-106">[in] A `CORDB_ADDRESS` 중단점을 설정한 주소 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="761f7-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="761f7-107">설명</span><span class="sxs-lookup"><span data-stu-id="761f7-107">Remarks</span></span>  
 <span data-ttu-id="761f7-108">지정 된 중단점 이전에 설정 된 한 이전 호출에서 [icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="761f7-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="761f7-109">`ClearUnmanagedBreakpoint` 디버깅 중인 프로세스에서 실행 되는 동안에 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="761f7-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="761f7-110">`ClearUnmanagedBreakpoint` 관리 전용 모드에서 디버거가 연결 된 경우 또는 지정된 된 주소에서 중단점이 없는 경우 메서드가 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="761f7-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="761f7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="761f7-111">Requirements</span></span>  
 <span data-ttu-id="761f7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="761f7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="761f7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="761f7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="761f7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="761f7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="761f7-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="761f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
