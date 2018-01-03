---
title: "COR_FIELD 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_FIELD
helpviewer_keywords: COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09a96a22a653688540bcc2ea3a03d86e242c10f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corfield-structure"></a><span data-ttu-id="a434d-102">COR_FIELD 구조체</span><span class="sxs-lookup"><span data-stu-id="a434d-102">COR_FIELD Structure</span></span>
<span data-ttu-id="a434d-103">개체의 필드에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a434d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a434d-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="a434d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a434d-105">Members</span></span>  
  
|<span data-ttu-id="a434d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a434d-106">Member</span></span>|<span data-ttu-id="a434d-107">설명</span><span class="sxs-lookup"><span data-stu-id="a434d-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="a434d-108">`mdFieldDef` 필드 정보를 가져오는 데 사용할 수 있는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="a434d-109">개체의 필드 데이터의 바이트 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="a434d-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 필드의 유형을 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="a434d-111">필드의 유형을 나타내는 CorElementType 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a434d-112">설명</span><span class="sxs-lookup"><span data-stu-id="a434d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a434d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a434d-113">Requirements</span></span>  
 <span data-ttu-id="a434d-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a434d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a434d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a434d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a434d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a434d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a434d-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a434d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a434d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a434d-118">See Also</span></span>  
 [<span data-ttu-id="a434d-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="a434d-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a434d-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="a434d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
