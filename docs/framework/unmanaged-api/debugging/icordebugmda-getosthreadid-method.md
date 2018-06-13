---
title: ICorDebugMDA::GetOSThreadId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20833624b4b853a1a56964e11a25f446c6b39053
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414715"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="2f08b-102">ICorDebugMDA::GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="2f08b-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="2f08b-103">관리 디버깅 도우미 (MDA)으로 표시 된 운영 체제 (OS) 스레드 식별자를 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f08b-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f08b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f08b-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f08b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f08b-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="2f08b-106">[out] 운영 체제 스레드 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f08b-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f08b-107">설명</span><span class="sxs-lookup"><span data-stu-id="2f08b-107">Remarks</span></span>  
 <span data-ttu-id="2f08b-108">운영 체제 스레드가 네이티브 스레드인 또는 관리 코드를 아직 시작 되지 않은 관리 되는 스레드 MDA는 발생 하는 경우는 ICorDebugThread 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f08b-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f08b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f08b-109">Requirements</span></span>  
 <span data-ttu-id="2f08b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f08b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f08b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f08b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f08b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f08b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f08b-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f08b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f08b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f08b-114">See Also</span></span>  
 [<span data-ttu-id="2f08b-115">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f08b-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="2f08b-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="2f08b-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
