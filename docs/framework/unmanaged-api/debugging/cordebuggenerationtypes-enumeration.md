---
title: "CorDebugGenerationTypes 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGenerationTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGenerationTypes
helpviewer_keywords: CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: adefc0de4ba09419660c214df75365c90ec2c66e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="bd1d3-102">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="bd1d3-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="bd1d3-103">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd1d3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="bd1d3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bd1d3-105">Members</span></span>  
  
|<span data-ttu-id="bd1d3-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="bd1d3-106">Member name</span></span>|<span data-ttu-id="bd1d3-107">설명</span><span class="sxs-lookup"><span data-stu-id="bd1d3-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="bd1d3-108">0세대.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="bd1d3-109">1세대.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="bd1d3-110">2세대.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="bd1d3-111">큰 개체 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd1d3-112">설명</span><span class="sxs-lookup"><span data-stu-id="bd1d3-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1d3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd1d3-113">Requirements</span></span>  
 <span data-ttu-id="bd1d3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1d3-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd1d3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd1d3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd1d3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd1d3-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1d3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1d3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd1d3-118">See Also</span></span>  
 [<span data-ttu-id="bd1d3-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="bd1d3-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
