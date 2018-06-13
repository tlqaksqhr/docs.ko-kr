---
title: CorDebugGuidToTypeMapping 구조체
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c803a805da605bd52fd50eb1e292c0e277143d7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405261"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="e6a70-102">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="e6a70-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="e6a70-103">지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 해당 ICorDebugType 개체 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a70-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a70-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6a70-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e6a70-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e6a70-105">Members</span></span>  
  
|<span data-ttu-id="e6a70-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e6a70-106">Member</span></span>|<span data-ttu-id="e6a70-107">설명</span><span class="sxs-lookup"><span data-stu-id="e6a70-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="e6a70-108">캐시 된 GUID [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a70-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="e6a70-109">캐시 된 유형에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a70-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6a70-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6a70-110">Requirements</span></span>  
 <span data-ttu-id="e6a70-111">**플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a70-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="e6a70-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6a70-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6a70-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6a70-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6a70-114">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6a70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a70-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6a70-115">See Also</span></span>  
 [<span data-ttu-id="e6a70-116">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="e6a70-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e6a70-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="e6a70-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
