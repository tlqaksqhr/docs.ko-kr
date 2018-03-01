---
title: "ICorProfilerInfo::GetFunctionFromIP 메서드"
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
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 144d80bb0e4111e319427d6a265d199b04b7f863
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="7207b-102">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="7207b-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="7207b-103">관리 되는 코드의 명령 포인터에 매핑하는 `FunctionID`합니다.</span><span class="sxs-lookup"><span data-stu-id="7207b-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7207b-104">구문</span><span class="sxs-lookup"><span data-stu-id="7207b-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7207b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7207b-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="7207b-106">[in] 관리 코드에서 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7207b-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="7207b-107">[out] 반환 된 함수 id입니다.</span><span class="sxs-lookup"><span data-stu-id="7207b-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7207b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7207b-108">Requirements</span></span>  
 <span data-ttu-id="7207b-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7207b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7207b-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7207b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7207b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7207b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7207b-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7207b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7207b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7207b-113">See Also</span></span>  
 [<span data-ttu-id="7207b-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7207b-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
