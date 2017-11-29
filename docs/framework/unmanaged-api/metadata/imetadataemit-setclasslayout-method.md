---
title: "IMetaDataEmit::SetClassLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a68d94cbea408bee90b117965f83f760ba7ea5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="51170-102">IMetaDataEmit::SetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="51170-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="51170-103">이전 호출에서 정의 된 클래스에 대 한 필드 레이아웃을 완료 [DefineTypeDef 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51170-104">구문</span><span class="sxs-lookup"><span data-stu-id="51170-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51170-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51170-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="51170-106">[in] `mdTypeDef` 토큰을 배치 하는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="51170-107">[in] 압축 크기: 1, 2, 4, 8 또는 16 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="51170-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="51170-108">압축 크기는 인접 한 필드 사이의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="51170-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="51170-109">[in] 배열을 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 구조를 각각 클래스의 필드와 필드는 클래스 내에서 오프셋을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="51170-110">사용 하 여 배열을 종료 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="51170-111">[in] 클래스의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51170-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51170-112">설명</span><span class="sxs-lookup"><span data-stu-id="51170-112">Remarks</span></span>  
 <span data-ttu-id="51170-113">클래스를 호출 하 여 초기에 정의 되는 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드 및 클래스의 필드에 대 한 세 가지 레이아웃 중 하나를 지정: 자동, 순차적으로 또는 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="51170-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="51170-114">일반적으로 자동 레이아웃을 사용 하는 필드의 레이아웃에 가장 좋은 방법은 선택 하 여 런타임에서 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="51170-115">그러나 필드를 비관리 코드에서 사용 하는 정렬 기준에 따라 레이아웃을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51170-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="51170-116">이 경우 순차적으로 또는 명시적 레이아웃 및 호출을 선택 `SetClassLayout` 필드의 레이아웃을 완료 하려면:</span><span class="sxs-lookup"><span data-stu-id="51170-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="51170-117">순차적 레이아웃이: 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="51170-118">필드의 자연 크기 또는 압축 크기는 필드의 더 작은 오프셋에 따라 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51170-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="51170-119">설정 `rFieldOffsets` 및 `ulClassSize` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51170-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="51170-120">명시적 레이아웃: 각 필드의 오프셋을 지정 하거나, 클래스 크기와 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51170-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51170-121">Requirements</span></span>  
 <span data-ttu-id="51170-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51170-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51170-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51170-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51170-124">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="51170-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51170-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51170-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51170-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51170-126">See Also</span></span>  
 [<span data-ttu-id="51170-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51170-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="51170-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51170-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
