---
title: "ICorDebugProcess2::SetUnmanagedBreakpoint 메서드"
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
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 825917d48aaab5d9d5ce482fa600ca02efa158ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="ea7b5-102">ICorDebugProcess2::SetUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="ea7b5-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="ea7b5-103">네이티브 이미지를 지정 된 오프셋 위치에서 관리 되지 않는 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea7b5-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea7b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea7b5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="ea7b5-106">[in] A `CORDB_ADDRESS` 네이티브 이미지 오프셋을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="ea7b5-107">[in] 를 바이트 단위로 크기의는 `buffer` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="ea7b5-108">[out] 중단점으로 교체 하는 opcode가 포함 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="ea7b5-109">[out] 반환 된 바이트 수에 대 한 포인터는 `buffer` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea7b5-110">설명</span><span class="sxs-lookup"><span data-stu-id="ea7b5-110">Remarks</span></span>  
 <span data-ttu-id="ea7b5-111">네이티브 이미지 오프셋 공용 언어 런타임 (CLR) 내에 있으면 중단점이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="ea7b5-112">이렇게 하면 디버거에서 중단점이 설정 된 경우 대역의 중단점을 디스패치하지 CLR이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea7b5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea7b5-113">Requirements</span></span>  
 <span data-ttu-id="ea7b5-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea7b5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea7b5-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea7b5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea7b5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea7b5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea7b5-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea7b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
