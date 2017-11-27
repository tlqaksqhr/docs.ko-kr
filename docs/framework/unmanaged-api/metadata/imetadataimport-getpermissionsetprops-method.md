---
title: "IMetaDataImport::GetPermissionSetProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2556c0beee7a21d2f01c403ab141054e5bf68177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="a9c74-102">IMetaDataImport::GetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c74-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="a9c74-103">와 연결 된 메타 데이터를 가져옵니다는 <xref:System.Security.PermissionSet?displayProperty=nameWithType> 지정한 권한 토큰이 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c74-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9c74-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9c74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9c74-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="a9c74-106">[in] 권한 집합에 대 한 메타 데이터 속성을 나타내는 권한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="a9c74-107">[out] 사용 권한 집합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="a9c74-108">[out] 사용 권한 집합의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="a9c74-109">[out] 바이트 크기 `ppvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c74-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9c74-110">Requirements</span></span>  
 <span data-ttu-id="a9c74-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c74-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9c74-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9c74-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a9c74-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c74-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c74-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9c74-115">See Also</span></span>  
 <xref:System.Security.PermissionSet>  
 [<span data-ttu-id="a9c74-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c74-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a9c74-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c74-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
