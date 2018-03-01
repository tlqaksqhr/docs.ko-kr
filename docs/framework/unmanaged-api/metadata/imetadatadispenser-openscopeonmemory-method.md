---
title: "IMetaDataDispenser::OpenScopeOnMemory 메서드"
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
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d206863736387df04157ed752a6269b22a884b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="a50c4-102">IMetaDataDispenser::OpenScopeOnMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="a50c4-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="a50c4-103">기존 메타 데이터가 포함 된 메모리 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="a50c4-104">즉,이 메서드는 메타 데이터로 기존 데이터를 처리 하는 메모리의 지정된 된 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="a50c4-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a50c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a50c4-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="a50c4-107">[in] 메모리 영역의 시작 주소를 지정 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a50c4-108">[in] 바이트 단위로 메모리 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a50c4-109">[in] 값은 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열기 위한 모드 (읽기, 쓰기 및 등)를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="a50c4-110">[in] 반환할; 원하는 메타 데이터 인터페이스의 IID 호출자에 게 가져옵니다 (읽기 대상) 또는 (쓰기) 메타 데이터 내보내기 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="a50c4-111">값 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="a50c4-112">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, 또는 IID_IMetaDataImport2입니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a50c4-113">[out] 반환 되는 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50c4-114">설명</span><span class="sxs-lookup"><span data-stu-id="a50c4-114">Remarks</span></span>  
 <span data-ttu-id="a50c4-115">"가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 또는 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 메타 데이터의 메모리 내 복사본을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="a50c4-116">`OpenScopeOnMemory` 메서드는 비슷합니다는 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드를 제외 하 고 관심 있는 메타 데이터 디스크에 파일에서 하지 않고 메모리에 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="a50c4-117">대상 영역의 메모리 공용 언어 런타임 (CLR) 메타 데이터가 포함 되어 있지 않으면는 `OpenScopeOnMemory` 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50c4-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a50c4-118">Requirements</span></span>  
 <span data-ttu-id="a50c4-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a50c4-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50c4-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a50c4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a50c4-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a50c4-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a50c4-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50c4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50c4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a50c4-123">See Also</span></span>  
 [<span data-ttu-id="a50c4-124">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="a50c4-125">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="a50c4-126">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="a50c4-127">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="a50c4-128">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a50c4-129">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="a50c4-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a50c4-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50c4-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
