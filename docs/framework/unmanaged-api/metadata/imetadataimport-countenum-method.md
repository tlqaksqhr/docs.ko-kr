---
title: "IMetaDataImport::CountEnum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.CountEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29bbc78da38ca65b2c19c5f0d93a273ba3ac0da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="ea2d1-102">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="ea2d1-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="ea2d1-103">지정된 된 열거자에서 검색 된 열거형의 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea2d1-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea2d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea2d1-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea2d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea2d1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ea2d1-106">[in] 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2d1-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="ea2d1-107">[out] 열거 된 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2d1-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea2d1-108">설명</span><span class="sxs-lookup"><span data-stu-id="ea2d1-108">Remarks</span></span>  
 <span data-ttu-id="ea2d1-109">로 지정 된 핸들 `hEnum` 이전에서 가져온 `Enum` *이름* 호출 (예를 들어 [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ea2d1-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea2d1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea2d1-110">Requirements</span></span>  
 <span data-ttu-id="ea2d1-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2d1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea2d1-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea2d1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea2d1-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ea2d1-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea2d1-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea2d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2d1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea2d1-115">See Also</span></span>  
 [<span data-ttu-id="ea2d1-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea2d1-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ea2d1-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea2d1-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
