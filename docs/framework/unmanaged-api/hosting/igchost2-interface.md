---
title: "IGCHost2 인터페이스"
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
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a616e724d6fb26734fcda48d6a9b39605e0284a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="aa673-102">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa673-102">IGCHost2 Interface</span></span>
<span data-ttu-id="aa673-103">가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa673-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa673-104">새 개발을 위해 사용 하는 권장는 [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) 대신 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa673-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa673-105">메서드</span><span class="sxs-lookup"><span data-stu-id="aa673-105">Methods</span></span>  
  
|<span data-ttu-id="aa673-106">메서드</span><span class="sxs-lookup"><span data-stu-id="aa673-106">Method</span></span>|<span data-ttu-id="aa673-107">설명</span><span class="sxs-lookup"><span data-stu-id="aa673-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa673-108">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="aa673-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="aa673-109">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa673-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="aa673-110">0 세대 및 세그먼트 크기 보다 큰 수 있도록 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa673-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa673-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa673-111">Requirements</span></span>  
 <span data-ttu-id="aa673-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa673-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa673-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="aa673-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="aa673-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="aa673-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa673-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa673-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa673-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa673-116">See Also</span></span>  
 [<span data-ttu-id="aa673-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa673-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="aa673-118">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa673-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="aa673-119">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="aa673-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
