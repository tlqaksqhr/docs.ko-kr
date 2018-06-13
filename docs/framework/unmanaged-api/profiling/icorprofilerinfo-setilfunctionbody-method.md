---
title: ICorProfilerInfo::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 886bb706be30481c082012bf057a001f37903b16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461658"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="79142-102">ICorProfilerInfo::SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="79142-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="79142-103">지정된 된 모듈에 지정 된 함수의 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79142-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79142-104">구문</span><span class="sxs-lookup"><span data-stu-id="79142-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79142-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79142-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="79142-106">[in] 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="79142-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="79142-107">[in] 바꿀 본문에 대 한 함수의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="79142-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="79142-108">[in] 함수에 대 한 새 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="79142-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79142-109">설명</span><span class="sxs-lookup"><span data-stu-id="79142-109">Remarks</span></span>  
 <span data-ttu-id="79142-110">`SetILFunctionBody` 메서드 메타 데이터에서이 함수의 상대 가상 주소를 대체 하는 새 함수 본문을 가리키는 내부 데이터 구조를 필요에 따라 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79142-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="79142-111">`SetILFunctionBody` 되지 타임 (JIT) 컴파일러에 의해 컴파일된 함수만에 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79142-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="79142-112">사용 하 여는 [icorprofilerinfo:: Getilfunctionbodyallocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) 메서드 버퍼 호환 되는지 확인 하려면 새 메서드에 대 한 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="79142-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79142-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79142-113">Requirements</span></span>  
 <span data-ttu-id="79142-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79142-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79142-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79142-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79142-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79142-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79142-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79142-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79142-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79142-118">See Also</span></span>  
 [<span data-ttu-id="79142-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79142-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
