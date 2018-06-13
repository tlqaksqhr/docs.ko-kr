---
title: IMetaDataAssemblyEmit::SetExportedTypeProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8643a4d207fb570195caa00a1ac659c78c2ff2b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445068"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="90e44-102">IMetaDataAssemblyEmit::SetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="90e44-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="90e44-103">지정된 `ExportedType` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e44-104">구문</span><span class="sxs-lookup"><span data-stu-id="90e44-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90e44-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90e44-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="90e44-106">[in] 메타 데이터 토큰을 지정 하는 `ExportedType` 메타 데이터 구조를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="90e44-107">[in] 형식의 토큰 `File`, `AssemblyRef`, 또는 `ExportedType`,이 형식을 구현 하는 방법을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="90e44-108">[in] `TypeDef` 코드 파일에서 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="90e44-109">[in] 형식의 특성을 지정 하는 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90e44-110">설명</span><span class="sxs-lookup"><span data-stu-id="90e44-110">Remarks</span></span>  
 <span data-ttu-id="90e44-111">만들려는 `ExportedType` 메타 데이터 구조를 사용 하 여는 [imetadataassemblyemit:: Defineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="90e44-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e44-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90e44-112">Requirements</span></span>  
 <span data-ttu-id="90e44-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90e44-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e44-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90e44-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90e44-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="90e44-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90e44-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e44-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90e44-117">See Also</span></span>  
 [<span data-ttu-id="90e44-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90e44-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
