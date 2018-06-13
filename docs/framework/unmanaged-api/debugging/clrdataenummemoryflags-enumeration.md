---
title: CLRDataEnumMemoryFlags 열거형
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a19c6f22ee9fbe7eb1019a0b799d63e4ee650e98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406821"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="3fed3-102">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3fed3-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="3fed3-103">메모리 영역에 대 한 호출을 나타냅니다는 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메서드가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fed3-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fed3-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fed3-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3fed3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3fed3-105">Members</span></span>  
  
|<span data-ttu-id="3fed3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3fed3-106">Member</span></span>|<span data-ttu-id="3fed3-107">설명</span><span class="sxs-lookup"><span data-stu-id="3fed3-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="3fed3-108">미니 덤프, 즉 스파스 메모리 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fed3-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="3fed3-109">전체 힙 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fed3-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3fed3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fed3-110">Requirements</span></span>  
 <span data-ttu-id="3fed3-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fed3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fed3-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3fed3-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3fed3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fed3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fed3-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fed3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fed3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fed3-115">See Also</span></span>  
 [<span data-ttu-id="3fed3-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="3fed3-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
