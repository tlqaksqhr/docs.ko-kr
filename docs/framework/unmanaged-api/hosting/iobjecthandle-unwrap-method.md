---
title: "IObjectHandle::Unwrap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IObjectHandle.Unwrap
api_location: mscoree.dll
api_type: COM
f1_keywords: Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b14483279e4416c898a836ae87c6bca180b4736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="c6239-102">IObjectHandle::Unwrap 메서드</span><span class="sxs-lookup"><span data-stu-id="c6239-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="c6239-103">간접 참조에서 값 방식 마샬링 개체 래핑 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6239-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6239-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6239-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6239-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6239-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="c6239-106">[out] 래핑 해제할 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6239-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6239-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6239-107">Requirements</span></span>  
 <span data-ttu-id="c6239-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6239-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6239-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6239-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6239-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c6239-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6239-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6239-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6239-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6239-112">See Also</span></span>  
 
