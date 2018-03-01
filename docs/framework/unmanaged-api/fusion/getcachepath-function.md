---
title: "GetCachePath 함수"
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
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 371dab83d7441681b9d6bd5723bcd8c3caadb50e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getcachepath-function"></a><span data-ttu-id="8f522-102">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="8f522-102">GetCachePath Function</span></span>
<span data-ttu-id="8f522-103">지정된 된 플래그를 사용 하 여 캐시 된 어셈블리에 경로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f522-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f522-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f522-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f522-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f522-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="8f522-106">[in] [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 캐시 된 어셈블리의 소스를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f522-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="8f522-107">[out] 반환 된 포인터의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8f522-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="8f522-108">[out에서] 요청 된 최대 길이 `pwzCachePath`, 및의 실제 길이 반환 시 `pwzCachePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f522-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f522-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f522-109">Requirements</span></span>  
 <span data-ttu-id="8f522-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f522-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f522-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8f522-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8f522-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f522-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f522-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f522-113">See Also</span></span>  
 [<span data-ttu-id="8f522-114">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="8f522-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [<span data-ttu-id="8f522-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8f522-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
