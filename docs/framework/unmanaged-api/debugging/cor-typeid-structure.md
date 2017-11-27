---
title: "COR_TYPEID 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 795dea77ac8dac1e1d22574c23f1e1c13344a71a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="f6f1e-102">COR_TYPEID 구조체</span><span class="sxs-lookup"><span data-stu-id="f6f1e-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="f6f1e-103">유형 식별자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6f1e-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="f6f1e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f6f1e-105">Members</span></span>  
  
|<span data-ttu-id="f6f1e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f6f1e-106">Member</span></span>|<span data-ttu-id="f6f1e-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6f1e-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="f6f1e-108">첫 번째 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="f6f1e-109">두 번째 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6f1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="f6f1e-110">Remarks</span></span>  
 <span data-ttu-id="f6f1e-111">`COR_TYPEID` 구조는 여러 디버깅 메서드를 가비지 수집할 개체에 대 한 정보를 제공 하 여 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="f6f1e-112">그 다음 전달할 수 있습니다를 인수로 해당 항목에 대 한 추가 정보를 제공 하는 다른 디버깅 메서드로.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="f6f1e-113">열거 하는 예를 들어 여는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 개체, 개별를 검색할 수 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개별 관리 되는 힙의 개체를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="f6f1e-114">에 전달할 수 있습니다는 `COR_TYPEID` 에서 값의 `COR_HEAPOBJECT.type` 필드를 [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 개체에 대 한 형식 정보를 제공 하는 ICorDebugType 개체를 검색 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="f6f1e-115">A `COR_TYPEID` 개체는 불투명 되도록 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="f6f1e-116">개별 필드를 액세스 하거나 조작할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="f6f1e-117">유일한 사용은으로 제공 되는 식별자로 됩니다는 `out` 차례로 메서드 호출 및 수 있는 매개 변수가 추가 정보를 제공 하는 기타 메서드가에 전달 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f1e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6f1e-118">Requirements</span></span>  
 <span data-ttu-id="f6f1e-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f1e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f1e-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6f1e-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6f1e-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6f1e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6f1e-122">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f1e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f1e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6f1e-123">See Also</span></span>  
 [<span data-ttu-id="f6f1e-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="f6f1e-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="f6f1e-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="f6f1e-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
