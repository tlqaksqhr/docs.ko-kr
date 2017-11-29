---
title: "GetIdentityAuthority 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: GetIdentityAuthority
helpviewer_keywords: GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1490efdc00c4f928d17bf172eecd5a3bed824193
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="3a206-102">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="3a206-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="3a206-103">에 대 한 포인터를 가져옵니다는 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) 코드 개체에 대 한 키를 관리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a206-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a206-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a206-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a206-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a206-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="3a206-106">[out] 반환 된 `IIdentityAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a206-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a206-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a206-107">Requirements</span></span>  
 <span data-ttu-id="3a206-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a206-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a206-109">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3a206-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3a206-110">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a206-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a206-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a206-111">See Also</span></span>  
 [<span data-ttu-id="3a206-112">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a206-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 [<span data-ttu-id="3a206-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="3a206-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
