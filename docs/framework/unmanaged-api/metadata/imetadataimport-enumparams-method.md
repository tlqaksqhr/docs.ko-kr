---
title: "IMetaDataImport::EnumParams 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42555e1300016222e9ea8064e90fa3062d79db6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="44c4e-102">IMetaDataImport::EnumParams 메서드</span><span class="sxs-lookup"><span data-stu-id="44c4e-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="44c4e-103">지정한 MethodDef 토큰이 참조하는 메서드의 매개 변수를 나타내는 ParamDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="44c4e-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44c4e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44c4e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="44c4e-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="44c4e-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="44c4e-108">[in] 열거 하는 매개 변수에 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="44c4e-109">[out] ParamDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="44c4e-110">[in] `rParams` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="44c4e-111">[out] 반환 된 ParamDef 토큰 수 `rParams`합니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44c4e-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="44c4e-112">Return Value</span></span>  
  
|<span data-ttu-id="44c4e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44c4e-113">HRESULT</span></span>|<span data-ttu-id="44c4e-114">설명</span><span class="sxs-lookup"><span data-stu-id="44c4e-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="44c4e-115">`EnumParams`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="44c4e-116">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="44c4e-117">이 경우 `pcTokens` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44c4e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44c4e-118">Requirements</span></span>  
 <span data-ttu-id="44c4e-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44c4e-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c4e-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44c4e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44c4e-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="44c4e-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44c4e-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c4e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c4e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44c4e-123">See Also</span></span>  
 [<span data-ttu-id="44c4e-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44c4e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="44c4e-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44c4e-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
