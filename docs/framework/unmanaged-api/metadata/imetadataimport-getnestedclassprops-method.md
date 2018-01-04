---
title: "IMetaDataImport::GetNestedClassProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNestedClassProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bbfe382a9a2fdf8ece1015ee73c3d9ef604ec7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="c74c6-102">IMetaDataImport::GetNestedClassProps 메서드</span><span class="sxs-lookup"><span data-stu-id="c74c6-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="c74c6-103">부모 TypeDef 토큰을 가져옵니다 <xref:System.Type> 지정 된 중첩 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c74c6-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c74c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c74c6-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c74c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c74c6-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="c74c6-106">[in] TypeDef 토큰을 나타내는 <xref:System.Type> 부모 클래스를 반환할에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c74c6-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="c74c6-107">[out] 에 대 한 TypeDef 토큰에 대 한 포인터는 <xref:System.Type> 하 `tdNestedClass` 에 중첩 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c74c6-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c74c6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c74c6-108">Requirements</span></span>  
 <span data-ttu-id="c74c6-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c74c6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c74c6-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c74c6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c74c6-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c74c6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c74c6-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c74c6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c74c6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c74c6-113">See Also</span></span>  
 [<span data-ttu-id="c74c6-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c74c6-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c74c6-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c74c6-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
