---
title: "IGCHost::Collect 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0ffe759c6c6049baa11dcc00d4cdee8415156f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="igchostcollect-method"></a><span data-ttu-id="b9252-102">IGCHost::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="b9252-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="b9252-103">현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 대 한 컬렉션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9252-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9252-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9252-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9252-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9252-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b9252-106">[in] 가비지 수집을 수행 하기를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9252-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="b9252-107">값이-1은 모든 세대 가비지 수집을 될 예정 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9252-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9252-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9252-108">Requirements</span></span>  
 <span data-ttu-id="b9252-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9252-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9252-110">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b9252-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b9252-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b9252-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9252-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9252-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9252-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9252-113">See Also</span></span>  
 [<span data-ttu-id="b9252-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9252-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
