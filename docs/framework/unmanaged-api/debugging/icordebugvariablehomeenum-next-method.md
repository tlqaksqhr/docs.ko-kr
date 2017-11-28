---
title: "ICorDebugVariableHomeEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480317a4ec0515411f1ca8156a5bc4d06aa3f38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="108b7-102">ICorDebugVariableHomeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="108b7-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="108b7-103">지정된 된 수의 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 로컬 변수 및 인수는 함수에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="108b7-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="108b7-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="108b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="108b7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="108b7-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="108b7-107">각각 가리키는 포인터의 배열은 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 지역 변수 또는 함수 '의 인수에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="108b7-108">[out] 개체에 실제로 반환 된 인스턴스 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="108b7-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="108b7-109">Return Value</span></span>  
 <span data-ttu-id="108b7-110">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="108b7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="108b7-111">HRESULT</span></span>|<span data-ttu-id="108b7-112">설명</span><span class="sxs-lookup"><span data-stu-id="108b7-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="108b7-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="108b7-114">실제 인스턴스 수 검색에 반영 된 대로 `pceltFetched`, 요청 된 인스턴스의 수보다 적습니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="108b7-115">설명</span><span class="sxs-lookup"><span data-stu-id="108b7-115">Remarks</span></span>  
 <span data-ttu-id="108b7-116">[ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) 메서드 검색 최대 `celt` 열거자의 현재 위치부터 시작 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="108b7-117">메서드가 반환 될 때 `pceltFetched` 검색 된 개체의 실제 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108b7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="108b7-118">Requirements</span></span>  
 <span data-ttu-id="108b7-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="108b7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108b7-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="108b7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="108b7-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108b7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108b7-122">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108b7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108b7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="108b7-123">See Also</span></span>  
 [<span data-ttu-id="108b7-124">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="108b7-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [<span data-ttu-id="108b7-125">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="108b7-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
