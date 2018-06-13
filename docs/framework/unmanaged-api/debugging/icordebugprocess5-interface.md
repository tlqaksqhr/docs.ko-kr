---
title: ICorDebugProcess5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423373"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="1c8f8-102">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c8f8-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="1c8f8-103">관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하는 관리 되는 힙에 대 한 액세스를 지원 하기 위해 ICorDebugProcess 인터페이스를 확장 하 고 디버거 여부를 확인 하려면 응용 프로그램의 로컬 네이티브 이미지 캐시에서 이미지를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c8f8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-104">Methods</span></span>  
  
|<span data-ttu-id="1c8f8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-105">Method</span></span>|<span data-ttu-id="1c8f8-106">설명</span><span class="sxs-lookup"><span data-stu-id="1c8f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c8f8-107">EnableNGenPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="1c8f8-108">응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="1c8f8-109">EnumerateGCReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="1c8f8-110">프로세스의 가비지 수집 하는 모든 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="1c8f8-111">EnumerateHandles 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="1c8f8-112">프로세스에서 개체 핸들에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="1c8f8-113">EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="1c8f8-114">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="1c8f8-115">EnumerateHeapRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="1c8f8-116">관리 영역에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="1c8f8-117">GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="1c8f8-118">메모리에 배열 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="1c8f8-119">GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="1c8f8-120">에 대 한 포인터를 가져옵니다는 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 관리 되는 힙의 가비지 수집 될 개체에 대 한 정보가 포함 된 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="1c8f8-121">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="1c8f8-122">관리 되는 힙의 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="1c8f8-123">GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="1c8f8-124">유형 식별자를 기반으로 하는 형식에 대 한 필드 정보를 포함 하는 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="1c8f8-125">GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="1c8f8-126">해당 형식 식별자를 기반으로 개체에 대 한 정보를 제공 하는 형식 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="1c8f8-127">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="1c8f8-128">지정된 된 주소에서 개체에 대 한 형식 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="1c8f8-129">GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="1c8f8-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="1c8f8-130">유형 식별자를 기반으로 메모리에 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c8f8-131">설명</span><span class="sxs-lookup"><span data-stu-id="1c8f8-131">Remarks</span></span>  
 <span data-ttu-id="1c8f8-132">이 인터페이스 ICorDebugProcess2, ICorDebugProcess를 논리적으로 확장 하 고 [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c8f8-133">이 인터페이스는 다른 프로세스 또는 다른 컴퓨터에서 원격 호출을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c8f8-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c8f8-134">Requirements</span></span>  
 <span data-ttu-id="1c8f8-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c8f8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c8f8-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c8f8-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c8f8-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c8f8-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c8f8-138">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c8f8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8f8-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c8f8-139">See Also</span></span>  
 [<span data-ttu-id="1c8f8-140">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c8f8-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1c8f8-141">디버깅</span><span class="sxs-lookup"><span data-stu-id="1c8f8-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
