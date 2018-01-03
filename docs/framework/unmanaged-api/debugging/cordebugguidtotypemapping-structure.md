---
title: "CorDebugGuidToTypeMapping 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugGuidToTypeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGuidToTypeMapping
helpviewer_keywords: CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecdadc96c0fb850fef13ba978fc97eef91dadd65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="e1551-102">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="e1551-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="e1551-103">지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 해당 ICorDebugType 개체 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="e1551-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1551-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1551-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e1551-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e1551-105">Members</span></span>  
  
|<span data-ttu-id="e1551-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1551-106">Member</span></span>|<span data-ttu-id="e1551-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1551-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="e1551-108">캐시 된 GUID [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e1551-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="e1551-109">캐시 된 유형에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1551-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1551-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1551-110">Requirements</span></span>  
 <span data-ttu-id="e1551-111">**플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e1551-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="e1551-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1551-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1551-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1551-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1551-114">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1551-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1551-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1551-115">See Also</span></span>  
 [<span data-ttu-id="e1551-116">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="e1551-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e1551-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="e1551-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
