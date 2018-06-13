---
title: IMetaDataImport::GetNestedClassProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c77f946b14fcb5ddc786488ab42e37eb868fbc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448281"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="2dbba-102">IMetaDataImport::GetNestedClassProps 메서드</span><span class="sxs-lookup"><span data-stu-id="2dbba-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="2dbba-103">부모 TypeDef 토큰을 가져옵니다 <xref:System.Type> 지정 된 중첩 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbba-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dbba-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dbba-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dbba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dbba-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="2dbba-106">[in] TypeDef 토큰을 나타내는 <xref:System.Type> 부모 클래스를 반환할에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbba-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="2dbba-107">[out] 에 대 한 TypeDef 토큰에 대 한 포인터는 <xref:System.Type> 하 `tdNestedClass` 에 중첩 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dbba-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dbba-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dbba-108">Requirements</span></span>  
 <span data-ttu-id="2dbba-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2dbba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dbba-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2dbba-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2dbba-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2dbba-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2dbba-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dbba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbba-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dbba-113">See Also</span></span>  
 [<span data-ttu-id="2dbba-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dbba-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2dbba-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dbba-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
