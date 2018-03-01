---
title: "IInstallReferenceEnum::GetNextInstallReferenceItem 메서드"
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
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f3a1b745c3ee28c126e328b1a3fa9e283f98d99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="e08f8-102">IInstallReferenceEnum::GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e08f8-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="e08f8-103">다음에 대 한 포인터를 가져옵니다 [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) 이에 포함 된 개체 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="e08f8-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e08f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e08f8-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="e08f8-106">[out] 반환 된 `IInstallReferenceItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e08f8-107">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e08f8-108">`dwFlags`0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e08f8-109">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e08f8-110">`pvReserved`null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e08f8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e08f8-111">Requirements</span></span>  
 <span data-ttu-id="e08f8-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e08f8-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e08f8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e08f8-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e08f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08f8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e08f8-115">See Also</span></span>  
 [<span data-ttu-id="e08f8-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e08f8-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="e08f8-117">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e08f8-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
