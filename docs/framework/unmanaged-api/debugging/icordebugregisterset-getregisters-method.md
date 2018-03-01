---
title: "ICorDebugRegisterSet::GetRegisters 메서드"
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
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ddefb1ac5694bf1f213dd77e0ffc7f746b7e62cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="983fc-102">ICorDebugRegisterSet::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="983fc-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="983fc-103">(현재 코드를 실행 하는 컴퓨터)에서 각 레지스터의 값을 가져옵니다는 비트 마스크에 의해 지정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="983fc-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="983fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="983fc-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="983fc-106">[in] 검색할 값은 어느 레지스터를 지정 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="983fc-107">각 비트를 레지스터에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="983fc-108">약간 1로 설정 되 면 레지스터의 값이 검색 됩니다. 그렇지 않으면 레지스터의 값은 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="983fc-109">[in] 레지스터 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="983fc-110">[out] 배열 `CORDB_REGISTER` 각각 수신 하는 레지스터의 값 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="983fc-111">설명</span><span class="sxs-lookup"><span data-stu-id="983fc-111">Remarks</span></span>  
 <span data-ttu-id="983fc-112">배열의 크기는 비트 마스크에 1로 설정 된 비트 수와 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="983fc-113">`regCount` 매개 변수 레지스터 값을 받을 버퍼에서 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="983fc-114">경우는 `regCount` 값이 너무 작아서 마스크에 의해 지정 된 레지스터 수에 대 한, 레지스터 집합에서 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="983fc-115">경우는 `regCount` 값이 너무 커서는 사용 하지 않는 `regBuffer` 요소를 수정 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="983fc-116">비트 마스크를 사용할 수 있는 레지스터를 지정 하는 경우 `GetRegisters` 해당 레지스터에 대 한 비활성화 상태 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983fc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="983fc-117">Requirements</span></span>  
 <span data-ttu-id="983fc-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="983fc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983fc-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983fc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983fc-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983fc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983fc-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983fc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983fc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="983fc-122">See Also</span></span>  
 [<span data-ttu-id="983fc-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="983fc-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="983fc-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="983fc-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
