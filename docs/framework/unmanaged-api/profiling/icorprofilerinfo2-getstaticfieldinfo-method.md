---
title: "ICorProfilerInfo2::GetStaticFieldInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7cf16a0fae7f3e2afd095534b2e7f7957d44e3e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="5ad49-102">ICorProfilerInfo2::GetStaticFieldInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="5ad49-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="5ad49-103">지정된 된 필드에 적용 되는 정적의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad49-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ad49-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ad49-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ad49-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5ad49-106">[in] 정적 필드 정의 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="5ad49-107">[in] 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="5ad49-108">[out] 값에 대 한 포인터는 [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) 경우, 정적의 종류에 적용 되는 필드 및 지정 된 필드가 정적 인지 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ad49-109">설명</span><span class="sxs-lookup"><span data-stu-id="5ad49-109">Remarks</span></span>  
 <span data-ttu-id="5ad49-110">정적 필드의 주소를 얻기 위해 호출할 함수를 확인 하려면이 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="5ad49-111">프로파일러 코드는 정적 필드의 주소에 실제로 있는지 확인 하는 메타 데이터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="5ad49-112">정적 리터럴 (즉, 상수) 메타 데이터에만 존재 하 고 주소를가지고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ad49-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ad49-113">Requirements</span></span>  
 <span data-ttu-id="5ad49-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad49-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad49-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ad49-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ad49-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ad49-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ad49-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad49-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad49-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ad49-118">See Also</span></span>  
 [<span data-ttu-id="5ad49-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad49-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5ad49-120">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad49-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
