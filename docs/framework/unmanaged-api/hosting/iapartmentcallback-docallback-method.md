---
title: "IApartmentCallback::DoCallback 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback.DoCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06aaab6d4ad7d33bbdc52a38c999cc925eee1666
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="8992d-102">IApartmentCallback::DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="8992d-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="8992d-103">아파트 내에서 지정된 된 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8992d-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8992d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8992d-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8992d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8992d-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="8992d-106">[in] 아파트 내에서 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8992d-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="8992d-107">[in] 함수의 인수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8992d-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8992d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8992d-108">Requirements</span></span>  
 <span data-ttu-id="8992d-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8992d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8992d-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8992d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8992d-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8992d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8992d-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8992d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8992d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8992d-113">See Also</span></span>  
 [<span data-ttu-id="8992d-114">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8992d-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
