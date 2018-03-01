---
title: "GetAppIdAuthority 함수"
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
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e89624feb04050534b917b865d5cb53b8c4cf58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getappidauthority-function"></a><span data-ttu-id="6e951-102">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="6e951-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="6e951-103">에 대 한 포인터를 가져옵니다는 [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) 응용 프로그램 id 및 참조에 대 한 키를 관리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e951-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e951-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e951-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e951-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e951-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="6e951-106">[out] 반환 된 `IAppIdAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e951-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e951-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e951-107">Requirements</span></span>  
 <span data-ttu-id="6e951-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e951-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e951-109">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="6e951-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6e951-110">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e951-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e951-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e951-111">See Also</span></span>  
 [<span data-ttu-id="6e951-112">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e951-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="6e951-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6e951-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
