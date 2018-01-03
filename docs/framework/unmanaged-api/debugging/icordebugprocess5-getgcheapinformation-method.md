---
title: "ICorDebugProcess5::GetGCHeapInformation 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetGCHeapInformation
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70e9e3ab6c7332e492b7146e52e0265653803bf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="c48ed-102">ICorDebugProcess5::GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="c48ed-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="c48ed-103">현재 열거 가능 여부를 포함 하 여 가비지 수집 힙에 대 한 일반 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="c48ed-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c48ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c48ed-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="c48ed-106">[out] 에 대 한 포인터는 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 가비지 수집 힙에 대 한 일반 정보를 제공 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c48ed-107">설명</span><span class="sxs-lookup"><span data-stu-id="c48ed-107">Remarks</span></span>  
 <span data-ttu-id="c48ed-108">`ICorDebugProcess5::GetGCHeapInformation` 힙을 열거 하기 전에 메서드를 호출 해야 또는 개별 힙 영역은 가비지 수집 구조체는 프로세스에 있는지 확인 하는 현재 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="c48ed-109">가비지 수집 힙에서 컬렉션 진행 중인 동안 진행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="c48ed-110">그렇지 않으면 열거형 유효 하지 않은 가비지 수집 구조를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c48ed-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c48ed-111">Requirements</span></span>  
 <span data-ttu-id="c48ed-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c48ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48ed-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c48ed-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c48ed-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c48ed-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c48ed-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48ed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48ed-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c48ed-116">See Also</span></span>  
 [<span data-ttu-id="c48ed-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c48ed-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="c48ed-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c48ed-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
