---
title: "IAssemblyEnum::GetNextAssembly 메서드"
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
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2666970e220334e9e8c2470622026442db0c2f95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="93675-102">IAssemblyEnum::GetNextAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="93675-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="93675-103">다음에 대 한 포인터를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 이에 포함 된 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="93675-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93675-104">구문</span><span class="sxs-lookup"><span data-stu-id="93675-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93675-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93675-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="93675-106">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93675-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="93675-107">`pvReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93675-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="93675-108">[out] 반환 된 `IAssemblyName` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="93675-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="93675-109">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93675-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="93675-110">`dwFlags`0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93675-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93675-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93675-111">Requirements</span></span>  
 <span data-ttu-id="93675-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93675-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93675-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="93675-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="93675-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93675-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93675-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93675-115">See Also</span></span>  
 [<span data-ttu-id="93675-116">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93675-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="93675-117">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93675-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
