---
title: "CorTokenType 열거형"
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
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae9164753e919b80e635582b15da5263194e215f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="ad5ab-102">CorTokenType 열거형</span><span class="sxs-lookup"><span data-stu-id="ad5ab-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="ad5ab-103">메타 데이터 토큰의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad5ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad5ab-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="ad5ab-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ad5ab-105">Members</span></span>  
  
|<span data-ttu-id="ad5ab-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ad5ab-106">Member</span></span>|<span data-ttu-id="ad5ab-107">설명</span><span class="sxs-lookup"><span data-stu-id="ad5ab-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="ad5ab-108">`mdModule` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="ad5ab-109">`mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="ad5ab-110">`mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="ad5ab-111">`mdFieldDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="ad5ab-112">`mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="ad5ab-113">`mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="ad5ab-114">`mdInterfaceImpl` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="ad5ab-115">`mdMemberRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="ad5ab-116">`mdCustomAttribute` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="ad5ab-117">`mdPermission` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="ad5ab-118">`mdSignature` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="ad5ab-119">`mdEvent` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="ad5ab-120">`mdProperty` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="ad5ab-121">`mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="ad5ab-122">`mdTypeSpec` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="ad5ab-123">`mdAssembly` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="ad5ab-124">`mdAssemblyRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="ad5ab-125">`mdFile` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="ad5ab-126">`mdExportedType` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="ad5ab-127">`mdManifestResource` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="ad5ab-128">`mdGenericParam` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="ad5ab-129">`mdMethodSpec` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="ad5ab-130">`mdGenericParamConstraint` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="ad5ab-131">`mdString` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="ad5ab-132">`mdName` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="ad5ab-133">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad5ab-134">설명</span><span class="sxs-lookup"><span data-stu-id="ad5ab-134">Remarks</span></span>  
 <span data-ttu-id="ad5ab-135">각 값은 해당 메타 데이터 토큰에서 최상위 바이트의 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad5ab-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad5ab-136">Requirements</span></span>  
 <span data-ttu-id="ad5ab-137">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5ab-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad5ab-138">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ad5ab-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ad5ab-139">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad5ab-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5ab-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad5ab-140">See Also</span></span>  
 [<span data-ttu-id="ad5ab-141">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ad5ab-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
