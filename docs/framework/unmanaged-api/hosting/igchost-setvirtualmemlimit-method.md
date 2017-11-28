---
title: "IGCHost::SetVirtualMemLimit 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetVirtualMemLimit
api_location: mscoree.dll
api_type: COM
f1_keywords: SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff3b5a8ba559530561503a3678a37ac0b9480907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="fb194-102">IGCHost::SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="fb194-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="fb194-103">런타임 가상 메모리의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb194-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb194-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb194-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb194-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb194-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="fb194-106">[in] (메가바이트) 런타임 가상 메모리의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fb194-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb194-107">설명</span><span class="sxs-lookup"><span data-stu-id="fb194-107">Remarks</span></span>  
 <span data-ttu-id="fb194-108">런타임 가상 메모리의 최대 크기를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb194-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb194-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb194-109">Requirements</span></span>  
 <span data-ttu-id="fb194-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb194-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb194-111">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="fb194-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fb194-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fb194-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb194-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb194-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb194-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb194-114">See Also</span></span>  
 [<span data-ttu-id="fb194-115">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb194-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
