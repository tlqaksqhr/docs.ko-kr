---
title: CreateAssemblyEnum 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2098d5d9ce1c01f232cf2904c1fd3e990dfbe2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432118"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="b21cd-102">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="b21cd-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="b21cd-103">에 대 한 포인터를 가져옵니다는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 지정 된 어셈블리에 있는 개체를 열거할 수 있는 인스턴스 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b21cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="b21cd-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b21cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b21cd-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="b21cd-106">[out] 요청 된 포함 된 메모리 위치에 대 한 포인터 `IAssemblyEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="b21cd-107">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b21cd-108">`pUnkReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="b21cd-109">[in] `IAssemblyName` 요청된 된 어셈블리의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="b21cd-110">이 이름은 열거형 필터링 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="b21cd-111">전역 어셈블리 캐시의 모든 어셈블리를 열거 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b21cd-112">[in] 열거자의 동작을 수정 하기 위한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="b21cd-113">이 매개 변수에 포함에서 정확히 하나의 비트만 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b21cd-114">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b21cd-115">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b21cd-116">설명</span><span class="sxs-lookup"><span data-stu-id="b21cd-116">Remarks</span></span>  
 <span data-ttu-id="b21cd-117">`dwFlags` 에서 정확히 한 비트를 포함 하는 매개 변수는 `ASM_CACHE_FLAGS` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b21cd-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b21cd-118">Requirements</span></span>  
 <span data-ttu-id="b21cd-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b21cd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b21cd-120">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b21cd-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b21cd-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b21cd-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b21cd-122">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b21cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21cd-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b21cd-123">See Also</span></span>  
 [<span data-ttu-id="b21cd-124">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b21cd-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="b21cd-125">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b21cd-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="b21cd-126">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b21cd-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
