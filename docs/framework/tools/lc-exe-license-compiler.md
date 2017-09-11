---
title: "Lc.exe(라이선스 컴파일러)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f65212d9f62d090cd0c16e15b6678e21b00f235
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="c1a33-102">Lc.exe(라이선스 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="c1a33-102">Lc.exe (License Compiler)</span></span>
<span data-ttu-id="c1a33-103">라이선스 컴파일러를 사용하면 라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함될 수 있는 바이너리 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-103">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="c1a33-104">.licx 텍스트 파일은 폼에 라이센스가 있는 컨트롤을 추가할 때마다 Windows Forms 디자이너가 자동으로 생성하고 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-104">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="c1a33-105">컴파일의 일부로 프로젝트 시스템에서는 .licx 텍스트 파일을 .NET 컨트롤 라이선스를 지원하는 .licenses 이진 리소스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-105">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="c1a33-106">그러면 이진 리소스가 프로젝트 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-106">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="c1a33-107">프로젝트를 빌드할 때 라이선스 컴파일러를 사용하면 32비트 및 64비트 간에 크로스 컴파일이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-107">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="c1a33-108">그 이유는 라이선스 컴파일러가 어셈블리를 로드해야 하며 32비트 응용 프로그램에서 64비트 어셈블리를 로드하는 것은 허용되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-108">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="c1a33-109">이 경우 명령줄의 라이선스 컴파일러를 사용하여 라이선스를 수동으로 컴파일하고 해당 아키텍처를 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a33-109">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="c1a33-110">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c1a33-111">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-111">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c1a33-112">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a33-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="c1a33-113">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-113">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a33-114">구문</span><span class="sxs-lookup"><span data-stu-id="c1a33-114">Syntax</span></span>  
  
```  
      lc /target:  
      targetPE /complist:filename [/outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="c1a33-115">옵션</span><span class="sxs-lookup"><span data-stu-id="c1a33-115">Option</span></span>|<span data-ttu-id="c1a33-116">설명</span><span class="sxs-lookup"><span data-stu-id="c1a33-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c1a33-117">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="c1a33-117">**/complist:** *filename*</span></span>|<span data-ttu-id="c1a33-118">.licenses 파일에 포함할 라이선스가 있는 구성 요소의 목록이 들어 있는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-118">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="c1a33-119">각 구성 요소는 한 줄에 하나의 구성 요소로 전체 이름을 사용하여 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-119">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="c1a33-120">명령줄 사용자는 프로젝트의 각 형식마다 별도의 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-120">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="c1a33-121">Lc.exe로 여러 개의 입력 파일을 사용하여 하나의 .licenses 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-121">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="c1a33-122">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="c1a33-122">**/h**[**elp**]</span></span>|<span data-ttu-id="c1a33-123">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-123">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c1a33-124">**/i:** *모듈*</span><span class="sxs-lookup"><span data-stu-id="c1a33-124">**/i:** *module*</span></span>|<span data-ttu-id="c1a33-125">**/complist** 파일에 나열된 구성 요소가 들어 있는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-125">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="c1a33-126">모듈을 두 개 이상 지정하려면 여러 개의 **/i** 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-126">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="c1a33-127">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="c1a33-127">**/nologo**</span></span>|<span data-ttu-id="c1a33-128">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-128">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="c1a33-129">**/outdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="c1a33-129">**/outdir:** *path*</span></span>|<span data-ttu-id="c1a33-130">출력된 .licenses 파일을 포함할 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-130">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="c1a33-131">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="c1a33-131">**/target:** *targetPE*</span></span>|<span data-ttu-id="c1a33-132">.licenses 파일이 생성되는 대상 실행 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-132">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="c1a33-133">**/v**</span><span class="sxs-lookup"><span data-stu-id="c1a33-133">**/v**</span></span>|<span data-ttu-id="c1a33-134">세부 정보 표시 모드를 지정합니다. 즉, 컴파일 진행 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-134">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="c1a33-135">**@** *파일*</span><span class="sxs-lookup"><span data-stu-id="c1a33-135">**@** *file*</span></span>|<span data-ttu-id="c1a33-136">지시 파일(.rsp)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-136">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="c1a33-137">**/?**</span><span class="sxs-lookup"><span data-stu-id="c1a33-137">**/?**</span></span>|<span data-ttu-id="c1a33-138">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-138">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1a33-139">예제</span><span class="sxs-lookup"><span data-stu-id="c1a33-139">Example</span></span>  
  
1.  <span data-ttu-id="c1a33-140">`HostApp.exe`라는 응용 프로그램의 `Samples.DLL`에 들어 있는 라이선스가 있는 컨트롤 `MyCompany.Samples.LicControl1`을 사용하는 경우 다음 내용이 들어 있는 `HostAppLic.txt`를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-140">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```  
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2.  <span data-ttu-id="c1a33-141">다음 명령을 사용하여 `HostApp.exe.licenses`라는 .licenses 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-141">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3.  <span data-ttu-id="c1a33-142">해당 .licenses 파일을 리소스로 포함하는 `HostApp.exe`를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-142">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="c1a33-143">C# 응용 프로그램을 빌드하는 경우에는 다음 명령을 사용하여 해당 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-143">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```  
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="c1a33-144">다음 명령을 사용하여 `myApp.licenses`, `hostapplic.txt` 및 `hostapplic2.txt`로 지정된, 라이선스가 있는 구성 요소 목록에서 `hostapplic3.txt`를 컴파일하고,</span><span class="sxs-lookup"><span data-stu-id="c1a33-144">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="c1a33-145">`modulesList` 인수를 사용하여 라이선스가 있는 구성 요소가 들어 있는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-145">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="c1a33-146">지시 파일 예</span><span class="sxs-lookup"><span data-stu-id="c1a33-146">Response File Example</span></span>  
 <span data-ttu-id="c1a33-147">다음 목록에서는 지시 파일의 예로 `response.rsp`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-147">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="c1a33-148">지시 파일에 대한 자세한 내용은 [지시 파일](/visualstudio/msbuild/msbuild-response-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a33-148">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```  
/target:hostapp.exe  
/complist:hostapplic.txt   
/i:WFCPrj.dll   
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="c1a33-149">다음 명령줄은 `response.rsp` 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a33-149">The following command line uses the `response.rsp` file.</span></span>  
  
```  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1a33-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1a33-150">See Also</span></span>  
 <span data-ttu-id="c1a33-151">[도구](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1a33-151">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="c1a33-152">[Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span><span class="sxs-lookup"><span data-stu-id="c1a33-152">[Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span></span>  
 [<span data-ttu-id="c1a33-153">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="c1a33-153">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

