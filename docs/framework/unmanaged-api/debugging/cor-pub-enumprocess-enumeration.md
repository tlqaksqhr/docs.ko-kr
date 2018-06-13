---
title: COR_PUB_ENUMPROCESS 열거형
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcdb5883e109d7e0c73c8fb76ee61b52cf23091f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407003"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="f6704-102">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="f6704-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="f6704-103">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f6704-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6704-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6704-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="f6704-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f6704-105">Members</span></span>  
  
|<span data-ttu-id="f6704-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="f6704-106">Member name</span></span>|<span data-ttu-id="f6704-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6704-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="f6704-108">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="f6704-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6704-109">설명</span><span class="sxs-lookup"><span data-stu-id="f6704-109">Remarks</span></span>  
 <span data-ttu-id="f6704-110">관리 되지 않는 디버깅 API의 현재 버전 관리 프로세스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6704-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6704-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6704-111">Requirements</span></span>  
 <span data-ttu-id="f6704-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6704-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6704-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f6704-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f6704-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6704-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6704-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6704-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6704-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6704-116">See Also</span></span>  
 [<span data-ttu-id="f6704-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="f6704-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
