---
title: "ICorProfilerInfo::GetHandleFromThread 메서드"
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
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 465fb61d17269873b3a2aa2f323086f209cab946
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="e4e89-102">ICorProfilerInfo::GetHandleFromThread 메서드</span><span class="sxs-lookup"><span data-stu-id="e4e89-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="e4e89-103">Win32 스레드 핸들을 스레드 ID를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e89-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e89-104">구문</span><span class="sxs-lookup"><span data-stu-id="e4e89-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4e89-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4e89-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e4e89-106">[in] 매핑할 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4e89-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="e4e89-107">[out] Win32 스레드 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e4e89-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4e89-108">설명</span><span class="sxs-lookup"><span data-stu-id="e4e89-108">Remarks</span></span>  
 <span data-ttu-id="e4e89-109">프로파일러에서 호출 하 여 Win32 `DuplicateHandle` 사용 하기 전에 핸들에 대해 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e4e89-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4e89-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e89-110">Requirements</span></span>  
 <span data-ttu-id="e4e89-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4e89-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4e89-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4e89-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4e89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4e89-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e89-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4e89-115">See Also</span></span>  
 [<span data-ttu-id="e4e89-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4e89-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
