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
ms.openlocfilehash: 5d4ff12674fefbde6afbbe76cb411dbbe33d2187
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="90e94-102">IObjectHandle::Unwrap 메서드</span><span class="sxs-lookup"><span data-stu-id="90e94-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="90e94-103">간접 참조에서 값 방식 마샬링 개체 래핑 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90e94-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e94-104">구문</span><span class="sxs-lookup"><span data-stu-id="90e94-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90e94-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90e94-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="90e94-106">[out] 래핑 해제할 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90e94-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e94-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90e94-107">Requirements</span></span>  
 <span data-ttu-id="90e94-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90e94-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e94-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90e94-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90e94-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="90e94-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90e94-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e94-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e94-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90e94-112">See Also</span></span>  
 
