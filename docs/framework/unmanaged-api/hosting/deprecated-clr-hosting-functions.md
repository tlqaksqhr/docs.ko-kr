---
title: "사용되지 않는 CLR 호스팅 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985425ad44003f5971b21f107fad322f2123f6ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="99639-102">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="99639-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="99639-103">이 섹션에서는 이전 버전의 호스팅 API에서 사용 되는 관리 되지 않는 전역 정적 함수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="99639-104">인프라 기능을 제외 하 고 (`_Cor*` 함수),.NET Framework 에서만 사용 되는, 이러한 함수에 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="99639-105">활성화 함수</span><span class="sxs-lookup"><span data-stu-id="99639-105">Activation functions</span></span>  
 [<span data-ttu-id="99639-106">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="99639-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="99639-107">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-107">Deprecated.</span></span> <span data-ttu-id="99639-108">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99639-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="99639-109">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="99639-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="99639-110">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-110">Obsolete.</span></span> <span data-ttu-id="99639-111">공용 언어 런타임 (CLR)를 초기화 하려면 사용 하 여 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="99639-112">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="99639-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="99639-113">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-113">Deprecated.</span></span> <span data-ttu-id="99639-114">CLR 실행 엔진 프로세스에 로드 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="99639-115">사용 하 여 [iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="99639-116">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="99639-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="99639-117">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-117">Deprecated.</span></span> <span data-ttu-id="99639-118">XML 파일에 저장 된 버전 정보를 사용 하 여 공용 언어 런타임 (CLR) 프로세스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="99639-119">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="99639-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="99639-120">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-120">Deprecated.</span></span> <span data-ttu-id="99639-121">관리 되지 않는 호스트 프로세스에 CLR을 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="99639-122">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="99639-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="99639-123">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-123">Deprecated.</span></span> <span data-ttu-id="99639-124">XML 파일에서 읽을 수 있는 버전 정보를 사용 하 여 프로세스에 CLR을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="99639-125">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="99639-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="99639-126">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-126">Deprecated.</span></span> <span data-ttu-id="99639-127">관리 되지 않는 호스트 프로세스에 CLR을 로드할 수 있도록 하 고 CLR의 동작을 지정 하는 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="99639-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="99639-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="99639-129">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-129">Deprecated.</span></span> <span data-ttu-id="99639-130">호스트 프로세스에 지정된 된 버전의 CLR 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="99639-131">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="99639-132">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-132">Deprecated.</span></span> <span data-ttu-id="99639-133">필요한 CLR 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="99639-134">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="99639-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="99639-135">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-135">Deprecated.</span></span> <span data-ttu-id="99639-136">프로세스에 로드 된 CLR의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="99639-137">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="99639-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="99639-138">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-138">Deprecated.</span></span> <span data-ttu-id="99639-139">사용 하는 CLR의 최신 설치 버전에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="99639-140">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="99639-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="99639-141">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-141">Deprecated.</span></span> <span data-ttu-id="99639-142">응용 프로그램에서 요청한 CLR에 대 한 버전 및 디렉터리 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="99639-143">CLR 버전 함수</span><span class="sxs-lookup"><span data-stu-id="99639-143">CLR version functions</span></span>  
 <span data-ttu-id="99639-144">이 섹션의 함수는 CLR 버전;를 반환합니다. CLR를 활성화 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="99639-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="99639-145">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="99639-146">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-146">Deprecated.</span></span> <span data-ttu-id="99639-147">현재 프로세스에서 실행 되는 CLR의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="99639-148">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="99639-149">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-149">Deprecated.</span></span> <span data-ttu-id="99639-150">지정된 된 버퍼를 사용 하 여 지정된 된 파일의 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="99639-151">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="99639-152">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-152">Deprecated.</span></span> <span data-ttu-id="99639-153">지정된 된 응용 프로그램에서 요청한 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="99639-154">해당 버전이 설치 되지 않은 경우 요청 된 버전 이전에 설치 된 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="99639-155">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="99639-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="99639-156">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-156">Deprecated.</span></span> <span data-ttu-id="99639-157">지정된 된 CLSID 사용 하 여 클래스에 대 한 적절 한 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="99639-158">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="99639-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="99639-159">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-159">Deprecated.</span></span> <span data-ttu-id="99639-160">지정 된 프로세스 핸들과 연결 된 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="99639-161">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="99639-162">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-162">Deprecated.</span></span> <span data-ttu-id="99639-163">호스트가 명시적으로 CLR을 초기화 하기 전에 프로세스에서 사용할 CLR의 버전은 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="99639-164">호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="99639-164">Hosting functions</span></span>  
 [<span data-ttu-id="99639-165">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="99639-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="99639-166">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-166">Deprecated.</span></span> <span data-ttu-id="99639-167">지정된 된 라이브러리에 지정 된 이름 및 매개 변수를 가진 함수를 호출 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="99639-168">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="99639-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="99639-169">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-169">Deprecated.</span></span> <span data-ttu-id="99639-170">프로세스에서 COM 어셈블리를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="99639-171">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="99639-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="99639-172">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-172">Deprecated.</span></span> <span data-ttu-id="99639-173">현재 관리 되지 않는 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="99639-174">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="99639-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="99639-175">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-175">Deprecated.</span></span> <span data-ttu-id="99639-176">지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에 있는 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="99639-177">CorMarkThreadInThreadPool 함수</span><span class="sxs-lookup"><span data-stu-id="99639-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="99639-178">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-178">Deprecated.</span></span> <span data-ttu-id="99639-179">관리 코드의 실행에 대 한 현재 실행 중인 스레드 풀 스레드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="99639-180">.NET Framework 버전 2.0 이상에서는이 함수는 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="99639-181">필요 하지 하 고 사용자 코드에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="99639-182">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="99639-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="99639-183">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-183">Obsolete.</span></span> <span data-ttu-id="99639-184">CLR은 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="99639-185">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="99639-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="99639-186">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="99639-187">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="99639-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="99639-188">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-188">Deprecated.</span></span> <span data-ttu-id="99639-189">만듭니다는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 지정된 된 버전 정보에 따라 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="99639-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="99639-190">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="99639-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="99639-191">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-191">Deprecated.</span></span> <span data-ttu-id="99639-192">만듭니다는 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="99639-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="99639-193">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="99639-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="99639-194">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-194">Deprecated.</span></span> <span data-ttu-id="99639-195">제거 프로그램 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="99639-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="99639-196">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="99639-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="99639-197">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-197">Deprecated.</span></span> <span data-ttu-id="99639-198">관리 되는 코드를 실행 하는 CLR를 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="99639-199">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="99639-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="99639-200">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-200">Deprecated.</span></span> <span data-ttu-id="99639-201">CLR 호스트에 알리기 위해 호출 하는 함수를 가리키는 초기화가 시작 또는 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="99639-202">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="99639-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="99639-203">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-203">Deprecated.</span></span> <span data-ttu-id="99639-204">Id를 관리 하는 CLR을 허용 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="99639-205">LoadLibraryShim 함수</span><span class="sxs-lookup"><span data-stu-id="99639-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="99639-206">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-206">Deprecated.</span></span> <span data-ttu-id="99639-207">지정 된 버전의.NET Framework DLL을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="99639-208">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="99639-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="99639-209">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-209">Deprecated.</span></span> <span data-ttu-id="99639-210">현재 스레드의 기본 문화권을 사용 하 여 오류 메시지에는 HRESULT 값을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="99639-211">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="99639-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="99639-212">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-212">Deprecated.</span></span> <span data-ttu-id="99639-213">HRESULT 값을 지정된 된 문화권에 대 한 적절 한 오류 메시지를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="99639-214">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="99639-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="99639-215">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-215">Deprecated.</span></span> <span data-ttu-id="99639-216">Overlapped는 호스트에 알리는 하는 함수를 가리키는 (즉, 비동기) 장치에 대 한 I/O 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="99639-217">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="99639-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="99639-218">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-218">Deprecated.</span></span> <span data-ttu-id="99639-219">스레드 실행을 시작 했음을 호스트에 알려 줍니다 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="99639-220">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="99639-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="99639-221">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-221">Deprecated.</span></span> <span data-ttu-id="99639-222">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="99639-223">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="99639-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="99639-224">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99639-224">Deprecated.</span></span> <span data-ttu-id="99639-225">대기 핸들 중 하나 신호 되었거나 시간이 초과 되었습니다 호스트를 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="99639-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="99639-226">인프라 함수</span><span class="sxs-lookup"><span data-stu-id="99639-226">Infrastructure functions</span></span>  
 <span data-ttu-id="99639-227">이 섹션의 함수는.NET Framework에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99639-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="99639-228">_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="99639-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="99639-229">CLR을 초기화 하 고 DLL 어셈블리의 CLR 헤더의 관리 되는 진입점을 찾고 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="99639-230">_CorExeMain 함수</span><span class="sxs-lookup"><span data-stu-id="99639-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="99639-231">CLR을 초기화 하 고 실행 가능한 어셈블리의 CLR 헤더의 관리 되는 진입점을 찾고 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="99639-232">_CorExeMain2 함수</span><span class="sxs-lookup"><span data-stu-id="99639-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="99639-233">지정된 된 메모리 매핑된 코드에서 진입점을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99639-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="99639-234">이 함수는 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99639-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="99639-235">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="99639-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="99639-236">관리 모듈 이미지가 로드 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="99639-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="99639-237">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="99639-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="99639-238">관리 모듈 이미지가 유효성을 검사 하 고 로드 된 후에 운영 체제 로더를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="99639-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99639-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99639-239">See Also</span></span>  
 [<span data-ttu-id="99639-240">.NET Framework 4 호스팅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="99639-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
