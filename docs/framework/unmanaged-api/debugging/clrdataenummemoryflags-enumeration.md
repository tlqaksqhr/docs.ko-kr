---
title: "CLRDataEnumMemoryFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataEnumMemoryFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLRDataEnumMemoryFlags
helpviewer_keywords: CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c88fe4e6bcbe4f2ec3f13c08450f7dea44ccdbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="6e963-102">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6e963-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="6e963-103">메모리 영역에 대 한 호출을 나타냅니다는 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메서드가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e963-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e963-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6e963-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6e963-105">Members</span></span>  
  
|<span data-ttu-id="6e963-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6e963-106">Member</span></span>|<span data-ttu-id="6e963-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e963-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="6e963-108">미니 덤프, 즉 스파스 메모리 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="6e963-109">전체 힙 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e963-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e963-110">Requirements</span></span>  
 <span data-ttu-id="6e963-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e963-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6e963-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6e963-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e963-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e963-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e963-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e963-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e963-115">See Also</span></span>  
 [<span data-ttu-id="6e963-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6e963-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
