---
title: ICorDebugRegisterSet2::SetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35d91f13cedfbf49d48318630760cf1525d16340
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422392"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="d863f-102">ICorDebugRegisterSet2::SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="d863f-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="d863f-103">`SetRegisters` .NET Framework 버전 2.0에서에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d863f-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d863f-104">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d863f-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d863f-105">와 같은 상위 수준 작업을 사용 하 여 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 또는 [icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d863f-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d863f-106">구문</span><span class="sxs-lookup"><span data-stu-id="d863f-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d863f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d863f-107">Requirements</span></span>  
 <span data-ttu-id="d863f-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d863f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d863f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d863f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d863f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d863f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d863f-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d863f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d863f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d863f-112">See Also</span></span>  
 [<span data-ttu-id="d863f-113">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d863f-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="d863f-114">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d863f-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
