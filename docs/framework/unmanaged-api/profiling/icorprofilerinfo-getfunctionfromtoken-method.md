---
title: "ICorProfilerInfo::GetFunctionFromToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionFromToken
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c90a63f075c392ca3ff02a47190f9c4dfe6aad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="3eae8-102">ICorProfilerInfo::GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="3eae8-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="3eae8-103">함수의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-103">Gets the ID of a function.</span></span> <span data-ttu-id="3eae8-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3eae8-105">사용 하 여 [icorprofilerinfo2:: Getfunctionfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eae8-106">구문</span><span class="sxs-lookup"><span data-stu-id="3eae8-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3eae8-107">설명</span><span class="sxs-lookup"><span data-stu-id="3eae8-107">Remarks</span></span>  
 <span data-ttu-id="3eae8-108">`GetFunctionFromToken` 메서드는 제네릭 함수 또는 제네릭 형식에는 함수에 대해 작동 하지 것입니다;는 이제 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="3eae8-109">사용 하 여 `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` 모든 함수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eae8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3eae8-110">Requirements</span></span>  
 <span data-ttu-id="3eae8-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eae8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eae8-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3eae8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3eae8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eae8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eae8-114">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3eae8-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eae8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3eae8-115">See Also</span></span>  
 [<span data-ttu-id="3eae8-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eae8-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
