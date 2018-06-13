---
title: IInstallReferenceItem::GetReference 메서드
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6c64b98f3b5ab0445b076b0d3bacfaa398e26f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429770"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="b9c4c-102">IInstallReferenceItem::GetReference 메서드</span><span class="sxs-lookup"><span data-stu-id="b9c4c-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="b9c4c-103">에 대 한 포인터를 가져옵니다는 [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) 이 표시 되는 구조 [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c4c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9c4c-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9c4c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9c4c-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="b9c4c-106">[out] 반환 된 `FUSION_INSTALL_REFERENCE` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b9c4c-107">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b9c4c-108">`dwFlags` 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b9c4c-109">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b9c4c-110">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9c4c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9c4c-111">Requirements</span></span>  
 <span data-ttu-id="b9c4c-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c4c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9c4c-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9c4c-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9c4c-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9c4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c4c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9c4c-115">See Also</span></span>  
 [<span data-ttu-id="b9c4c-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9c4c-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="b9c4c-117">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="b9c4c-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
