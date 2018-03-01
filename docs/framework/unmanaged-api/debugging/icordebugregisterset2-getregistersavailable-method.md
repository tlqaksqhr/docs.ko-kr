---
title: "ICorDebugRegisterSet2::GetRegistersAvailable 메서드"
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
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="86bf6-102">ICorDebugRegisterSet2::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="86bf6-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="86bf6-103">사용 가능한 레지스터의 비트맵을 제공 하는 바이트의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86bf6-104">구문</span><span class="sxs-lookup"><span data-stu-id="86bf6-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86bf6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86bf6-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="86bf6-106">[in] `availableRegChunks` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="86bf6-107">[out] 바이트 배열 인 각 비트를 레지스터에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="86bf6-108">레지스터를 사용할 수 있는 레지스터의 해당 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86bf6-109">설명</span><span class="sxs-lookup"><span data-stu-id="86bf6-109">Remarks</span></span>  
 <span data-ttu-id="86bf6-110">CorDebugRegister 열거형의 값 다른 마이크로프로세서의 레지스터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="86bf6-111">각 값의 상위 5 개 비트에 대 한 인덱스는는 `availableRegChunks` 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="86bf6-112">각 값의 하위 3 비트 인덱싱된 바이트에서 비트 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="86bf6-113">지정 된 `CorDebugRegister` 특정 레지스터를 마스크의 레지스터의 위치를 지정 하는 값은 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="86bf6-114">추출 정확한 바이트에 액세스 하는 데 필요한 인덱스는 `availableRegChunks` 배열:</span><span class="sxs-lookup"><span data-stu-id="86bf6-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="86bf6-115">`CorDebugRegister`값 >> 3</span><span class="sxs-lookup"><span data-stu-id="86bf6-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="86bf6-116">인덱싱된 바이트에서 비트 위치 0 비트는 최하위 비트를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="86bf6-117">`CorDebugRegister`값 및 7</span><span class="sxs-lookup"><span data-stu-id="86bf6-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86bf6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86bf6-118">Requirements</span></span>  
 <span data-ttu-id="86bf6-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="86bf6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86bf6-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86bf6-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86bf6-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86bf6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86bf6-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86bf6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bf6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86bf6-123">See Also</span></span>  
 [<span data-ttu-id="86bf6-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86bf6-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="86bf6-125">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86bf6-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
