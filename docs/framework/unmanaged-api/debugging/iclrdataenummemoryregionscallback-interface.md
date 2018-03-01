---
title: "ICLRDataEnumMemoryRegionsCallback 인터페이스"
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
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 091f5345461ebe5054e769ae9d051ef2e0737ffb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="0b356-102">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b356-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="0b356-103">에 대 한 콜백 메서드를 제공 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메모리의 지정된 된 영역을 열거 하는 시도의 결과 디버거에 보고 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b356-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b356-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0b356-104">Methods</span></span>  
  
|<span data-ttu-id="0b356-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0b356-105">Method</span></span>|<span data-ttu-id="0b356-106">설명</span><span class="sxs-lookup"><span data-stu-id="0b356-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b356-107">EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="0b356-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="0b356-108">에 의해 호출 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메모리의 지정된 된 영역을 열거 하는 시도의 결과 디버거에 보고 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b356-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b356-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b356-109">Requirements</span></span>  
 <span data-ttu-id="0b356-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b356-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b356-111">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0b356-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0b356-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b356-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b356-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b356-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b356-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b356-114">See Also</span></span>  
 [<span data-ttu-id="0b356-115">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b356-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
