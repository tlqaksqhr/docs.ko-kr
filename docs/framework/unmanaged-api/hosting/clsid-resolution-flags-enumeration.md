---
title: "CLSID_RESOLUTION_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLSID_RESOLUTION_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: CLSID_RESOLUTION_FLAGS
helpviewer_keywords: CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17e74e8b39ff9079973063f4ea703607411ab93d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="0362b-102">CLSID_RESOLUTION_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="0362b-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="0362b-103">공용 언어 런타임 (CLR) 확인 하는 방법을 나타내는 값을 포함 한 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="0362b-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0362b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0362b-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0362b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0362b-105">Members</span></span>  
  
|<span data-ttu-id="0362b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0362b-106">Member</span></span>|<span data-ttu-id="0362b-107">설명</span><span class="sxs-lookup"><span data-stu-id="0362b-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="0362b-108">기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0362b-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="0362b-109">런타임에서 레지스트리를 검색 하 고 shim 정책을 적용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0362b-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0362b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0362b-110">Requirements</span></span>  
 <span data-ttu-id="0362b-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0362b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0362b-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0362b-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0362b-113">**.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0362b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0362b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0362b-114">See Also</span></span>  
 [<span data-ttu-id="0362b-115">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="0362b-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
