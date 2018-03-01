---
title: "ICorDebugILFrame::CanSetIP 메서드"
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
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22d0df9add0a4ce35b1a590d65e30a6756fec49c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="844c5-102">ICorDebugILFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="844c5-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="844c5-103">명령 포인터 Microsoft MSIL (Intermediate Language) 코드에서 지정된 된 오프셋된 위치를 설정할 수 있는지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="844c5-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="844c5-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="844c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="844c5-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="844c5-106">[in] 명령 포인터에 대 한 원하는 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="844c5-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="844c5-107">설명</span><span class="sxs-lookup"><span data-stu-id="844c5-107">Remarks</span></span>  
 <span data-ttu-id="844c5-108">사용 하 여는 `CanSetIP` 메서드 호출 하기 전에 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="844c5-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="844c5-109">경우 `CanSetIP` HRESULT를 반환 S_OK 이외의 실행할 수 있습니다 `ICorDebugILFrame::SetIP`, 하지만 디버거에서 디버깅 중인 코드를 안전 하 고 올바르게 실행할을 계속 해 서 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="844c5-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="844c5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="844c5-110">Requirements</span></span>  
 <span data-ttu-id="844c5-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="844c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="844c5-112">**헤더:** CorDebug.idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="844c5-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="844c5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="844c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="844c5-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="844c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
