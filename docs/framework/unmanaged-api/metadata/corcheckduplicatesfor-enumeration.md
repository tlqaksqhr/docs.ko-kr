---
title: "CorCheckDuplicatesFor 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5a9376f6d56e2a21ee474e2724ce5eff8f6f63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="7362b-102">CorCheckDuplicatesFor 열거형</span><span class="sxs-lookup"><span data-stu-id="7362b-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="7362b-103">중복 항목을 확인 하는 메타 데이터 토큰을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7362b-104">구문</span><span class="sxs-lookup"><span data-stu-id="7362b-104">Syntax</span></span>  
  
```  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="7362b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7362b-105">Members</span></span>  
  
|<span data-ttu-id="7362b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7362b-106">Member</span></span>|<span data-ttu-id="7362b-107">설명</span><span class="sxs-lookup"><span data-stu-id="7362b-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="7362b-108">중복 항목에 대 한 모든 메타 데이터 토큰을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="7362b-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="7362b-110">중복 항목에 대 한 메타 데이터 토큰을 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="7362b-111">중복 여부를 확인 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="7362b-112">중복 여부를 확인 `mdInterfaceImpl` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="7362b-113">중복 여부를 확인 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="7362b-114">중복 여부를 확인 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="7362b-115">중복 여부를 확인 `mdMemberRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="7362b-116">중복 여부를 확인 `mdCustomAttribute` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="7362b-117">중복 여부를 확인 `mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="7362b-118">중복 여부를 확인 `mdPermission` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="7362b-119">중복 여부를 확인 `mdProperty` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="7362b-120">중복 여부를 확인 `mdEvent` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="7362b-121">중복 여부를 확인 `mdFieldDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="7362b-122">중복 여부를 확인 `mdSignature` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="7362b-123">중복 여부를 확인 `mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="7362b-124">중복 여부를 확인 `mdTypeSpec` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="7362b-125">중복 여부를 확인 `mdImplMap` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="7362b-126">중복 여부를 확인 `mdAssemblyRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="7362b-127">중복 여부를 확인 `mdFile` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="7362b-128">중복 여부를 확인 `mdExportedType` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="7362b-129">중복 여부를 확인 `mdManifestResource` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="7362b-130">중복 여부를 확인 `mdGenericParam` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="7362b-131">중복 여부를 확인 `mdMethodSpec` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="7362b-132">중복 여부를 확인 `mdGenericParamConstraint` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="7362b-133">중복 여부를 확인 `mdAssembly` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="7362b-134">중복 여부를 확인 `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, 및 `mdMethodSpec` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7362b-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7362b-135">Requirements</span></span>  
 <span data-ttu-id="7362b-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7362b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7362b-137">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7362b-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7362b-138">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7362b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7362b-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7362b-139">See Also</span></span>  
 [<span data-ttu-id="7362b-140">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7362b-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
