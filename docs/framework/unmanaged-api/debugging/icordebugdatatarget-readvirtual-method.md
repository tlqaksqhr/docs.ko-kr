---
title: "ICorDebugDataTarget::ReadVirtual 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.ReadVirtual Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a406af14d4cb5612009972542c0efe9c1b5f62cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="cc9ed-102">ICorDebugDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="cc9ed-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="cc9ed-103">지정된 된 주소에서 시작 하는 인접 한 메모리 블록을 가져오고 제공된 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc9ed-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc9ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc9ed-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="cc9ed-106">[in] 요청 된 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="cc9ed-107">[out] 메모리를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="cc9ed-108">[in] 대상 주소에서 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="cc9ed-109">[out] 바이트 수가 대상 주소에서 실제로 읽는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="cc9ed-110">보다 적을 수 있습니다 `bytesRequested`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc9ed-111">설명</span><span class="sxs-lookup"><span data-stu-id="cc9ed-111">Remarks</span></span>  
 <span data-ttu-id="cc9ed-112">지정 된 시작 주소) (에서 첫 번째 바이트를 읽을 수 호출 성공 (자체 설명 되는 null로 끝나는 문자열 처럼의 길이와 데이터 구조를 효율적으로 읽을)를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc9ed-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc9ed-113">Requirements</span></span>  
 <span data-ttu-id="cc9ed-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc9ed-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc9ed-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc9ed-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc9ed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc9ed-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc9ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9ed-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc9ed-118">See Also</span></span>  
 [<span data-ttu-id="cc9ed-119">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc9ed-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="cc9ed-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc9ed-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cc9ed-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="cc9ed-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
