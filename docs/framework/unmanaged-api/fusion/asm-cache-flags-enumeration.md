---
title: "ASM_CACHE_FLAGS 열거형"
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
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 87dce9a2daf7067409d78a9f389695b6b01f23c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="b9aa2-102">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="b9aa2-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="b9aa2-103">나타내는 어셈블리의 소스를 나타냅니다 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) 전역 어셈블리 캐시에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9aa2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9aa2-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b9aa2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b9aa2-105">Members</span></span>  
  
|<span data-ttu-id="b9aa2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b9aa2-106">Member</span></span>|<span data-ttu-id="b9aa2-107">설명</span><span class="sxs-lookup"><span data-stu-id="b9aa2-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="b9aa2-108">Ngen.exe를 사용 하 여 미리 컴파일된 어셈블리의 캐시를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="b9aa2-109">전역 어셈블리 캐시를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="b9aa2-110">필요에 따라 다운로드 된 또는 섀도 복사 된 어셈블리를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="b9aa2-111">나타냅니다는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) 함수 공용 언어 런타임 (CLR) 버전 2.0에 대 한 전역 어셈블리 캐시에 경로 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="b9aa2-112">에 대 한 호출의 경우에만 의미 있는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="b9aa2-113">나타냅니다는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) 함수 CLR 버전 4에 대 한 전역 어셈블리 캐시에 경로 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="b9aa2-114">에 대 한 호출의 경우에만 의미 있는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9aa2-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9aa2-115">Requirements</span></span>  
 <span data-ttu-id="b9aa2-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9aa2-117">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9aa2-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9aa2-118">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b9aa2-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9aa2-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9aa2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9aa2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9aa2-120">See Also</span></span>  
 [<span data-ttu-id="b9aa2-121">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="b9aa2-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="b9aa2-122">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9aa2-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="b9aa2-123">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="b9aa2-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
