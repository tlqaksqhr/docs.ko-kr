---
title: "IMetaDataImport::IsGlobal 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsGlobal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f7d437e09063bf621990dec4f2903139af8238
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="7ca7a-102">IMetaDataImport::IsGlobal 메서드</span><span class="sxs-lookup"><span data-stu-id="7ca7a-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="7ca7a-103">지정한 메타데이터 토큰이 나타내는 필드, 메서드 또는 형식에 전역 범위가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7a-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ca7a-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ca7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ca7a-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="7ca7a-106">[in] 형식, 필드 또는 메서드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7a-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="7ca7a-107">[out] 이면 1 개체에 전역 범위가 지정 됩니다. 그렇지 않으면 0 (영)입니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7a-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca7a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ca7a-108">Requirements</span></span>  
 <span data-ttu-id="7ca7a-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca7a-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ca7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ca7a-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7ca7a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ca7a-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca7a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ca7a-113">See Also</span></span>  
 [<span data-ttu-id="7ca7a-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca7a-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7ca7a-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ca7a-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
