---
title: "IMetaDataAssemblyImport::FindExportedTypeByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindExportedTypeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7ef0e09cb5a44e612e545fc4ee7278c2d128174
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="c3817-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="c3817-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="c3817-103">해당 이름 및 바깥쪽 형식 지정 된 내보낸된 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3817-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3817-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3817-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3817-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c3817-106">[in] 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="c3817-107">[in] 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="c3817-108">이 값은 `mdExportedTypeNil` 요청 된 내보낸가 아니면 중첩된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="c3817-109">[out] 에 대 한 포인터는 `mdExportedType` 내보낸된 형식 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3817-110">설명</span><span class="sxs-lookup"><span data-stu-id="c3817-110">Remarks</span></span>  
 <span data-ttu-id="c3817-111">`FindExportedTypeByName` 메서드는 참조를 확인 하기 위한 공용 언어 런타임에서 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3817-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3817-112">Requirements</span></span>  
 <span data-ttu-id="c3817-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3817-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3817-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3817-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3817-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c3817-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3817-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3817-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3817-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3817-117">See Also</span></span>  
 [<span data-ttu-id="c3817-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3817-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="c3817-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c3817-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
