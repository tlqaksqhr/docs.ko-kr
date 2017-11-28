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
ms.openlocfilehash: 8a538cea5267b32790a9c656df9584d5ea31f54c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="e046b-102">IMetaDataImport::GetNestedClassProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e046b-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="e046b-103">부모 TypeDef 토큰을 가져옵니다 <xref:System.Type> 지정 된 중첩 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e046b-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e046b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e046b-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e046b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e046b-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="e046b-106">[in] TypeDef 토큰을 나타내는 <xref:System.Type> 부모 클래스를 반환할에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e046b-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="e046b-107">[out] 에 대 한 TypeDef 토큰에 대 한 포인터는 <xref:System.Type> 하 `tdNestedClass` 에 중첩 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e046b-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e046b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e046b-108">Requirements</span></span>  
 <span data-ttu-id="e046b-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e046b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e046b-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e046b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e046b-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e046b-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e046b-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e046b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e046b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e046b-113">See Also</span></span>  
 [<span data-ttu-id="e046b-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e046b-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e046b-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e046b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
