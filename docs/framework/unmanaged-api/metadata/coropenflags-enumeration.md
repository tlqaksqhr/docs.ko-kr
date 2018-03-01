---
title: "CorOpenFlags 열거형"
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
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4447f648277576169c9004d1880283728639c8f3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="3dac8-102">CorOpenFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3dac8-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="3dac8-103">매니페스트 파일을 열 때 메타데이터 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dac8-104">구문</span><span class="sxs-lookup"><span data-stu-id="3dac8-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3dac8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3dac8-105">Members</span></span>  
  
|<span data-ttu-id="3dac8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3dac8-106">Member</span></span>|<span data-ttu-id="3dac8-107">설명</span><span class="sxs-lookup"><span data-stu-id="3dac8-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="3dac8-108">파일을 읽기 전용으로 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="3dac8-109">쓸 수 있도록 파일을 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="3dac8-110">.winmd 파일을 열 때 `ofWrite` 플래그를 사용하는 경우에는 `ofNoTransform` 플래그도 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="3dac8-111">읽기 및 쓰기용 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="3dac8-112">파일을 메모리로 읽어들여야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="3dac8-113">메타데이터는 자체 복사본을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="3dac8-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-114">Obsolete.</span></span> <span data-ttu-id="3dac8-115">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="3dac8-116">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-116">Obsolete.</span></span> <span data-ttu-id="3dac8-117">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="3dac8-118">읽기, 및에 대 한 파일을 열 수 있는지 나타냅니다에 대 한 호출 `QueryInterface` 에 대 한 프로그램 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="3dac8-119">에 대 한 호출을 사용 하 여 메모리가 할당 된 나타냅니다 [CoTaskMemAlloc](http://msdn.microsoft.com/library/c4cb588d-9482-4f90-a92e-75b604540d5c) 메타 데이터에서 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](http://msdn.microsoft.com/library/c4cb588d-9482-4f90-a92e-75b604540d5c) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="3dac8-120">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-120">Obsolete.</span></span> <span data-ttu-id="3dac8-121">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="3dac8-122">.winmd 파일의 자동 변환을 사용하지 않도록 설정해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="3dac8-123">즉, Windows 런타임 형식에서 .NET Framework 형식으로의 프로젝션을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="3dac8-124">자세한 내용은 참조 [아래 고급.NET 및 Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="3dac8-125">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="3dac8-126">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="3dac8-127">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3dac8-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dac8-128">Requirements</span></span>  
 <span data-ttu-id="3dac8-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dac8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dac8-130">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3dac8-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3dac8-131">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dac8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dac8-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dac8-132">See Also</span></span>  
 [<span data-ttu-id="3dac8-133">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="3dac8-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
