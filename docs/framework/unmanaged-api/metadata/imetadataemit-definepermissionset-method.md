---
title: "IMetaDataEmit::DefinePermissionSet 메서드"
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
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74bea316d3f56e007c4b75e6b801d8c82ae8ce96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="912d3-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="912d3-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="912d3-103">지정 된 메타 데이터 서명을 가진 권한 집합에 대 한 정의 만들고 해당 사용 권한 집합 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="912d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="912d3-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="912d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="912d3-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="912d3-106">[in] 데코 레이트 되어야 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="912d3-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 사용할 선언적 보안의 형식을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="912d3-108">[in] BLOB 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="912d3-109">[in] 를 바이트 단위로 크기의 `pvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="912d3-110">[out] 반환 된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="912d3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="912d3-111">Requirements</span></span>  
 <span data-ttu-id="912d3-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="912d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="912d3-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="912d3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="912d3-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="912d3-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="912d3-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="912d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912d3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="912d3-116">See Also</span></span>  
 [<span data-ttu-id="912d3-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="912d3-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="912d3-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="912d3-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
