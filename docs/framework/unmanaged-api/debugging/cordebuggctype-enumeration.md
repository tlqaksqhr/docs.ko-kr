---
title: "CorDebugGCType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGCType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGCType
helpviewer_keywords: CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14d6f28c2e5fa356c7f406ffb4c2787f0ace500a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="fc832-102">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="fc832-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="fc832-103">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc832-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc832-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc832-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc832-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc832-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="fc832-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fc832-106">Members</span></span>  
  
|<span data-ttu-id="fc832-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="fc832-107">Member name</span></span>|<span data-ttu-id="fc832-108">설명</span><span class="sxs-lookup"><span data-stu-id="fc832-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="fc832-109">워크스테이션에서 가비지 수집기가 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="fc832-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="fc832-110">가비지 수집기는 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc832-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc832-111">설명</span><span class="sxs-lookup"><span data-stu-id="fc832-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc832-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc832-112">Requirements</span></span>  
 <span data-ttu-id="fc832-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc832-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc832-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc832-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc832-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc832-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc832-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc832-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc832-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc832-117">See Also</span></span>  
 [<span data-ttu-id="fc832-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="fc832-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
