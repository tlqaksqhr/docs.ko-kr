---
title: "COR_PRF_RUNTIME_TYPE 열거형"
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
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 154773e76046656e4286f4ba12717b6b45e9b069
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="c6f61-102">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="c6f61-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="c6f61-103">공용 언어 런타임 (CLR)의 버전을 나타내는 값을 포함: 데스크톱 또는 Silverlight에서 사용 되는 CoreCLR 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f61-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f61-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6f61-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="c6f61-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c6f61-105">Members</span></span>  
  
|<span data-ttu-id="c6f61-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c6f61-106">Member</span></span>|<span data-ttu-id="c6f61-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6f61-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="c6f61-108">CLR의 데스크톱 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c6f61-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="c6f61-109">Silverlight에서 사용 되는 CLR의 핵심 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c6f61-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6f61-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6f61-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f61-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6f61-111">Requirements</span></span>  
 <span data-ttu-id="c6f61-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f61-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f61-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6f61-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6f61-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6f61-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f61-115">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f61-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f61-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6f61-116">See Also</span></span>  
 [<span data-ttu-id="c6f61-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="c6f61-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
