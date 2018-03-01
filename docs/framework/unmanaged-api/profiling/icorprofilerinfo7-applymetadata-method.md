---
title: "Icorprofilerinfo7:: Applymetadata 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e79d687d3d777895dea9427e4865c2fc866f50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="d34a3-102">Icorprofilerinfo7:: Applymetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="d34a3-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="d34a3-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="d34a3-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d34a3-104">새로 정의한 메타 데이터에 적용 되는 `IMetadataEmit::Define*` 메서드를 지정된 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34a3-105">구문</span><span class="sxs-lookup"><span data-stu-id="d34a3-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34a3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d34a3-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d34a3-107">[in] 변경 된 메타 데이터가 포함 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d34a3-108">설명</span><span class="sxs-lookup"><span data-stu-id="d34a3-108">Remarks</span></span>  
 <span data-ttu-id="d34a3-109">이후 메타 데이터를 변경 하는 경우는 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백에서 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="d34a3-110">`ApplyMetaData`다음과 같은 유형의 메타 데이터를 추가 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="d34a3-111">`AssemblyRef`호출 하 여 만든는 레코드에는 [imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="d34a3-112">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-112">method.</span></span>  
  
-   <span data-ttu-id="d34a3-113">`TypeRef`호출 하 여 만든는 레코드에는 [imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d34a3-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="d34a3-114">`TypeSpec`호출 하 여 만든는 레코드에는 [imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d34a3-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="d34a3-115">`MemberRef`호출 하 여 만든는 레코드에는 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d34a3-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="d34a3-116">`MemberSpec`호출 하 여 만든는 레코드에는 [imetadataemit2:: Definemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d34a3-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="d34a3-117">`UserString`호출 하 여 만든는 레코드에는 [imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d34a3-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34a3-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d34a3-118">Requirements</span></span>  
 <span data-ttu-id="d34a3-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d34a3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34a3-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d34a3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d34a3-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d34a3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d34a3-122">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34a3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34a3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d34a3-123">See Also</span></span>  
 [<span data-ttu-id="d34a3-124">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d34a3-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
