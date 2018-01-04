---
title: "VariableLocationType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: VariableLocationType
api_location: mscordbi.dll
api_type: COM
f1_keywords: VariableLocationType
helpviewer_keywords: VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ea476ef32b807823108aa2836778da576618214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="19e9a-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="19e9a-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="19e9a-103">기본 위치에 대 한 유형을 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19e9a-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19e9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="19e9a-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="19e9a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="19e9a-105">Members</span></span>  
  
|<span data-ttu-id="19e9a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="19e9a-106">Member</span></span>|<span data-ttu-id="19e9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="19e9a-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="19e9a-108">변수가 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="19e9a-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="19e9a-109">변수가 메모리 레지스터 상대 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="19e9a-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="19e9a-110">변수는 레지스터 또는 레지스터 상대 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19e9a-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19e9a-111">설명</span><span class="sxs-lookup"><span data-stu-id="19e9a-111">Remarks</span></span>  
 <span data-ttu-id="19e9a-112">멤버는 `VariableLocationType` 열거형에서 반환 되는 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="19e9a-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19e9a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19e9a-113">Requirements</span></span>  
 <span data-ttu-id="19e9a-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19e9a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e9a-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19e9a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19e9a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19e9a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19e9a-117">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e9a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e9a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19e9a-118">See Also</span></span>  
 [<span data-ttu-id="19e9a-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="19e9a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
