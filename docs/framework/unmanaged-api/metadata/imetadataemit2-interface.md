---
title: "IMetaDataEmit2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94180a1f844ac43d8a42be59ac4fca807a70ec70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="a9c1f-102">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c1f-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="a9c1f-103">확장 된 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 주로 제네릭 형식을 사용할 수 있는 기능을 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9c1f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-104">Methods</span></span>  
  
|<span data-ttu-id="a9c1f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-105">Method</span></span>|<span data-ttu-id="a9c1f-106">설명</span><span class="sxs-lookup"><span data-stu-id="a9c1f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9c1f-107">DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="a9c1f-108">제네릭 형식 매개 변수에 대 한 정의 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="a9c1f-109">DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="a9c1f-110">메서드의 제네릭 인스턴스를 만들고 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="a9c1f-111">GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="a9c1f-112">편집 하며 계속 하기는 현재 세션에 대 한 변경 내용을 표현 하는 데 필요한 데이터 크기의 차이 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="a9c1f-113">ResetENCLog 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="a9c1f-114">편집 하며 계속 하기 로그를 다시 설정 하 고 새 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="a9c1f-115">SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="a9c1f-116">편집 하며 계속 하기는 현재 세션에서 지정된 된 파일 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="a9c1f-117">SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="a9c1f-118">편집 하며 계속 하기는 현재 세션에서 변경 내용을 메모리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="a9c1f-119">SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="a9c1f-120">변경 내용을 편집 하며 계속 하기는 현재 세션에서 지정 된 스트림에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="a9c1f-121">SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c1f-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="a9c1f-122">지정 된 토큰에서 참조 하는 제네릭 매개 변수 정의 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9c1f-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9c1f-123">Requirements</span></span>  
 <span data-ttu-id="a9c1f-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c1f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c1f-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9c1f-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9c1f-126">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a9c1f-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c1f-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c1f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c1f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9c1f-128">See Also</span></span>  
 [<span data-ttu-id="a9c1f-129">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c1f-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="a9c1f-130">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c1f-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
