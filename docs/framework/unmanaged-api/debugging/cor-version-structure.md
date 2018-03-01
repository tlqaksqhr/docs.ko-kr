---
title: "COR_VERSION 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b527cb9175315af98a9ad4e9be06d459ad6e188e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corversion-structure"></a><span data-ttu-id="a0734-102">COR_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="a0734-102">COR_VERSION Structure</span></span>
<span data-ttu-id="a0734-103">공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0734-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0734-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="a0734-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a0734-105">Members</span></span>  
  
|<span data-ttu-id="a0734-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a0734-106">Member</span></span>|<span data-ttu-id="a0734-107">설명</span><span class="sxs-lookup"><span data-stu-id="a0734-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="a0734-108">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="a0734-109">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="a0734-110">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="a0734-111">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0734-112">설명</span><span class="sxs-lookup"><span data-stu-id="a0734-112">Remarks</span></span>  
 <span data-ttu-id="a0734-113">버전 번호가 1.0.3705.288 이면 1은 주 버전 번호, 0은 부 버전 번호, 3705는 빌드 번호 및 288는 하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0734-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0734-114">Requirements</span></span>  
 <span data-ttu-id="a0734-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0734-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0734-116">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a0734-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a0734-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0734-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0734-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0734-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0734-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0734-119">See Also</span></span>  
 [<span data-ttu-id="a0734-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="a0734-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a0734-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="a0734-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
