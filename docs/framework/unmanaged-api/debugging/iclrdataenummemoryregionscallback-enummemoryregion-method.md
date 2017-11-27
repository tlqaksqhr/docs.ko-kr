---
title: "ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b1897b18a8dcbb261a5041ca8b530b7877b910
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="056b0-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="056b0-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="056b0-103">에 의해 호출 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메모리의 지정된 된 영역을 열거 하는 시도의 결과 디버거에 보고 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="056b0-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="056b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="056b0-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="056b0-106">[in] 시작 주소를 열거할 수 있는 메모리 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="056b0-107">[in] 바이트 메모리 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="056b0-108">설명</span><span class="sxs-lookup"><span data-stu-id="056b0-108">Remarks</span></span>  
 <span data-ttu-id="056b0-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메모리 영역을 열거 하는 각 시도 후이 콜백 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="056b0-110">열거형에는이 메서드는 오류를 나타내는 HRESULT를 반환 하는 경우에 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="056b0-111">이 콜백은에서 보고 하는 지역 중복 되거나 겹쳐질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056b0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="056b0-112">Requirements</span></span>  
 <span data-ttu-id="056b0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="056b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056b0-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="056b0-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="056b0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="056b0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="056b0-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056b0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056b0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="056b0-117">See Also</span></span>  
 [<span data-ttu-id="056b0-118">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="056b0-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
