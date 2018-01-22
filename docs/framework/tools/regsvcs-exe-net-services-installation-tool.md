---
title: "Regsvcs.exe(.NET 서비스 설치 도구)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfe7c3e34c2ceaf01f89c1e54f930991ee7e0a2b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="315cf-102">Regsvcs.exe(.NET 서비스 설치 도구)</span><span class="sxs-lookup"><span data-stu-id="315cf-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="315cf-103">.NET 서비스 설치 도구를 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
-   <span data-ttu-id="315cf-104">어셈블리를 로드 및 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-104">Loads and registers an assembly.</span></span>  
  
-   <span data-ttu-id="315cf-105">형식 라이브러리를 지정된 COM+ 응용 프로그램에 생성, 등록 및 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
-   <span data-ttu-id="315cf-106">프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="315cf-107">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-107">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="315cf-108">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="315cf-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="315cf-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="315cf-110">구문</span><span class="sxs-lookup"><span data-stu-id="315cf-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a><span data-ttu-id="315cf-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="315cf-111">Parameters</span></span>  
  
|<span data-ttu-id="315cf-112">인수</span><span class="sxs-lookup"><span data-stu-id="315cf-112">Argument</span></span>|<span data-ttu-id="315cf-113">설명</span><span class="sxs-lookup"><span data-stu-id="315cf-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="315cf-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="315cf-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="315cf-115">소스 어셈블리 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-115">The source assembly file.</span></span> <span data-ttu-id="315cf-116">강력한 이름으로 어셈블리를 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="315cf-117">자세한 내용은 [강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="315cf-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="315cf-118">옵션</span><span class="sxs-lookup"><span data-stu-id="315cf-118">Option</span></span>|<span data-ttu-id="315cf-119">설명</span><span class="sxs-lookup"><span data-stu-id="315cf-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="315cf-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="315cf-120">**/appdir:** *path*</span></span>|<span data-ttu-id="315cf-121">응용 프로그램의 루트 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="315cf-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="315cf-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="315cf-123">찾거나 만들 COM+ 응용 프로그램의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="315cf-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="315cf-124">**/c**</span></span>|<span data-ttu-id="315cf-125">대상 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-125">Creates the target application.</span></span>|  
|<span data-ttu-id="315cf-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="315cf-126">**/componly**</span></span>|<span data-ttu-id="315cf-127">구성 요소만 구성하고 메서드 및 인터페이스는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="315cf-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="315cf-128">**/exapp**</span></span>|<span data-ttu-id="315cf-129">기존 응용 프로그램을 예상하기 위한 도구에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="315cf-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="315cf-130">**/extlb**</span></span>|<span data-ttu-id="315cf-131">기존의 형식 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="315cf-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="315cf-132">**/fc**</span></span>|<span data-ttu-id="315cf-133">대상 응용 프로그램을 찾거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="315cf-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="315cf-134">**/help**</span></span>|<span data-ttu-id="315cf-135">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="315cf-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="315cf-136">**/noreconfig**</span></span>|<span data-ttu-id="315cf-137">기존의 대상 응용 프로그램을 다시 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="315cf-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="315cf-138">**/nologo**</span></span>|<span data-ttu-id="315cf-139">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="315cf-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="315cf-140">**/parname:** *name*</span></span>|<span data-ttu-id="315cf-141">찾거나 만들 COM+ 응용 프로그램의 이름 또는 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="315cf-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="315cf-142">**/reconfig**</span></span>|<span data-ttu-id="315cf-143">기존의 대상 응용 프로그램을 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="315cf-144">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-144">This is the default.</span></span>|  
|<span data-ttu-id="315cf-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="315cf-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="315cf-146">설치할 형식 라이브러리 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="315cf-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="315cf-147">**/u**</span></span>|<span data-ttu-id="315cf-148">대상 응용 프로그램을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="315cf-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="315cf-149">**/quiet**</span></span>|<span data-ttu-id="315cf-150">자동 모드를 지정합니다. 즉, 로고 및 성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="315cf-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="315cf-151">**/?**</span></span>|<span data-ttu-id="315cf-152">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="315cf-153">설명</span><span class="sxs-lookup"><span data-stu-id="315cf-153">Remarks</span></span>  
 <span data-ttu-id="315cf-154">Regsvcs.exe에는 *assemblyFile.dll*에서 지정한 소스 어셈블리 파일이 필요하며,</span><span class="sxs-lookup"><span data-stu-id="315cf-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="315cf-155">이 어셈블리는 강력한 이름으로 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="315cf-156">강력한 이름 서명에 대한 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="315cf-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="315cf-157">대상 응용 프로그램 및 형식 라이브러리 파일의 이름은 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="315cf-158">*applicationName* 인수는 소스 어셈블리 파일에서 생성할 수 있으며, 이 인수가 없는 경우에는 소스 어셈블리 파일에서 생성될 수 있고 Regsvcs.exe로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="315cf-159">*typelibraryfile* 인수를 사용하여 형식 라이브러리 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="315cf-160">형식 라이브러리 이름을 지정하지 않으면 해당 어셈블리 이름이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="315cf-161">Regsvcs.exe는 구성 요소의 메서드를 등록할 때 해당 메서드에 있는 [요청](http://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) 및 [링크 요청](../../../docs/framework/misc/link-demands.md)의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](http://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="315cf-162">이 도구는 완전히 신뢰할 수 있는 환경에서 실행되므로 대부분의 권한 요청이 성공하지만</span><span class="sxs-lookup"><span data-stu-id="315cf-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="315cf-163">Regsvcs.exe는 <xref:System.Security.Permissions.StrongNameIdentityPermission> 또는 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대한 요청 또는 링크 요청에 따라 보호된 메서드가 있는 구성 요소를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="315cf-164">Regsvcs.exe를 사용하려면 로컬 컴퓨터에 대한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="315cf-165">이러한 작업 수행 도중 오류가 발생하면 해당 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="315cf-166">예제</span><span class="sxs-lookup"><span data-stu-id="315cf-166">Examples</span></span>  
 <span data-ttu-id="315cf-167">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 응용 프로그램)에 추가하고 `myTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="315cf-168">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 응용 프로그램)에 추가하고 `newTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="315cf-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="315cf-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="315cf-169">See Also</span></span>  
 [<span data-ttu-id="315cf-170">도구</span><span class="sxs-lookup"><span data-stu-id="315cf-170">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="315cf-171">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="315cf-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="315cf-172">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="315cf-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
