---
title: "ICorProfilerInfo::GetClassFromToken 메서드"
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
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9972a9d97f94a6286adc0906416349f92e6bf7ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="060ca-102">ICorProfilerInfo::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="060ca-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="060ca-103">메타 데이터 토큰이 지정 된 클래스의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="060ca-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="060ca-105">사용 하 여 [icorprofilerinfo2:: Getclassfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060ca-106">구문</span><span class="sxs-lookup"><span data-stu-id="060ca-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="060ca-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="060ca-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="060ca-108">[in] 클래스를 포함 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="060ca-109">[in] `mdTypeDef` 클래스를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="060ca-110">[out] 클래스 ID에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="060ca-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="060ca-111">설명</span><span class="sxs-lookup"><span data-stu-id="060ca-111">Remarks</span></span>  
 <span data-ttu-id="060ca-112">이 메서드는 사용 되지 않습니다. 대신를 사용 하 여 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` 모든 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="060ca-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="060ca-113">Requirements</span></span>  
 <span data-ttu-id="060ca-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="060ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="060ca-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="060ca-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="060ca-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="060ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="060ca-117">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="060ca-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060ca-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="060ca-118">See Also</span></span>  
 [<span data-ttu-id="060ca-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="060ca-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
