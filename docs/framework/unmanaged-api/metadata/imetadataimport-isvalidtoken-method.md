---
title: IMetaDataImport::IsValidToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d752d6dbe8a6b7a23faae498f9118c8d89e92929
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447699"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="ff010-102">IMetaDataImport::IsValidToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ff010-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="ff010-103">지정한 토큰이 코드 개체에 대한 유효한 참조를 포함하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff010-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff010-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff010-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff010-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff010-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ff010-106">[in] 에 대 한 참조 유효성을 검사 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ff010-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff010-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff010-107">Return Value</span></span>  
 <span data-ttu-id="ff010-108">`true` 경우 `tk` 현재 범위 내 올바른 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ff010-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="ff010-109">그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="ff010-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff010-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff010-110">Requirements</span></span>  
 <span data-ttu-id="ff010-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff010-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff010-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff010-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff010-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ff010-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff010-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff010-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff010-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff010-115">See Also</span></span>  
 [<span data-ttu-id="ff010-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff010-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ff010-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff010-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
