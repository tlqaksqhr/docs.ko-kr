---
title: "IMetaDataImport::GetModuleRefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee230b691411c49ba4f0096d998ac229283fc02c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="a2f32-102">IMetaDataImport::GetModuleRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a2f32-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="a2f32-103">지정한 메타데이터 토큰에서 참조된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f32-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2f32-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2f32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2f32-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="a2f32-106">[in] ModuleRef 메타 데이터 토큰에 대 한 메타 데이터 정보를 가져올 모듈을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="a2f32-107">[out] 모듈 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a2f32-108">[in] 요청된 된 크기의 `szName` 와이드 문자에서입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a2f32-109">[out] 반환 되는 크기의 `szName` 와이드 문자에서입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f32-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2f32-110">Requirements</span></span>  
 <span data-ttu-id="a2f32-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f32-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2f32-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2f32-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a2f32-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2f32-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f32-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2f32-115">See Also</span></span>  
 [<span data-ttu-id="a2f32-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f32-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a2f32-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f32-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
