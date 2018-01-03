---
title: "ICorDebug::DebugActiveProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.DebugActiveProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10cb2a5323db67c6f5664e13cb1f97d1a807d20c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="77855-102">ICorDebug::DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="77855-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="77855-103">기존 프로세스에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="77855-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77855-104">구문</span><span class="sxs-lookup"><span data-stu-id="77855-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77855-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77855-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="77855-106">[in] 디버거를 연결 하는 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="77855-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="77855-107">[in] 부울 값으로 설정 된 `true` 디버거 프로세스에 대 한 Win32 디버거도 작동 하 고 관리 되지 않는 콜백을; 발송 해야 하는 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="77855-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="77855-108">[out] 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77855-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77855-109">설명</span><span class="sxs-lookup"><span data-stu-id="77855-109">Remarks</span></span>  
 <span data-ttu-id="77855-110">Interop 디버깅 IA 64 기반 및 AMD64 기반 플랫폼에서와 같은 Win9x 및 비 x86 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77855-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77855-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77855-111">Requirements</span></span>  
 <span data-ttu-id="77855-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77855-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77855-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77855-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77855-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77855-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77855-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77855-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77855-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77855-116">See Also</span></span>  
 [<span data-ttu-id="77855-117">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77855-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
