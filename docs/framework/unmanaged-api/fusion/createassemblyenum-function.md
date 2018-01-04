---
title: "CreateAssemblyEnum 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3719da442b2c2c589772a0bc19cec3efb4e6dace
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="53d19-102">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="53d19-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="53d19-103">에 대 한 포인터를 가져옵니다는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 지정 된 어셈블리에 있는 개체를 열거할 수 있는 인스턴스 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d19-104">구문</span><span class="sxs-lookup"><span data-stu-id="53d19-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53d19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53d19-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="53d19-106">[out] 요청 된 포함 된 메모리 위치에 대 한 포인터 `IAssemblyEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="53d19-107">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="53d19-108">`pUnkReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="53d19-109">[in] `IAssemblyName` 요청된 된 어셈블리의 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="53d19-110">이 이름은 열거형 필터링 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="53d19-111">전역 어셈블리 캐시의 모든 어셈블리를 열거 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="53d19-112">[in] 열거자의 동작을 수정 하기 위한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="53d19-113">이 매개 변수에 포함에서 정확히 하나의 비트만 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="53d19-114">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="53d19-115">`pvReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53d19-116">설명</span><span class="sxs-lookup"><span data-stu-id="53d19-116">Remarks</span></span>  
 <span data-ttu-id="53d19-117">`dwFlags` 에서 정확히 한 비트를 포함 하는 매개 변수는 `ASM_CACHE_FLAGS` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d19-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53d19-118">Requirements</span></span>  
 <span data-ttu-id="53d19-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53d19-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d19-120">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="53d19-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="53d19-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="53d19-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53d19-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d19-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d19-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53d19-123">See Also</span></span>  
 [<span data-ttu-id="53d19-124">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53d19-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="53d19-125">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53d19-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="53d19-126">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="53d19-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
