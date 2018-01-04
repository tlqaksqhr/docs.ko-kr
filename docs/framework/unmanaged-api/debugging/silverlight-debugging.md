---
title: "Silverlight 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6869e58ca47b7b55a5b988e0f6ae4a224f0f35a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="silverlight-debugging"></a><span data-ttu-id="4dbbc-102">Silverlight 디버깅</span><span class="sxs-lookup"><span data-stu-id="4dbbc-102">Silverlight Debugging</span></span>
<span data-ttu-id="4dbbc-103">이 섹션의 항목에서는 CLR(공용 언어 런타임)이 Windows 운영 체제나 Macintosh 플랫폼에서 실행 중인 Silverlight 기반 응용 프로그램 디버그를 지원하기 위해 제공하는 환경 및 인터페이스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dbbc-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4dbbc-104">In This Section</span></span>  
 [<span data-ttu-id="4dbbc-105">EnumerateCLRs 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="4dbbc-106">프로세스의 CLR을 열거하기 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="4dbbc-107">CloseCLREnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="4dbbc-108">반환 된 핸들 배열에 있는 모든 유효한 CLR 계속-시작 이벤트를 닫습니다는 [EnumerateCLRs 함수](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), 핸들 및 문자열 경로 배열에 대 한 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="4dbbc-109">CreateCoreClrDebugTarget 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="4dbbc-110">프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="4dbbc-111">CreateCordbObject 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="4dbbc-112">원격 프로세스에서 관리되는 디버깅 세션을 인스턴스화하기 위한 기능을 제공하는 디버거 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="4dbbc-113">CreateVersionStringFromModule 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="4dbbc-114">대상 프로세스의 CLR 경로에서 버전 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="4dbbc-115">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="4dbbc-116">반환 된 CLR 버전 문자열을 수락 [CreateVersionStringFromModule 함수](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)작동 하 고 해당 디버거 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="4dbbc-117">CoreClrDebugProcInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="4dbbc-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="4dbbc-118">원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="4dbbc-119">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="4dbbc-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="4dbbc-120">원격 컴퓨터의 프로세스에서 로드된 CLR 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="4dbbc-121">GetStartupNotificationEvent 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="4dbbc-122">지정된 대상 프로세스에 로드 중인 CLR(공용 언어 런타임)에서 신호를 전송할 이벤트 핸들을 만들거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="4dbbc-123">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4dbbc-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="4dbbc-124">프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="4dbbc-125">InitDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="4dbbc-126">프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="4dbbc-127">ShutdownDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="4dbbc-128">원격 대상 컴퓨터에 대한 연결을 위해 전송 관리자를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="4dbbc-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dbbc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4dbbc-129">See Also</span></span>  
 [<span data-ttu-id="4dbbc-130">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="4dbbc-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [<span data-ttu-id="4dbbc-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4dbbc-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4dbbc-132">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="4dbbc-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [<span data-ttu-id="4dbbc-133">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="4dbbc-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="4dbbc-134">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="4dbbc-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
