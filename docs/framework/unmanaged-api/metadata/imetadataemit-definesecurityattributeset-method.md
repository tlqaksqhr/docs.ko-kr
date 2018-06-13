---
title: IMetaDataEmit::DefineSecurityAttributeSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60cb1640d374ce71d1d2fb51ba536b53ddd39b92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443529"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="9c434-102">IMetaDataEmit::DefineSecurityAttributeSet 메서드</span><span class="sxs-lookup"><span data-stu-id="9c434-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="9c434-103">지정한 토큰이 참조 하는 개체에 연결 하는 보안 권한 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c434-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c434-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c434-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c434-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="9c434-106">[in] 보안 정보가 연결 되는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="9c434-107">[in] 배열 `COR_SECATTR` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="9c434-108">[in] 요소 수가 `rSecAttrs`합니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="9c434-109">[out] 메서드가 실패 하는 경우 지정 된 인덱스 `rSecAttrs` 문제를 발생 시킨 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c434-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c434-110">Requirements</span></span>  
 <span data-ttu-id="9c434-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c434-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c434-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c434-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c434-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9c434-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c434-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c434-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c434-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c434-115">See Also</span></span>  
 [<span data-ttu-id="9c434-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c434-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9c434-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c434-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
