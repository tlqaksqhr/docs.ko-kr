---
title: "ICorDebugNativeFrame::CanSetIP 메서드"
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
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b87ff9ae71b916a9a1141c2e5fedce7f79fbcd23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="f0a8f-102">ICorDebugNativeFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="f0a8f-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="f0a8f-103">네이티브 코드에서 지정된 된 오프셋된 위치를은 IP (명령 포인터)를 설정할 수 있는지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0a8f-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0a8f-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0a8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0a8f-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f0a8f-106">[in] 명령 포인터에 대 한 원하는 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a8f-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a8f-107">설명</span><span class="sxs-lookup"><span data-stu-id="f0a8f-107">Remarks</span></span>  
 <span data-ttu-id="f0a8f-108">사용 하 여는 `CanSetIP` 메서드를 호출 하기 전에 [icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f0a8f-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="f0a8f-109">경우 `CanSetIP` HRESULT를 반환 S_OK 이외의 실행할 수 있습니다 `ICorDebugNativeFrame::SetIP`, 하지만 디버거에서 디버깅 중인 코드를 안전 하 고 올바르게 실행할을 계속 해 서 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a8f-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a8f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0a8f-110">Requirements</span></span>  
 <span data-ttu-id="f0a8f-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a8f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a8f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0a8f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0a8f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0a8f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0a8f-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a8f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a8f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0a8f-115">See Also</span></span>  
 
