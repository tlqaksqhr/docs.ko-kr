---
title: "IMetaDataImport::GetSigFromToken 메서드"
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
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6328e112aa948ecc2f0f5d816c4fd77673e06244
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="5640f-102">IMetaDataImport::GetSigFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5640f-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="5640f-103">지정한 토큰과 연결된 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5640f-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5640f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5640f-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5640f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5640f-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="5640f-106">[in] 에 대 한 이진 메타 데이터 서명을 반환 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5640f-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="5640f-107">[out] 반환 된 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5640f-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="5640f-108">[out] 이진 메타 데이터 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5640f-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5640f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5640f-109">Requirements</span></span>  
 <span data-ttu-id="5640f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5640f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5640f-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5640f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5640f-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5640f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5640f-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5640f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5640f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5640f-114">See Also</span></span>  
 [<span data-ttu-id="5640f-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5640f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5640f-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5640f-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
