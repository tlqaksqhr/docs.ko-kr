---
title: "COR_FIELD_OFFSET 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD_OFFSET
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_FIELD_OFFSET
helpviewer_keywords: COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8e821a9d4ffa5054f687eff7360bc8d7cefb9f09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="870ad-102">COR_FIELD_OFFSET 구조체</span><span class="sxs-lookup"><span data-stu-id="870ad-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="870ad-103">클래스 내에서 지정된 필드의 오프셋을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="870ad-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="870ad-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="870ad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="870ad-105">Members</span></span>  
  
|<span data-ttu-id="870ad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="870ad-106">Member</span></span>|<span data-ttu-id="870ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="870ad-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="870ad-108">`mdFieldDef` 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="870ad-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="870ad-109">필드는 해당 클래스 내에서 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="870ad-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="870ad-110">설명</span><span class="sxs-lookup"><span data-stu-id="870ad-110">Remarks</span></span>  
 <span data-ttu-id="870ad-111">[Imetadataimport:: Getclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) 및 [imetadataemit:: Setclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) 메서드 형식 매개 변수를 `COR_FIELD_OFFSET`합니다.</span><span class="sxs-lookup"><span data-stu-id="870ad-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870ad-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="870ad-112">Requirements</span></span>  
 <span data-ttu-id="870ad-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="870ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="870ad-114">**헤더:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="870ad-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="870ad-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="870ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870ad-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="870ad-116">See Also</span></span>  
 [<span data-ttu-id="870ad-117">메타 데이터 구조</span><span class="sxs-lookup"><span data-stu-id="870ad-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="870ad-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="870ad-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="870ad-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="870ad-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
