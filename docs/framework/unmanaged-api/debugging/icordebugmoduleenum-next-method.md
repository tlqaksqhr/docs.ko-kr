---
title: "ICorDebugModuleEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 917707135f2159b020d9d3c7afb7d70ae466e3e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="fdab6-102">ICorDebugModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fdab6-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="fdab6-103">로 지정 된 "ICorDebugModule" 인스턴스 수를 가져옵니다 `celt` 에서 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fdab6-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdab6-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdab6-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdab6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdab6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fdab6-106">[in] 수가 `ICorDebugModule` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdab6-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="fdab6-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugModule` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fdab6-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fdab6-108">[out] 수에 대 한 포인터 `ICorDebugModule` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="fdab6-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="fdab6-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fdab6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdab6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdab6-110">Requirements</span></span>  
 <span data-ttu-id="fdab6-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdab6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdab6-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdab6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdab6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdab6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdab6-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdab6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdab6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdab6-115">See Also</span></span>  
 
