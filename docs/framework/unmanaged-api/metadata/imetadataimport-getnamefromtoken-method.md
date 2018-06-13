---
title: IMetaDataImport::GetNameFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a39eac88537d47535844d1f05e0741cc94142f0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447255"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="46a93-102">IMetaDataImport::GetNameFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="46a93-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="46a93-103">지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="46a93-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a93-105">구문</span><span class="sxs-lookup"><span data-stu-id="46a93-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46a93-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46a93-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="46a93-107">[in] 에 대 한 이름을 반환 하 고 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="46a93-108">[out] 힙에 있는 u t F-8 개체 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46a93-109">설명</span><span class="sxs-lookup"><span data-stu-id="46a93-109">Remarks</span></span>  
 <span data-ttu-id="46a93-110">`GetNameFromToken`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="46a93-111">대신 특정 유형의 같은 필요한 토큰의 속성을 가져오는 메서드를 호출 `GetFieldProps` 필드 또는 `GetMethodProps` 메서드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a93-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46a93-112">Requirements</span></span>  
 <span data-ttu-id="46a93-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46a93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46a93-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="46a93-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46a93-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="46a93-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46a93-116">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="46a93-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a93-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46a93-117">See Also</span></span>  
 [<span data-ttu-id="46a93-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46a93-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="46a93-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46a93-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
