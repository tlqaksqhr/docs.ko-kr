---
title: IApartmentCallback::DoCallback 메서드
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba1dc2a1ec8b0b3b5ec25036cab6362237efe98f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430758"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="90003-102">IApartmentCallback::DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="90003-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="90003-103">아파트 내에서 지정된 된 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="90003-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90003-104">구문</span><span class="sxs-lookup"><span data-stu-id="90003-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90003-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90003-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="90003-106">[in] 아파트 내에서 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90003-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="90003-107">[in] 함수의 인수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90003-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90003-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90003-108">Requirements</span></span>  
 <span data-ttu-id="90003-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90003-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90003-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90003-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90003-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="90003-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90003-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90003-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90003-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90003-113">See Also</span></span>  
 [<span data-ttu-id="90003-114">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90003-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
