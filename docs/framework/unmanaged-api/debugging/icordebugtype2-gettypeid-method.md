---
title: ICorDebugType2::GetTypeID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422073"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="baf82-102">ICorDebugType2::GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="baf82-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="baf82-103">가져옵니다는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf82-104">구문</span><span class="sxs-lookup"><span data-stu-id="baf82-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="baf82-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baf82-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="baf82-106">[out] 에 대 한 포인터는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 ICorDebugType에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baf82-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="baf82-107">Return Value</span></span>  
 <span data-ttu-id="baf82-108">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="baf82-109">`HRESULT` 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="baf82-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="baf82-110">Return code</span></span>|<span data-ttu-id="baf82-111">설명</span><span class="sxs-lookup"><span data-stu-id="baf82-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="baf82-112">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-112">Method succeeded.</span></span> <span data-ttu-id="baf82-113">메서드는 유효한 검색 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="baf82-114">형식 로드 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="baf82-115">형식이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf82-116">설명</span><span class="sxs-lookup"><span data-stu-id="baf82-116">Remarks</span></span>  
 <span data-ttu-id="baf82-117">이 메서드는 매핑을 수도 수 로드 되었을 런타임에 있는 형식을 나타내는 ICorDebugType에서 제공 된 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), 런타임에 로드 형식을 식별 하는 불투명으로 사용 하는 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="baf82-118">경우는 ICorDebugType 나타내는 형식이 아직이 메서드가 반환 로드 `CORDBG_E_CLASS_NOT_LOADED`합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="baf82-119">반환 형식을 지원 되지 않는 경우 `CORDBG_E_UNSUPPORTED`합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf82-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="baf82-120">Requirements</span></span>  
 <span data-ttu-id="baf82-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="baf82-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf82-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baf82-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baf82-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf82-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf82-124">**.NET framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf82-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf82-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baf82-125">See Also</span></span>  
 [<span data-ttu-id="baf82-126">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baf82-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
