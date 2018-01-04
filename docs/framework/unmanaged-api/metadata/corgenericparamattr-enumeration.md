---
title: "CorGenericParamAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGenericParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorGenericParamAttr
helpviewer_keywords: CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="76905-102">CorGenericParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="76905-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="76905-103">설명 하는 값이 포함 되어는 <xref:System.Type> 호출에서 사용된 된 제네릭 형식에 대 한 매개 변수 [imetadataemit2:: Definegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76905-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76905-104">구문</span><span class="sxs-lookup"><span data-stu-id="76905-104">Syntax</span></span>  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="76905-105">멤버</span><span class="sxs-lookup"><span data-stu-id="76905-105">Members</span></span>  
  
|<span data-ttu-id="76905-106">멤버</span><span class="sxs-lookup"><span data-stu-id="76905-106">Member</span></span>|<span data-ttu-id="76905-107">설명</span><span class="sxs-lookup"><span data-stu-id="76905-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="76905-108">매개 변수 분산 인터페이스 및 대리자에 대 한 제네릭 매개 변수에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76905-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="76905-109">분산 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76905-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="76905-110">공 분산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76905-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="76905-111">반공 분산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76905-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="76905-112">모든 특수 제약 조건을 적용할 수 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="76905-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="76905-113">제약 조건이 없는에 적용 되도록 나타냅니다는 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="76905-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="76905-114">나타냅니다는 <xref:System.Type> 매개 변수는 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76905-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="76905-115">나타냅니다는 <xref:System.Type> 매개 변수는 null 값이 될 수 없는 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76905-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="76905-116">나타냅니다는 <xref:System.Type> 매개 변수는 매개 변수가 없는 기본 public 생성자 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76905-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76905-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76905-117">Requirements</span></span>  
 <span data-ttu-id="76905-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76905-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76905-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="76905-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="76905-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76905-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76905-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76905-121">See Also</span></span>  
 [<span data-ttu-id="76905-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="76905-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
