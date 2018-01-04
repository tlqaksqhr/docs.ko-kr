---
title: "IMetaDataImport::FindTypeDefByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeDefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 036a177e807a2ab77a6afa74c7b811eeaaebfd29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="33e9c-102">IMetaDataImport::FindTypeDefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="33e9c-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="33e9c-103">에 대 한 토큰 TypeDef 메타 데이터에 대 한 포인터를 가져옵니다는 <xref:System.Type> 지정 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="33e9c-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33e9c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33e9c-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="33e9c-106">[in] TypeDef 토큰을 가져올 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="33e9c-107">[in] 바깥쪽 클래스를 나타내는 TypeDef 또는 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="33e9c-108">중첩 된 클래스 형식을 찾을 수 없는 경우이 값을 NULL로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="33e9c-109">[out] 일치 하는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e9c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33e9c-110">Requirements</span></span>  
 <span data-ttu-id="33e9c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33e9c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e9c-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33e9c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33e9c-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="33e9c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33e9c-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e9c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e9c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33e9c-115">See Also</span></span>  
 [<span data-ttu-id="33e9c-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33e9c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="33e9c-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33e9c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
