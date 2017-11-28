---
title: "COR_PRF_JIT_CACHE 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_JIT_CACHE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_JIT_CACHE
helpviewer_keywords: COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 08fe81321e958d61c1aae86ae366077b563dba3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="796f7-102">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="796f7-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="796f7-103">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="796f7-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="796f7-104">`COR_PRF_CACHED_FUNCTION_FOUND`값이 0 높으므로 `COR_PRF_JIT_CACHE` 를 부울 대신 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="796f7-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="796f7-105">구문</span><span class="sxs-lookup"><span data-stu-id="796f7-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="796f7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="796f7-106">Members</span></span>  
  
|<span data-ttu-id="796f7-107">멤버</span><span class="sxs-lookup"><span data-stu-id="796f7-107">Member</span></span>|<span data-ttu-id="796f7-108">설명</span><span class="sxs-lookup"><span data-stu-id="796f7-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="796f7-109">검색 함수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="796f7-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="796f7-110">검색 함수를 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="796f7-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="796f7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="796f7-111">Requirements</span></span>  
 <span data-ttu-id="796f7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="796f7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="796f7-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="796f7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="796f7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="796f7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="796f7-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="796f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796f7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="796f7-116">See Also</span></span>  
 [<span data-ttu-id="796f7-117">프로 파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="796f7-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
