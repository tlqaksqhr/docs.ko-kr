---
title: "IAssemblyCacheItem::커밋 메서드"
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
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3e1907fa3be4992573f84b4810f7504f3af78397
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="d621e-102">IAssemblyCacheItem::커밋 메서드</span><span class="sxs-lookup"><span data-stu-id="d621e-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="d621e-103">메모리에 캐시 된 어셈블리 참조를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="d621e-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d621e-104">구문</span><span class="sxs-lookup"><span data-stu-id="d621e-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d621e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d621e-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d621e-106">[in] 값에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d621e-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="d621e-107">[out, optional] 작업의 결과 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d621e-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d621e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d621e-108">Requirements</span></span>  
 <span data-ttu-id="d621e-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d621e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d621e-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d621e-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d621e-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d621e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d621e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d621e-112">See Also</span></span>  
 [<span data-ttu-id="d621e-113">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d621e-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
