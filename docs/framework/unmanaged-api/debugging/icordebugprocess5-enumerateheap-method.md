---
title: "ICorDebugProcess5::EnumerateHeap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41cd7d47650cdfe6a3598ba126be489107181a44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="16437-102">ICorDebugProcess5::EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="16437-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="16437-103">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16437-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16437-104">구문</span><span class="sxs-lookup"><span data-stu-id="16437-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16437-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16437-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="16437-106">[out] 주소에 대 한 포인터는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체는 관리 되는 힙에 있는 개체에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="16437-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16437-107">설명</span><span class="sxs-lookup"><span data-stu-id="16437-107">Remarks</span></span>  
 <span data-ttu-id="16437-108">호출 하기 전에 `ICorDebugProcess5::EnumerateHeap` 호출 해야 합니다는 [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드 값을 검사 하 고는 `areGCStructuresValid` 반환 된 필드 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 가비지 수집 힙의 현재 상태에서 열거 가능한 지 확인 하려면 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="16437-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="16437-109">또한는 `ICorDebugProcess5::EnumerateHeap` 반환 `E_FAIL` 관리 되는 힙의 할당에 대 한 메모리 하기 전에 프로세스의 수명을 너무 초기에 연결 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="16437-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="16437-110">[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체는 열거할 수 있도록 ICorDebugEnum 인터페이스에서 파생 된 표준 열거자 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="16437-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="16437-111">이 메서드는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 컬렉션 개체를 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 모든 개체에 대 한 정보를 제공 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="16437-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="16437-112">컬렉션에 포함 될 수도 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 하지으로 루트 개체에 대 한 정보를 제공 하는 인스턴스 개체 하지만 아직 가비지 수집기가 수집 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="16437-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16437-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16437-113">Requirements</span></span>  
 <span data-ttu-id="16437-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16437-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16437-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16437-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16437-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16437-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16437-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16437-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16437-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16437-118">See Also</span></span>  
 [<span data-ttu-id="16437-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16437-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="16437-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16437-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
