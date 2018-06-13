---
title: ICorDebugController::EnumerateThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f8276e2a8fd1bdc546add2ae1ca5d96298186c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412833"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="11a63-102">ICorDebugController::EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="11a63-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="11a63-103">프로세스에서 현재 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11a63-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a63-104">구문</span><span class="sxs-lookup"><span data-stu-id="11a63-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a63-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11a63-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="11a63-106">[out] 프로세스에서 활성화 되는 모든 관리 되는 스레드에 대 한 열거자를 나타내는 "ICorDebugThreadEnum" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11a63-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a63-107">설명</span><span class="sxs-lookup"><span data-stu-id="11a63-107">Remarks</span></span>  
 <span data-ttu-id="11a63-108">스레드 후 활성 것으로 간주 되는 [icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 콜백 처리 된 후에 하기 전에 [icordebugmanagedcallback:: Exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) 콜백 처리 된 후에 .</span><span class="sxs-lookup"><span data-stu-id="11a63-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="11a63-109">관리 되는 스레드 반드시 없을 수도 있는 관리 되는 프레임 스택에.</span><span class="sxs-lookup"><span data-stu-id="11a63-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="11a63-110">스레드 이전에 열거할 수는 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a63-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="11a63-111">열거형은 자연스럽 게 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a63-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a63-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11a63-112">Requirements</span></span>  
 <span data-ttu-id="11a63-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11a63-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a63-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11a63-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11a63-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a63-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a63-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a63-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11a63-117">See Also</span></span>  
 
