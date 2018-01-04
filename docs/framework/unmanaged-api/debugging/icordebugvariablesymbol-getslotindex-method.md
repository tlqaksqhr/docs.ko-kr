---
title: "ICorDebugVariableSymbol::GetSlotIndex 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abb84e529768e0be44883511bb89703a4c3199df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="e70d4-102">ICorDebugVariableSymbol::GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="e70d4-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="e70d4-103">지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e70d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="e70d4-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e70d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e70d4-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="e70d4-106">[out] 지역 변수의 슬롯 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e70d4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e70d4-107">Return Value</span></span>  
 <span data-ttu-id="e70d4-108">성공하는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-108">`S_OK` if successful.</span></span> <span data-ttu-id="e70d4-109">변수가 함수 인수인 경우 `E_FAIL`입니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e70d4-110">설명</span><span class="sxs-lookup"><span data-stu-id="e70d4-110">Remarks</span></span>  
 <span data-ttu-id="e70d4-111">지역 변수의 관리되는 슬롯 인덱스를 사용하여 변수의 메타데이터 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e70d4-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e70d4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e70d4-113">Requirements</span></span>  
 <span data-ttu-id="e70d4-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e70d4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e70d4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e70d4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e70d4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e70d4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e70d4-117">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e70d4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70d4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e70d4-118">See Also</span></span>  
 [<span data-ttu-id="e70d4-119">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e70d4-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="e70d4-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e70d4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
