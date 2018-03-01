---
title: "IAssemblyName::GetVersion 메서드"
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
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ad4084bc758ec8a0b6d97ef211555ccbe78f3bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="a480d-102">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="a480d-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="a480d-103">이 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a480d-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a480d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a480d-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a480d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a480d-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="a480d-106">[out] 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="a480d-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="a480d-107">[out] 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="a480d-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a480d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a480d-108">Requirements</span></span>  
 <span data-ttu-id="a480d-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a480d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a480d-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a480d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a480d-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a480d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a480d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a480d-112">See Also</span></span>  
 [<span data-ttu-id="a480d-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a480d-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
