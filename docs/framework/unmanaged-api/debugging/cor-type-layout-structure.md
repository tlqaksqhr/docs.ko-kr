---
title: "COR_TYPE_LAYOUT 구조체"
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
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 250d78dd9983b75fa7e1b3cfd99215160fbc2b1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="1721e-102">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="1721e-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="1721e-103">메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1721e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1721e-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="1721e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1721e-105">Members</span></span>  
  
|<span data-ttu-id="1721e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1721e-106">Member</span></span>|<span data-ttu-id="1721e-107">설명</span><span class="sxs-lookup"><span data-stu-id="1721e-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="1721e-108">이 형식에 대 한 부모 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="1721e-109">NULL 유형 id (token1 = 0, token2 = 0)의 형식 id에 해당 하는 경우 <xref:System.Object?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="1721e-110">이 형식의 개체의 기본 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-110">The base size of an object of this type.</span></span> <span data-ttu-id="1721e-111">비 변수 크기의 개체에 대 한 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="1721e-112">이 형식의 개체에 포함 된 필드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="1721e-113">Box은이 이와 같은 경우 개체의 필드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="1721e-114">이 필드는 기본 형식 및 구조와 같은 값 형식에 대해서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="1721e-115">이 형식이 속해 있는 CorElementType 합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1721e-116">설명</span><span class="sxs-lookup"><span data-stu-id="1721e-116">Remarks</span></span>  
 <span data-ttu-id="1721e-117">경우 `numFields` 0 보다 크면 호출할 수 있습니다는 [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) 이 형식의 필드에 대 한 정보를 얻는 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="1721e-118">경우 `type` 은 `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, 또는 `ELEMENT_TYPE_SZARRAY`,이 형식의 개체의 크기는 변수가 아니며 전달할 수 있습니다는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 구조체는 [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1721e-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1721e-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1721e-119">Requirements</span></span>  
 <span data-ttu-id="1721e-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1721e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1721e-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1721e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1721e-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1721e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1721e-123">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1721e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1721e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1721e-124">See Also</span></span>  
 [<span data-ttu-id="1721e-125">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1721e-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="1721e-126">디버깅</span><span class="sxs-lookup"><span data-stu-id="1721e-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
