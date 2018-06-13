---
title: IMetaDataImport::GetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95850448504fd863f2726a7fb7574436476a6dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449327"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="cb94f-102">IMetaDataImport::GetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="cb94f-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="cb94f-103">지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb94f-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb94f-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb94f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb94f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="cb94f-106">[in] 에 대 한 메타 데이터를 반환 매개 변수를 나타내는 ParamDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="cb94f-107">[out] 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="cb94f-108">[out] 메서드 인수 목록에서 매개 변수의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="cb94f-109">[out] 매개 변수의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="cb94f-110">[in] 요청된 된 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="cb94f-111">[out] 반환 되는 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="cb94f-112">[out] 매개 변수와 연관 된 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="cb94f-113">[out] 매개 변수가 지정 하는 플래그에 대 한 포인터는 <xref:System.ValueType>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="cb94f-114">[out] 매개 변수에서 반환 된 상수 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="cb94f-115">[out] 크기 `ppValue` 와이드 문자 또는 경우에는 0에서 `ppValue` 문자열로 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb94f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb94f-116">Requirements</span></span>  
 <span data-ttu-id="cb94f-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb94f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb94f-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cb94f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb94f-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cb94f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb94f-120">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb94f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb94f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb94f-121">See Also</span></span>  
 [<span data-ttu-id="cb94f-122">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb94f-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="cb94f-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb94f-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
