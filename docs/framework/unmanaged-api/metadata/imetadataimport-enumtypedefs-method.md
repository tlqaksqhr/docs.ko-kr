---
title: "IMetaDataImport::EnumTypeDefs 메서드"
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
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aeb0e3c2eab4cde219b050bcf0e50202fe2be3f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="2211b-102">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="2211b-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="2211b-103">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2211b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2211b-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2211b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2211b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2211b-106">[out] 새 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="2211b-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="2211b-108">[in] TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2211b-109">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="2211b-110">[out] 반환 하는 TypeDef 토큰 수 `rTypeDefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2211b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="2211b-111">Return Value</span></span>  
  
|<span data-ttu-id="2211b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2211b-112">HRESULT</span></span>|<span data-ttu-id="2211b-113">설명</span><span class="sxs-lookup"><span data-stu-id="2211b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2211b-114">`EnumTypeDefs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2211b-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2211b-116">이 경우 `pcTypeDefs` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2211b-117">설명</span><span class="sxs-lookup"><span data-stu-id="2211b-117">Remarks</span></span>  
 <span data-ttu-id="2211b-118">TypeDef 토큰에는 같은 클래스 또는 인터페이스 형식 뿐만 아니라 확장성 메커니즘을 통해 추가 된 모든 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2211b-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2211b-119">Requirements</span></span>  
 <span data-ttu-id="2211b-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2211b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2211b-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2211b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2211b-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2211b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2211b-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2211b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2211b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2211b-124">See Also</span></span>  
 [<span data-ttu-id="2211b-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2211b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2211b-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2211b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
