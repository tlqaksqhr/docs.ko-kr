---
title: "IMetaDataImport::EnumInterfaceImpls 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646d65ff81795ce0558651db9c3fe1bc7205ae08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="74f34-102">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="74f34-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="74f34-103">인터페이스 구현을 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f34-104">구문</span><span class="sxs-lookup"><span data-stu-id="74f34-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74f34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74f34-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="74f34-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="74f34-107">[in] 인터페이스 구현을 나타내는 MethodDef 토큰 인을 열거할 수는 TypeDef의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="74f34-108">[out] MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="74f34-109">[in] `rImpls` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="74f34-110">[out] 반환 된 토큰의 실제 수 `rImpls`합니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74f34-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="74f34-111">Return Value</span></span>  
  
|<span data-ttu-id="74f34-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74f34-112">HRESULT</span></span>|<span data-ttu-id="74f34-113">설명</span><span class="sxs-lookup"><span data-stu-id="74f34-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="74f34-114">`EnumInterfaceImpls`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="74f34-115">열거할 MethodDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="74f34-116">이 경우 `pcImpls` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74f34-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74f34-117">Requirements</span></span>  
 <span data-ttu-id="74f34-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74f34-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f34-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74f34-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74f34-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="74f34-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74f34-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f34-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f34-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74f34-122">See Also</span></span>  
 [<span data-ttu-id="74f34-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74f34-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="74f34-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74f34-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
