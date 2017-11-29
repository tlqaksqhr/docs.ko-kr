---
title: "ICorDebugRemote 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemote
helpviewer_keywords: ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6195b53d11877c6b7b2a52c3fd8d194dfb51810
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="e39e5-102">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e39e5-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="e39e5-103">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e39e5-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="e39e5-104">Syntax</span></span>  
  
```  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e39e5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e39e5-105">Methods</span></span>  
  
|<span data-ttu-id="e39e5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e39e5-106">Method</span></span>|<span data-ttu-id="e39e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="e39e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e39e5-108">Icordebugremote:: Createprocessex 메서드</span><span class="sxs-lookup"><span data-stu-id="e39e5-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="e39e5-109">관리 되는 디버깅에 대 한 원격 컴퓨터에서 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e39e5-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="e39e5-110">Icordebugremote:: Debugactiveprocessex 메서드</span><span class="sxs-lookup"><span data-stu-id="e39e5-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="e39e5-111">디버거에서 원격 컴퓨터에서 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e39e5-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e39e5-112">설명</span><span class="sxs-lookup"><span data-stu-id="e39e5-112">Remarks</span></span>  
 <span data-ttu-id="e39e5-113">현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상 디버깅에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e39e5-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e39e5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e39e5-114">Requirements</span></span>  
 <span data-ttu-id="e39e5-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e39e5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e39e5-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e39e5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e39e5-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e39e5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e39e5-118">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e39e5-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39e5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e39e5-119">See Also</span></span>  
 [<span data-ttu-id="e39e5-120">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e39e5-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="e39e5-121">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e39e5-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="e39e5-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e39e5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
