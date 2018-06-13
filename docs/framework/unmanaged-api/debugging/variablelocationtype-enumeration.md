---
title: VariableLocationType 열거형
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cc7a299e6be328095c0368acf0a4b767fb74d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423951"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="99b07-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="99b07-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="99b07-103">기본 위치에 대 한 유형을 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99b07-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b07-104">구문</span><span class="sxs-lookup"><span data-stu-id="99b07-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="99b07-105">멤버</span><span class="sxs-lookup"><span data-stu-id="99b07-105">Members</span></span>  
  
|<span data-ttu-id="99b07-106">멤버</span><span class="sxs-lookup"><span data-stu-id="99b07-106">Member</span></span>|<span data-ttu-id="99b07-107">설명</span><span class="sxs-lookup"><span data-stu-id="99b07-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="99b07-108">변수가 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="99b07-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="99b07-109">변수가 메모리 레지스터 상대 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="99b07-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="99b07-110">변수는 레지스터 또는 레지스터 상대 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99b07-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99b07-111">설명</span><span class="sxs-lookup"><span data-stu-id="99b07-111">Remarks</span></span>  
 <span data-ttu-id="99b07-112">멤버는 `VariableLocationType` 열거형에서 반환 되는 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="99b07-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99b07-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99b07-113">Requirements</span></span>  
 <span data-ttu-id="99b07-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99b07-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b07-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99b07-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99b07-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99b07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99b07-117">**.NET framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b07-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99b07-118">See Also</span></span>  
 [<span data-ttu-id="99b07-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="99b07-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
