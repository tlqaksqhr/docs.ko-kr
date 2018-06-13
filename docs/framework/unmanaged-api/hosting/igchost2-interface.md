---
title: IGCHost2 인터페이스
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437679"
---
# <a name="igchost2-interface"></a><span data-ttu-id="12a47-102">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12a47-102">IGCHost2 Interface</span></span>
<span data-ttu-id="12a47-103">가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="12a47-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12a47-104">새 개발을 위해 사용 하는 권장는 [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) 대신 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="12a47-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12a47-105">메서드</span><span class="sxs-lookup"><span data-stu-id="12a47-105">Methods</span></span>  
  
|<span data-ttu-id="12a47-106">메서드</span><span class="sxs-lookup"><span data-stu-id="12a47-106">Method</span></span>|<span data-ttu-id="12a47-107">설명</span><span class="sxs-lookup"><span data-stu-id="12a47-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12a47-108">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="12a47-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="12a47-109">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="12a47-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="12a47-110">0 세대 및 세그먼트 크기 보다 큰 수 있도록 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="12a47-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12a47-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12a47-111">Requirements</span></span>  
 <span data-ttu-id="12a47-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12a47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12a47-113">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="12a47-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="12a47-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="12a47-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12a47-115">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12a47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a47-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12a47-116">See Also</span></span>  
 [<span data-ttu-id="12a47-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12a47-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="12a47-118">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12a47-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="12a47-119">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="12a47-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
