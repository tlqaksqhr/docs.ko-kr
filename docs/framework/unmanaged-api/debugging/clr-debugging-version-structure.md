---
title: CLR_DEBUGGING_VERSION 구조체
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4be232ab557d582f3521b8775108c004b5a3dd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403307"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="a858b-102">CLR_DEBUGGING_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="a858b-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="a858b-103">디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a858b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a858b-104">Syntax</span></span>  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="a858b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a858b-105">Members</span></span>  
  
|<span data-ttu-id="a858b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a858b-106">Member</span></span>|<span data-ttu-id="a858b-107">설명</span><span class="sxs-lookup"><span data-stu-id="a858b-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="a858b-108">구조 버전 번호</span><span class="sxs-lookup"><span data-stu-id="a858b-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="a858b-109">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="a858b-110">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="a858b-111">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="a858b-112">수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a858b-113">설명</span><span class="sxs-lookup"><span data-stu-id="a858b-113">Remarks</span></span>  
 <span data-ttu-id="a858b-114">하지만 `CLR_DEBUGGING_VERSION` 구조체가 COR_VERSION 구조체와 동일, `CLR_DEBUGGING_VERSION` 추가 구조 버전 필드를 제공 하는 구조 (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="a858b-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="a858b-115">현재,이 필드를 0으로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a858b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a858b-116">Requirements</span></span>  
 <span data-ttu-id="a858b-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a858b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a858b-118">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a858b-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a858b-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a858b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a858b-120">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a858b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a858b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a858b-121">See Also</span></span>  
 [<span data-ttu-id="a858b-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="a858b-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a858b-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="a858b-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
