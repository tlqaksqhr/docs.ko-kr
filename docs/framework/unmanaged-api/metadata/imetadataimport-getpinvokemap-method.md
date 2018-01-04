---
title: "IMetaDataImport::GetPinvokeMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a28d628040a35d309515703563239a5f802dc4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="e518a-102">IMetaDataImport::GetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="e518a-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="e518a-103">PInvoke 호출의 대상 어셈블리를 나타내는 ModuleRef 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e518a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e518a-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e518a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e518a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e518a-106">[in] 에 대 한 PInvoke 매핑 메타 데이터를 가져올 FieldDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="e518a-107">[out] 매핑에 사용 되는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="e518a-108">이 값은의 비트 마스크는 [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="e518a-109">[out] 관리 되지 않는 대상 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="e518a-110">[in] 와이드 문자에서 크기 `szImportName`합니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="e518a-111">[out] 반환 된 와이드 문자의 수가 `szImportName`합니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="e518a-112">[out] 관리 되지 않는 대상 개체 라이브러리를 나타내는 ModuleRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e518a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e518a-113">Requirements</span></span>  
 <span data-ttu-id="e518a-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e518a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e518a-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e518a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e518a-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e518a-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e518a-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e518a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e518a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e518a-118">See Also</span></span>  
 [<span data-ttu-id="e518a-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e518a-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e518a-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e518a-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
