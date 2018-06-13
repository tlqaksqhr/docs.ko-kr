---
title: CorDebugHandleType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2898f530fe3f9368778d0f854e8254f7b32d5293
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404939"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="d81b4-102">CorDebugHandleType 열거형</span><span class="sxs-lookup"><span data-stu-id="d81b4-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="d81b4-103">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d81b4-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="d81b4-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="d81b4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d81b4-105">Members</span></span>  
  
|<span data-ttu-id="d81b4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d81b4-106">Member</span></span>|<span data-ttu-id="d81b4-107">설명</span><span class="sxs-lookup"><span data-stu-id="d81b4-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="d81b4-108">핸들이 강하고, 개체에서 가비지 수집에서 회수 되 고 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d81b4-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="d81b4-109">핸들은는 하지 않는 개체에서 가비지 수집에서 회수 되 고 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81b4-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="d81b4-110">핸들은 개체가 수집할 때 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d81b4-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d81b4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d81b4-111">Requirements</span></span>  
 <span data-ttu-id="d81b4-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d81b4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81b4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d81b4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d81b4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d81b4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d81b4-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81b4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81b4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d81b4-116">See Also</span></span>  
 [<span data-ttu-id="d81b4-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d81b4-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
