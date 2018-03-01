---
title: "ICorDebug::CreateProcess 메서드"
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
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="9e0cb-102">ICorDebug::CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="9e0cb-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="9e0cb-103">프로세스와 디버거 제어 기본 스레드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e0cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e0cb-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e0cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e0cb-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="9e0cb-106">[in] 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="9e0cb-107">모듈 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="9e0cb-108">[in] 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="9e0cb-109">응용 프로그램 이름 (예: "SomeApp.exe") 첫 번째 인수로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="9e0cb-110">[in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스에 대 한 보안 설명자를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="9e0cb-111">경우 `lpProcessAttributes` 가 null 인 프로세스 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="9e0cb-112">[in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스의 주 스레드에 대 한 보안 설명자를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="9e0cb-113">경우 `lpThreadAttributes` 가 null 인 스레드가 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="9e0cb-114">[in] 로 설정 `true` 시작된 프로세스에 의해 상속 가능한 각 핸들 호출 프로세스에이 상속 됨을 나타내기 위해 또는 `false` 핸들이 상속 되지 않습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="9e0cb-115">상속 된 핸들에는 원래 핸들와 동일한 값 및 액세스 권한을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="9e0cb-116">[in] 비트 조합 된 [Win32 프로세스 생성 플래그가](http://go.microsoft.com/fwlink/?linkid=69981) 우선 순위 클래스 및 시작 된 프로세스의 동작을 제어 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="9e0cb-117">[in] 새로운 프로세스에 대 한 환경 블록에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="9e0cb-118">[in] 프로세스에 대 한 현재 디렉터리에 전체 경로 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="9e0cb-119">이 매개 변수가 null 이면 새 프로세스에 호출 프로세스와 현재 동일한 드라이브와 디렉터리 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="9e0cb-120">[in] Win32에 대 한 포인터 `STARTUPINFOW` 창 스테이션, 바탕 화면, 표준 핸들 및 시작 된 프로세스에 대 한 주 창의 모양을 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="9e0cb-121">[in] Win32에 대 한 포인터 `PROCESS_INFORMATION` 시작 프로세스에 대 한 식별 정보를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="9e0cb-122">[in] 디버깅 옵션을 지정 하는 CorDebugCreateProcessFlags 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9e0cb-123">[out] 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e0cb-124">설명</span><span class="sxs-lookup"><span data-stu-id="9e0cb-124">Remarks</span></span>  
 <span data-ttu-id="9e0cb-125">이 메서드의 매개 변수는 Win32의와 동일 `CreateProcess` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="9e0cb-126">관리 되지 않는 혼합 모드 디버깅을 사용 하려면 설정 `dwCreationFlags` DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="9e0cb-127">관리 되는 디버깅만 사용 하려는 경우에 이러한 플래그를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="9e0cb-128">디버거 및 프로세스를 디버깅 (연결 된 프로세스) 하는 경우 단일 콘솔을 공유 하 고 콘솔 잠금을 유지 하 고 디버그 이벤트에서 중지 하는 연결 된 프로세스에 대 한 가능한는 interop 디버깅을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="9e0cb-129">디버거는 콘솔을 사용 하려는 모든 시도가 차단 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="9e0cb-130">이 문제를 방지 하려면에서 CREATE_NEW_CONSOLE 플래그를 설정의 `dwCreationFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="9e0cb-131">Interop 디버깅 IA 64 기반 및 AMD64 기반 플랫폼에서와 같은 Win9x 및 비 x86 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e0cb-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e0cb-132">Requirements</span></span>  
 <span data-ttu-id="9e0cb-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0cb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e0cb-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e0cb-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e0cb-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e0cb-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e0cb-136">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e0cb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0cb-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e0cb-137">See Also</span></span>  
 [<span data-ttu-id="9e0cb-138">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e0cb-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
