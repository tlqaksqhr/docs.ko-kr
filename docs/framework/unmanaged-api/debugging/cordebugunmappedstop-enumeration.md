---
title: "CorDebugUnmappedStop 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUnmappedStop
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUnmappedStop
helpviewer_keywords: CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e75c827533a921c4cab31b2e8b0996dffa532fe2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="5ed69-102">CorDebugUnmappedStop 열거형</span><span class="sxs-lookup"><span data-stu-id="5ed69-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="5ed69-103">스텝퍼에 의해 코드 실행에서 중지를 트리거할 수 있는 매핑되지 않은 코드 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed69-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ed69-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="5ed69-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5ed69-105">Members</span></span>  
  
|<span data-ttu-id="5ed69-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5ed69-106">Member</span></span>|<span data-ttu-id="5ed69-107">설명</span><span class="sxs-lookup"><span data-stu-id="5ed69-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="5ed69-108">모든 유형의 매핑되지 않은 코드에서 중지 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5ed69-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="5ed69-109">프롤로그 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="5ed69-110">에필로그 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="5ed69-111">매핑 정보가 없는 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="5ed69-112">프롤로그, 에필로그, 아니요-매핑 정보 또는 관리 되지 않는 범주에 맞지 않는 매핑되지 않은 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="5ed69-113">비관리 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-113">Stop in unmanaged code.</span></span> <span data-ttu-id="5ed69-114">이 값은 interop 디버깅에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="5ed69-115">모든 유형의 매핑되지 않은 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ed69-116">설명</span><span class="sxs-lookup"><span data-stu-id="5ed69-116">Remarks</span></span>  
 <span data-ttu-id="5ed69-117">사용 하 여 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 스텝 퍼 멈춥니다 매핑되지 않은 코드를 지정 하는 플래그를 설정 하는 방법은 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ed69-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ed69-118">Requirements</span></span>  
 <span data-ttu-id="5ed69-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed69-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ed69-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ed69-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ed69-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ed69-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ed69-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ed69-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed69-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ed69-123">See Also</span></span>  
 [<span data-ttu-id="5ed69-124">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="5ed69-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
