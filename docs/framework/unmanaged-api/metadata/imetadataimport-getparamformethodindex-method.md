---
title: "IMetaDataImport::GetParamForMethodIndex 메서드"
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
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0cedc993e6b8794a15ff9927b06ff650ed76b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="3f49c-102">IMetaDataImport::GetParamForMethodIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="3f49c-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="3f49c-103">지정한 MethodDef 토큰이 나타내는 메서드에 지정 된 매개 변수를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f49c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f49c-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f49c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f49c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="3f49c-106">[in] 에 대 한 매개 변수 토큰을 반환 하는 메서드를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="3f49c-107">[in] 요청한 매개 변수 발생 하는 위치 매개 변수 목록의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="3f49c-108">매개 변수 위치 0에에서 메서드의 반환 값을 가진 하나에서 시작 하는 번호가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="3f49c-109">[out] 요청한 매개 변수를 나타내는 ParamDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f49c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f49c-110">Requirements</span></span>  
 <span data-ttu-id="3f49c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f49c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f49c-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f49c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f49c-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3f49c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f49c-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f49c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f49c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f49c-115">See Also</span></span>  
 [<span data-ttu-id="3f49c-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f49c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3f49c-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f49c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
