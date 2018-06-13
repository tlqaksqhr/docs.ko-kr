---
title: ICorProfilerInfo::GetThreadInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f68565977551a54244f3caf6a0250f67005a6ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452884"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="08a29-102">ICorProfilerInfo::GetThreadInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="08a29-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="08a29-103">지정 된 스레드에 대 한 현재 Win32 스레드 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08a29-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a29-104">구문</span><span class="sxs-lookup"><span data-stu-id="08a29-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08a29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08a29-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="08a29-106">[in] id입니다. 현재 Win32 가져올 스레드의 ID</span><span class="sxs-lookup"><span data-stu-id="08a29-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="08a29-107">[out] 지정한 스레드의 현재 Win32 스레드에 대 한 포인터의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="08a29-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08a29-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08a29-108">Requirements</span></span>  
 <span data-ttu-id="08a29-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08a29-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08a29-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08a29-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08a29-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08a29-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08a29-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08a29-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a29-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08a29-113">See Also</span></span>  
 [<span data-ttu-id="08a29-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08a29-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
