---
title: IMetaDataImport::EnumInterfaceImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447463"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="efa2d-102">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="efa2d-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="efa2d-103">인터페이스 구현을 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="efa2d-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efa2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efa2d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="efa2d-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="efa2d-107">[in] 인터페이스 구현을 나타내는 MethodDef 토큰 인을 열거할 수는 TypeDef의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="efa2d-108">[out] MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="efa2d-109">[in] `rImpls` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="efa2d-110">[out] 반환 된 토큰의 실제 수 `rImpls`합니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efa2d-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="efa2d-111">Return Value</span></span>  
  
|<span data-ttu-id="efa2d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efa2d-112">HRESULT</span></span>|<span data-ttu-id="efa2d-113">설명</span><span class="sxs-lookup"><span data-stu-id="efa2d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="efa2d-114">`EnumInterfaceImpls` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="efa2d-115">열거할 MethodDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="efa2d-116">이 경우 `pcImpls` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efa2d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efa2d-117">Requirements</span></span>  
 <span data-ttu-id="efa2d-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="efa2d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa2d-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="efa2d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efa2d-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="efa2d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efa2d-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa2d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa2d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efa2d-122">See Also</span></span>  
 [<span data-ttu-id="efa2d-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efa2d-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="efa2d-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efa2d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
