---
title: "CorDebugIlToNativeMappingTypes 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIlToNativeMappingTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIlToNativeMappingTypes
helpviewer_keywords: CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03046ebb678df64ad3d151aaadba313645417979
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="b6740-102">CorDebugIlToNativeMappingTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="b6740-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="b6740-103">COR_DEBUG_IL_TO_NATIVE_MAP 구조체의 인스턴스로 표시 되는 기본 명령의 특정 범위가 특수 코드 영역에 해당 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6740-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6740-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6740-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="b6740-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b6740-105">Members</span></span>  
  
|<span data-ttu-id="b6740-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b6740-106">Member</span></span>|<span data-ttu-id="b6740-107">설명</span><span class="sxs-lookup"><span data-stu-id="b6740-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="b6740-108">네이티브 명령의 범위가 특수 코드 영역에 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6740-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="b6740-109">네이티브 명령 범위는 프롤로그에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b6740-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="b6740-110">네이티브 명령 범위는 에필로그에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b6740-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6740-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6740-111">Requirements</span></span>  
 <span data-ttu-id="b6740-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6740-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6740-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6740-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6740-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6740-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6740-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6740-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6740-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6740-116">See Also</span></span>  
 [<span data-ttu-id="b6740-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="b6740-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="b6740-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b6740-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
