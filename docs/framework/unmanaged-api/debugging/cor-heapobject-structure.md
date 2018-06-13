---
title: COR_HEAPOBJECT 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e64bb2e1c8a7b11fe70024eb4a4fa1717c06e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407351"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="08875-102">COR_HEAPOBJECT 구조체</span><span class="sxs-lookup"><span data-stu-id="08875-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="08875-103">관리되는 힙의 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08875-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08875-104">구문</span><span class="sxs-lookup"><span data-stu-id="08875-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="08875-105">멤버</span><span class="sxs-lookup"><span data-stu-id="08875-105">Members</span></span>  
  
|<span data-ttu-id="08875-106">멤버</span><span class="sxs-lookup"><span data-stu-id="08875-106">Member</span></span>|<span data-ttu-id="08875-107">설명</span><span class="sxs-lookup"><span data-stu-id="08875-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="08875-108">메모리에 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="08875-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="08875-109">전체 크기 (바이트)에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08875-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="08875-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체의 형식을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="08875-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08875-111">설명</span><span class="sxs-lookup"><span data-stu-id="08875-111">Remarks</span></span>  
 <span data-ttu-id="08875-112">`COR_HEAPOBJECT` 인스턴스를 열거 하 여 검색할 수는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체를 호출 하 여 채워지는 [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="08875-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="08875-113">A `COR_HEAPOBJECT` 인스턴스 또는 관리 되는 힙에 대 한 활성 개체에 대 한 모든 개체에서 루트에서 시작 하지 않지만 아직 가비지 수집기가 수집 되지 않았습니다 하는 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08875-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="08875-114">성능 향상을 위해는 `COR_HEAPOBJECT.address` 필드는는 `CORDB_ADDRESS` 는 ICorDebugValue이 아닌 값 인터페이스 대부분의 디버깅 API에서 사용 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08875-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="08875-115">지정 된 개체 주소에 대 한 ICorDebugValue 개체를 가져오려면 전달할 수 있습니다는 `CORDB_ADDRESS` 값을 [icordebugprocess5:: Getobject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="08875-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="08875-116">성능 향상을 위해는 `COR_HEAPOBJECT.type` 필드는는 `COR_TYPEID` 는 ICorDebugType이 아닌 값 인터페이스 대부분의 디버깅 API에서 사용 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08875-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="08875-117">ICorDebugType 개체 ID를 지정 된 형식에 대 한를 가져오려면 전달할 수 있습니다는 `COR_TYPEID` 값을 [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="08875-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="08875-118">`COR_HEAPOBJECT` 구조에는 참조 횟수가 계산 COM 인터페이스에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08875-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="08875-119">검색 하는 경우는 `COR_HEAPOBJECT` 호출 하 여 열거자에서 인스턴스는 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드를 이후에 대 한 참조를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08875-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08875-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08875-120">Requirements</span></span>  
 <span data-ttu-id="08875-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08875-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08875-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08875-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08875-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08875-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08875-124">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08875-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08875-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08875-125">See Also</span></span>  
 [<span data-ttu-id="08875-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="08875-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="08875-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="08875-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
