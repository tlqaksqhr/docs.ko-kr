---
title: "ICorDebugProcess5::EnumerateHeapRegions 메서드"
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
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 478a8490e57946a08670d9f86e1f6ebcc67703a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="5de74-102">ICorDebugProcess5::EnumerateHeapRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="5de74-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="5de74-103">관리 되는 힙의 메모리 범위에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de74-104">구문</span><span class="sxs-lookup"><span data-stu-id="5de74-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5de74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5de74-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="5de74-106">[out] 주소에 대 한 포인터는 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 인터페이스 개체는 개체는 관리 되는 힙에서 거주 하는 메모리의 범위에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de74-107">설명</span><span class="sxs-lookup"><span data-stu-id="5de74-107">Remarks</span></span>  
 <span data-ttu-id="5de74-108">호출 하기 전에 `ICorDebugProcess5::EnumerateHeapRegions` 호출 해야 합니다는 [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드 값을 검사 하 고는 `areGCStructuresValid` 반환 된 필드 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 가비지 수집 힙의 현재 상태에서 열거 가능한 지 확인 하려면 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="5de74-109">또한는 `ICorDebugProcess5::EnumerateHeapRegions` 메서드 반환 `E_FAIL` 너무 일찍 프로세스의 수명에에서 연결 하는 경우 메모리 하기 전에 영역이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="5de74-110">이 메서드는 항상 관리 되는 개체를 포함할 수 있는 모든 메모리 영역 열거 하지만 관리 되는 개체 실제로에 상주 하는 해당 영역 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="5de74-111">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 컬렉션 개체는 비어 있거나 예약 된 메모리 영역을 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="5de74-112">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 인터페이스 개체는 열거할 수 있도록 ICorDebugEnum 인터페이스에서 파생 된 표준 열거자 [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="5de74-113">각 [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) 개체 해당 세그먼트에 있는 개체의 세대와 함께 특정 세그먼트의 메모리 범위에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de74-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5de74-114">Requirements</span></span>  
 <span data-ttu-id="5de74-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5de74-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de74-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5de74-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5de74-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5de74-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5de74-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de74-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de74-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5de74-119">See Also</span></span>  
 [<span data-ttu-id="5de74-120">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5de74-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="5de74-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5de74-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
