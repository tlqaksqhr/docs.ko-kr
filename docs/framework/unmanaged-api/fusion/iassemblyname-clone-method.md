---
title: "IAssemblyName::Clone 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.Clone
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 306263bcb27141eadc0943c0045a5f71285436e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="e246d-102">IAssemblyName::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="e246d-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="e246d-103">이 항목의 단순 복사본을 만듭니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e246d-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e246d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e246d-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e246d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e246d-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="e246d-106">[out] 이 반환 되는 복사본 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e246d-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e246d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e246d-107">Requirements</span></span>  
 <span data-ttu-id="e246d-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e246d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e246d-109">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e246d-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e246d-110">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e246d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e246d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e246d-111">See Also</span></span>  
 [<span data-ttu-id="e246d-112">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e246d-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
