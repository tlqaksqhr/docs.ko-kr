---
title: "ICorProfilerInfo2::EnumModuleFrozenObjects 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.EnumModuleFrozenObjects
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3866d91d28258eaee78e6025175628796a369f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="08427-102">ICorProfilerInfo2::EnumModuleFrozenObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="08427-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="08427-103">지정된 된 모듈에 고정된 된 개체를 반복할 수 있는 열거자를 가져옵니다. 이 메서드는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08427-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08427-104">구문</span><span class="sxs-lookup"><span data-stu-id="08427-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08427-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08427-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="08427-106">[in] 고정된 된 개체를 열거를 포함 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08427-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="08427-107">[out] 주소에 대 한 포인터는 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) 고정된 개체를 열거 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="08427-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08427-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08427-108">Requirements</span></span>  
 <span data-ttu-id="08427-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08427-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08427-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08427-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08427-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08427-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08427-112">**.NET framework 버전:** 3.5, 3.0 SP1, 3.0, 2.0 s p 1에서는 2.0</span><span class="sxs-lookup"><span data-stu-id="08427-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08427-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08427-113">See Also</span></span>  
 [<span data-ttu-id="08427-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08427-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="08427-115">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08427-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
