---
title: CorDebugCreateProcessFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fdc37676bfae8ac90fde0a7a5b11037b8357e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403759"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="b65e2-102">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="b65e2-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="b65e2-103">에 대 한 호출에서 사용할 수 있는 추가 디버깅 옵션을 제공 된 [icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b65e2-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b65e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b65e2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b65e2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b65e2-105">Members</span></span>  
  
|<span data-ttu-id="b65e2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b65e2-106">Member</span></span>|<span data-ttu-id="b65e2-107">설명</span><span class="sxs-lookup"><span data-stu-id="b65e2-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="b65e2-108">특별 한 옵션 없이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b65e2-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b65e2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b65e2-109">Requirements</span></span>  
 <span data-ttu-id="b65e2-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b65e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65e2-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b65e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b65e2-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b65e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b65e2-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65e2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b65e2-114">See Also</span></span>  
 [<span data-ttu-id="b65e2-115">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b65e2-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
