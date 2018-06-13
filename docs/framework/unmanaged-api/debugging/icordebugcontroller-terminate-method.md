---
title: ICorDebugController::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7a95f09d1baebed65bae994550431d88ba0dfc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412473"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="0ed42-102">ICorDebugController::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="0ed42-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="0ed42-103">지정된 된 종료 코드가 사용 하 여 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed42-104">이 메서드는 Win32에 대 한 래퍼 `TerminateProcess` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="0ed42-105">따라서 `Terminate` 종료 코드를 사용 하 여 동일한 방식으로 Win32 `TerminateProcess` 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ed42-106">구문</span><span class="sxs-lookup"><span data-stu-id="0ed42-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ed42-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ed42-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="0ed42-108">[in] 종료 코드는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="0ed42-109">유효한 숫자 값은 Winbase.h에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ed42-110">설명</span><span class="sxs-lookup"><span data-stu-id="0ed42-110">Remarks</span></span>  
 <span data-ttu-id="0ed42-111">프로세스가 시기를 중지 하는 경우 `Terminate` 는 호출 프로세스는 계속 진행 해야를 사용 하 여는 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드 디버거를 통해 종료에 대 한 확인을 받을 수 있도록는 [ Icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 또는 [icordebugmanagedcallback:: Exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed42-112">이 메서드는 응용 프로그램 도메인에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="0ed42-113">즉,에서 구현 되지 않음는 <xref:System.AppDomain> 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ed42-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ed42-114">Requirements</span></span>  
 <span data-ttu-id="0ed42-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed42-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ed42-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ed42-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ed42-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ed42-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ed42-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ed42-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed42-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ed42-119">See Also</span></span>  
 
