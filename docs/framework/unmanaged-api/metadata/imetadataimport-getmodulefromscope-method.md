---
title: IMetaDataImport::GetModuleFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1f8acc546c0d96aca079223200b43aec933f729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447911"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="141f7-102">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="141f7-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="141f7-103">현재 메타 데이터 범위에서 참조 되는 모듈에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="141f7-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="141f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="141f7-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="141f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="141f7-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="141f7-106">[out] 현재 메타 데이터 범위에서 참조 되는 모듈을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="141f7-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="141f7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="141f7-107">Requirements</span></span>  
 <span data-ttu-id="141f7-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="141f7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="141f7-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="141f7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="141f7-110">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="141f7-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="141f7-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="141f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141f7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="141f7-112">See Also</span></span>  
 [<span data-ttu-id="141f7-113">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="141f7-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="141f7-114">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="141f7-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
