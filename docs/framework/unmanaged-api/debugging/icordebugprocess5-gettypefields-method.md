---
title: "ICorDebugProcess5::GetTypeFields 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeFields
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a64e754a77c7d730d921f8a8c1547dd18b66d77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="2ed09-102">ICorDebugProcess5::GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="2ed09-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="2ed09-103">형식에 속하는 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed09-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ed09-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ed09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ed09-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="2ed09-106">[in] 해당 필드 정보를 검색할 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="2ed09-107">[in] 수가 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 필드 정보를 검색할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="2ed09-108">[out] 배열을 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 형식에 속하는 필드에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="2ed09-109">[out] 수에 대 한 포인터 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 에 포함 된 개체 `fields`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ed09-110">설명</span><span class="sxs-lookup"><span data-stu-id="2ed09-110">Remarks</span></span>  
 <span data-ttu-id="2ed09-111">`celt` 필드 메서드가 사용 하 여 필드 정보를 가져올 수를 지정 하는 매개 변수 `fields`의 값에 해당 해야는 `COR_TYPE_LAYOUT::numFields` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed09-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ed09-112">Requirements</span></span>  
 <span data-ttu-id="2ed09-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed09-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ed09-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ed09-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ed09-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ed09-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed09-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed09-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ed09-117">See Also</span></span>  
 [<span data-ttu-id="2ed09-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ed09-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="2ed09-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ed09-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
