---
title: "IMetaDataImport::GetModuleFromScope 메서드"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b389df634a69bff6197ae11dea96fbb6344dd369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="34de5-102">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="34de5-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="34de5-103">현재 메타 데이터 범위에서 참조 되는 모듈에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34de5-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34de5-104">구문</span><span class="sxs-lookup"><span data-stu-id="34de5-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34de5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34de5-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="34de5-106">[out] 현재 메타 데이터 범위에서 참조 되는 모듈을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="34de5-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34de5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34de5-107">Requirements</span></span>  
 <span data-ttu-id="34de5-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34de5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34de5-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34de5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34de5-110">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="34de5-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34de5-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34de5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34de5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34de5-112">See Also</span></span>  
 [<span data-ttu-id="34de5-113">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34de5-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="34de5-114">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34de5-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
