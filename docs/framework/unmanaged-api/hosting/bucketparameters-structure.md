---
title: "BucketParameters 구조체"
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
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9db30133a01877c6ae048b9152f35b066219aa22
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="b7e07-102">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="b7e07-102">BucketParameters Structure</span></span>
<span data-ttu-id="b7e07-103">이벤트와 연결 된 현재 예외에 대 한 이벤트 및 매개 변수 형식 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e07-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e07-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7e07-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="b7e07-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b7e07-105">Members</span></span>  
  
|<span data-ttu-id="b7e07-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b7e07-106">Member</span></span>|<span data-ttu-id="b7e07-107">설명</span><span class="sxs-lookup"><span data-stu-id="b7e07-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="b7e07-108">`true`를이 구조의 나머지 올바른지 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e07-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="b7e07-109">이벤트 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e07-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="b7e07-110">이벤트와 연결 된 현재 예외에 대 한 매개 변수를 지정 하며 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e07-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7e07-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7e07-111">Requirements</span></span>  
 <span data-ttu-id="b7e07-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e07-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e07-113">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b7e07-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b7e07-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7e07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e07-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7e07-115">See Also</span></span>  
 [<span data-ttu-id="b7e07-116">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="b7e07-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
