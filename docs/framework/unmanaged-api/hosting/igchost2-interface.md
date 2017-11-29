---
title: "IGCHost2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2
helpviewer_keywords: IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6706696e3fd5158d2b49a4d114d978a26510b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="69584-102">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69584-102">IGCHost2 Interface</span></span>
<span data-ttu-id="69584-103">가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="69584-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69584-104">새 개발을 위해 사용 하는 권장는 [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) 대신 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="69584-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69584-105">메서드</span><span class="sxs-lookup"><span data-stu-id="69584-105">Methods</span></span>  
  
|<span data-ttu-id="69584-106">메서드</span><span class="sxs-lookup"><span data-stu-id="69584-106">Method</span></span>|<span data-ttu-id="69584-107">설명</span><span class="sxs-lookup"><span data-stu-id="69584-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69584-108">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="69584-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="69584-109">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69584-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="69584-110">0 세대 및 세그먼트 크기 보다 큰 수 있도록 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="69584-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69584-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69584-111">Requirements</span></span>  
 <span data-ttu-id="69584-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69584-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69584-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="69584-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="69584-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="69584-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69584-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69584-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69584-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69584-116">See Also</span></span>  
 [<span data-ttu-id="69584-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69584-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="69584-118">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69584-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="69584-119">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="69584-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)