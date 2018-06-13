---
title: CorDebugGCType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e74f564a483d80fd6312cf015802750d48e73ca7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403996"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="23bd5-102">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="23bd5-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="23bd5-103">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23bd5-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23bd5-104">구문</span><span class="sxs-lookup"><span data-stu-id="23bd5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23bd5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23bd5-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="23bd5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="23bd5-106">Members</span></span>  
  
|<span data-ttu-id="23bd5-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="23bd5-107">Member name</span></span>|<span data-ttu-id="23bd5-108">설명</span><span class="sxs-lookup"><span data-stu-id="23bd5-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="23bd5-109">워크스테이션에서 가비지 수집기가 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="23bd5-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="23bd5-110">가비지 수집기는 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23bd5-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23bd5-111">설명</span><span class="sxs-lookup"><span data-stu-id="23bd5-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23bd5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23bd5-112">Requirements</span></span>  
 <span data-ttu-id="23bd5-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23bd5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23bd5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23bd5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23bd5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23bd5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23bd5-116">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23bd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bd5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23bd5-117">See Also</span></span>  
 [<span data-ttu-id="23bd5-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="23bd5-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
