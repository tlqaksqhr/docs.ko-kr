---
title: "CorDebugMappingResult 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMappingResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMappingResult
helpviewer_keywords: CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 793158ef63a0de27786dc8bd9b306f10c228054e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="444b0-102">CorDebugMappingResult 열거형</span><span class="sxs-lookup"><span data-stu-id="444b0-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="444b0-103">IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="444b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="444b0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="444b0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="444b0-105">Members</span></span>  
  
|<span data-ttu-id="444b0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="444b0-106">Member</span></span>|<span data-ttu-id="444b0-107">설명</span><span class="sxs-lookup"><span data-stu-id="444b0-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="444b0-108">네이티브 코드는 프롤로그에 이므로 IP의 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="444b0-109">네이티브 코드는 에필로그는 IP의 값은 메서드의 마지막 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="444b0-110">매핑 정보가 없는 방법에 대해 사용할 수 있는 이므로 IP의 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="444b0-111">메서드에 대 한 매핑 정보를는 없지만 현재 주소 Microsoft MSIL (intermediate language) 코드에 매핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="444b0-112">IP의 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="444b0-113">MSIL 코드에 정확히 메서드가 매핑되어 있거나 프레임 IP의 값은 정확 하 게 해석 되었으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="444b0-114">메서드가 성공적으로 매핑한, 되지만 IP의 값은 근사치일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="444b0-115">설명</span><span class="sxs-lookup"><span data-stu-id="444b0-115">Remarks</span></span>  
 <span data-ttu-id="444b0-116">사용할 수는 [icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) 메서드 명령 포인터의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444b0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="444b0-117">Requirements</span></span>  
 <span data-ttu-id="444b0-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="444b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444b0-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="444b0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="444b0-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="444b0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="444b0-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="444b0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444b0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="444b0-122">See Also</span></span>  
 [<span data-ttu-id="444b0-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="444b0-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
