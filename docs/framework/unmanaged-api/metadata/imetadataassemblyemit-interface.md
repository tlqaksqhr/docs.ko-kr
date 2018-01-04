---
title: "IMetaDataAssemblyEmit 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a7e4bd68bfd985b8902ae3b2340773ca77eee10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="80ce7-102">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80ce7-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="80ce7-103">공용 언어 런타임에서 리소스를 확인하고 소비하는 데 사용되는 자체 설명 모델을 지원하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80ce7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-104">Methods</span></span>  
  
|<span data-ttu-id="80ce7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-105">Method</span></span>|<span data-ttu-id="80ce7-106">설명</span><span class="sxs-lookup"><span data-stu-id="80ce7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80ce7-107">DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="80ce7-108">지정된 어셈블리에 대한 메타데이터를 포함하는 어셈블리 데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="80ce7-109">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="80ce7-110">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="80ce7-111">DefineExportedType 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="80ce7-112">지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="80ce7-113">DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="80ce7-114">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="80ce7-115">DefineManifestResource 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="80ce7-116">지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="80ce7-117">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="80ce7-118">지정된 `Assembly` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="80ce7-119">SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="80ce7-120">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="80ce7-121">SetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="80ce7-122">지정된 `ExportedType` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="80ce7-123">SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="80ce7-124">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="80ce7-125">SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="80ce7-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="80ce7-126">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80ce7-127">설명</span><span class="sxs-lookup"><span data-stu-id="80ce7-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ce7-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80ce7-128">Requirements</span></span>  
 <span data-ttu-id="80ce7-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80ce7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ce7-130">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80ce7-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80ce7-131">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="80ce7-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80ce7-132">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ce7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ce7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80ce7-133">See Also</span></span>  
 [<span data-ttu-id="80ce7-134">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80ce7-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="80ce7-135">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80ce7-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
