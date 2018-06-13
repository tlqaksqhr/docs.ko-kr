---
title: IMetaDataImport::EnumMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 933694a6a033dbfe817e3848b9008f05b86f51f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449014"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="917aa-102">IMetaDataImport::EnumMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="917aa-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="917aa-103">지정한 형식의 메서드를 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="917aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="917aa-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="917aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="917aa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="917aa-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="917aa-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="917aa-108">[in] 열거 하는 메서드를 통해 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="917aa-109">[out] MethodDef 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="917aa-110">[in] MethodDef의 최대 크기 `rMethods` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="917aa-111">[out] 반환 된 MethodDef 토큰 수 `rMethods`합니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="917aa-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="917aa-112">Return Value</span></span>  
  
|<span data-ttu-id="917aa-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="917aa-113">HRESULT</span></span>|<span data-ttu-id="917aa-114">설명</span><span class="sxs-lookup"><span data-stu-id="917aa-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="917aa-115">`EnumMethods` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="917aa-116">열거할 MethodDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="917aa-117">이 경우 `pcTokens` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="917aa-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="917aa-118">Requirements</span></span>  
 <span data-ttu-id="917aa-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="917aa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="917aa-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="917aa-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="917aa-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="917aa-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="917aa-122">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="917aa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917aa-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="917aa-123">See Also</span></span>  
 [<span data-ttu-id="917aa-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="917aa-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="917aa-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="917aa-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
