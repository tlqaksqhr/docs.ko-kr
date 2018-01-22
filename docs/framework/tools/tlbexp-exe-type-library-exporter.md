---
title: "Tlbexp.exe(형식 라이브러리 내보내기)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting type library [.NET Framework]
- exporter tool [.NET Framework]
- Tlbexp.exe
- Type Library Exporter
- type libraries [.NET Framework], exporting
ms.assetid: a487d61b-d166-467b-a7ca-d8b52fbff42d
caps.latest.revision: "35"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47710b81de79a9dfbb6bddd39035be2986350b0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="tlbexpexe-type-library-exporter"></a><span data-ttu-id="32acd-102">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="32acd-102">Tlbexp.exe (Type Library Exporter)</span></span>
<span data-ttu-id="32acd-103">형식 라이브러리 내보내기를 사용하면 공용 언어 런타임 어셈블리에 정의된 형식을 설명하는 형식 라이브러리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-103">The Type Library Exporter generates a type library that describes the types defined in a common language runtime assembly.</span></span>  
  
 <span data-ttu-id="32acd-104">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="32acd-105">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="32acd-106">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32acd-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="32acd-107">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32acd-108">구문</span><span class="sxs-lookup"><span data-stu-id="32acd-108">Syntax</span></span>  
  
```  
tlbexp assemblyName [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32acd-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32acd-109">Parameters</span></span>  
  
|<span data-ttu-id="32acd-110">인수</span><span class="sxs-lookup"><span data-stu-id="32acd-110">Argument</span></span>|<span data-ttu-id="32acd-111">설명</span><span class="sxs-lookup"><span data-stu-id="32acd-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="32acd-112">*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="32acd-112">*assemblyName*</span></span>|<span data-ttu-id="32acd-113">형식 라이브러리를 내보내려는 대상 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-113">The assembly for which to export a type library.</span></span>|  
  
|<span data-ttu-id="32acd-114">옵션</span><span class="sxs-lookup"><span data-stu-id="32acd-114">Option</span></span>|<span data-ttu-id="32acd-115">설명</span><span class="sxs-lookup"><span data-stu-id="32acd-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="32acd-116">**/asmpath:** *directory*</span><span class="sxs-lookup"><span data-stu-id="32acd-116">**/asmpath:** *directory*</span></span>|<span data-ttu-id="32acd-117">어셈블리를 검색할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-117">Specifies the location to search for assemblies.</span></span> <span data-ttu-id="32acd-118">이 옵션을 사용하는 경우 현재 디렉터리를 포함하여 참조되는 어셈블리를 검색할 위치를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-118">If you use this option, you must explicitly specify the locations to search for referenced assemblies, including the current directory.</span></span><br /><br /> <span data-ttu-id="32acd-119">**asmpath** 옵션을 사용하는 경우 형식 라이브러리 내보내기가 GAC(전역 어셈블리 캐시)에서 어셈블리를 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-119">When you use the **asmpath** option, the Type Library Exporter will not look for an assembly in the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="32acd-120">**/help**</span><span class="sxs-lookup"><span data-stu-id="32acd-120">**/help**</span></span>|<span data-ttu-id="32acd-121">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-121">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="32acd-122">**/names:** *filename*</span><span class="sxs-lookup"><span data-stu-id="32acd-122">**/names:** *filename*</span></span>|<span data-ttu-id="32acd-123">형식 라이브러리에 있는 이름을 대문자로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-123">Specifies the capitalization of names in a type library.</span></span> <span data-ttu-id="32acd-124">*filename* 인수는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-124">The *filename* argument is a text file.</span></span> <span data-ttu-id="32acd-125">파일의 각 줄에서 형식 라이브러리에 있는 이름을 하나씩 대문자로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-125">Each line in the file specifies the capitalization of one name in the type library.</span></span>|  
|<span data-ttu-id="32acd-126">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="32acd-126">**/nologo**</span></span>|<span data-ttu-id="32acd-127">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-127">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="32acd-128">**/oldnames**</span><span class="sxs-lookup"><span data-stu-id="32acd-128">**/oldnames**</span></span>|<span data-ttu-id="32acd-129">형식 이름이 충돌할 경우 Tlbexp.exe에서 데코레이팅된 형식 이름을 내보내도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-129">Forces Tlbexp.exe to export decorated type names if there is a type name conflict.</span></span> <span data-ttu-id="32acd-130">.NET Framework 2.0 이전 버전에서는 이 옵션이 기본 동작이었습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-130">Note that this was the default behavior in versions prior to the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="32acd-131">**/out:** *file*</span><span class="sxs-lookup"><span data-stu-id="32acd-131">**/out:** *file*</span></span>|<span data-ttu-id="32acd-132">생성할 형식 라이브러리 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-132">Specifies the name of the type library file to generate.</span></span> <span data-ttu-id="32acd-133">이 옵션을 지정하지 않으면 해당 어셈블리와 동일한 이름(실제 어셈블리 이름으로서 해당 어셈블리가 들어 있는 파일 이름과 동일하지 않을 수도 있음) 및 .tlb 확장명을 가지는 형식 라이브러리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-133">If you omit this option, Tlbexp.exe generates a type library with the same name as the assembly (the actual assembly name, which might not necessarily be the same as the file containing the assembly) and a .tlb extension.</span></span>|  
|<span data-ttu-id="32acd-134">**/silence:** `warningnumber`</span><span class="sxs-lookup"><span data-stu-id="32acd-134">**/silence:** `warningnumber`</span></span>|<span data-ttu-id="32acd-135">지정한 경고를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-135">Suppresses the display of the specified warning.</span></span> <span data-ttu-id="32acd-136">이 옵션은 **/silent**와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-136">This option cannot be used with **/silent**.</span></span>|  
|<span data-ttu-id="32acd-137">**/silent**</span><span class="sxs-lookup"><span data-stu-id="32acd-137">**/silent**</span></span>|<span data-ttu-id="32acd-138">성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-138">Suppresses the display of success messages.</span></span> <span data-ttu-id="32acd-139">이 옵션은 **/silence**와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-139">This option cannot be used with **/silence**.</span></span>|  
|<span data-ttu-id="32acd-140">**/tlbreference:** *typelibraryname*</span><span class="sxs-lookup"><span data-stu-id="32acd-140">**/tlbreference:** *typelibraryname*</span></span>|<span data-ttu-id="32acd-141">Tlbexp.exe에서 레지스트리를 조회하지 않고 형식 라이브러리 참조를 명시적으로 확인하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-141">Forces Tlbexp.exe to explicitly resolve type library references without consulting the registry.</span></span> <span data-ttu-id="32acd-142">예를 들어, 어셈블리 B가 어셈블리 A를 참조하는 경우, 레지스트리에 지정된 형식 라이브러리에 의존하지 않고 이 옵션을 사용하여 명시적 형식 라이브러리 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-142">For example, if assembly B references assembly A, you can use this option to provide an explicit type library reference, rather than relying on the type library specified in the registry.</span></span> <span data-ttu-id="32acd-143">Tlbexp.exe에서는 버전을 검사하여 형식 라이브러리 버전이 어셈블리 버전과 일치하는지 확인합니다. 일치하지 않으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-143">Tlbexp.exe performs a version check to ensure that the type library version matches the assembly version; otherwise, it generates an error.</span></span><br /><br /> <span data-ttu-id="32acd-144">**tlbreference** 옵션은 다른 형식으로 구현되는 인터페이스에 <xref:System.Runtime.InteropServices.ComImportAttribute> 특성이 적용되는 경우에도 레지스트리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-144">Note that the **tlbreference** option still consults the registry in cases where the <xref:System.Runtime.InteropServices.ComImportAttribute> attribute is applied to an interface that is then implemented by another type.</span></span>|  
|<span data-ttu-id="32acd-145">**/tlbrefpath:** *path*</span><span class="sxs-lookup"><span data-stu-id="32acd-145">**/tlbrefpath:** *path*</span></span>|<span data-ttu-id="32acd-146">참조되는 형식 라이브러리에 대한 정규화된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-146">Fully qualified path to a referenced type library.</span></span>|  
|<span data-ttu-id="32acd-147">**/win32**</span><span class="sxs-lookup"><span data-stu-id="32acd-147">**/win32**</span></span>|<span data-ttu-id="32acd-148">이 옵션은 64비트 컴퓨터에서 컴파일할 때 Tlbexp.exe가 32비트 형식 라이브러리를 생성하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-148">When compiling on a 64-bit computer, this option specifies that Tlbexp.exe generates a 32-bit type library.</span></span>|  
|<span data-ttu-id="32acd-149">**/win64**</span><span class="sxs-lookup"><span data-stu-id="32acd-149">**/win64**</span></span>|<span data-ttu-id="32acd-150">이 옵션은 32비트 컴퓨터에서 컴파일할 때 Tlbexp.exe가 64비트 형식 라이브러리를 생성하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-150">When compiling on a 32-bit computer, this option specifies that Tlbexp.exe generates a 64-bit type library.</span></span>|  
|<span data-ttu-id="32acd-151">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="32acd-151">**/verbose**</span></span>|<span data-ttu-id="32acd-152">세부 정보 표시 모드를 지정합니다. 즉, 형식 라이브러리가 생성되어야 하는 참조되는 어셈블리의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-152">Specifies verbose mode; displays a list of any referenced assemblies for which a type library needs to be generated.</span></span>|  
|<span data-ttu-id="32acd-153">**/?**</span><span class="sxs-lookup"><span data-stu-id="32acd-153">**/?**</span></span>|<span data-ttu-id="32acd-154">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-154">Displays command syntax and options for the tool.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="32acd-155">Tlbexp.exe의 명령줄 옵션은 대/소문자를 구분하지 않으며 순서에 관계없이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-155">The command-line options for Tlbexp.exe are case-insensitive and can be supplied in any order.</span></span> <span data-ttu-id="32acd-156">또한, 고유하게 식별할 수 있을 정도로만 옵션을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-156">You only need to specify enough of the option to uniquely identify it.</span></span> <span data-ttu-id="32acd-157">예를 들어 **/n**은 **/nologo**와 같고, **/o:** *outfile.tlb*는 **/out:** *outfile.tlb*와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-157">For example, **/n** is equivalent to **/nologo**, and **/o:** *outfile.tlb* is equivalent to **/out:** *outfile.tlb*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32acd-158">설명</span><span class="sxs-lookup"><span data-stu-id="32acd-158">Remarks</span></span>  
 <span data-ttu-id="32acd-159">Tlbexp.exe를 사용하여 어셈블리에 정의된 형식에 대한 정의가 들어 있는 형식 라이브러리를 생성할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="32acd-159">Tlbexp.exe generates a type library that contains definitions of the types defined in the assembly.</span></span> <span data-ttu-id="32acd-160">Visual Basic 6.0과 같은 응용 프로그램에서는 이렇게 생성된 형식 라이브러리를 사용하여 어셈블리에 정의된 .NET 형식에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-160">Applications such as Visual Basic 6.0 can use the generated type library to bind to the .NET types defined in the assembly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="32acd-161">Tlbexp.exe를 사용하여 Windows 메타데이터(.winmd) 파일을 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-161">You cannot use Tlbexp.exe to export Windows metadata (.winmd) files.</span></span> <span data-ttu-id="32acd-162">Windows 런타임 어셈블리 내보내기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-162">Exporting Windows Runtime assemblies is not supported.</span></span>  
  
 <span data-ttu-id="32acd-163">어셈블리는 전체가 한 번에 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-163">The entire assembly is converted at once.</span></span> <span data-ttu-id="32acd-164">Tlbexp.exe를 사용하여 어셈블리에 정의된 형식의 하위 집합에 대한 형식 정보를 생성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-164">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>  
  
 <span data-ttu-id="32acd-165">또한 [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)를 사용하여 가져온 어셈블리에서 형식 라이브러리를 생성할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-165">You cannot use Tlbexp.exe to produce a type library from an assembly that was imported using the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="32acd-166">대신 Tlbimp.exe를 사용하여 가져온 원본 형식 라이브러리를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-166">Instead, you should refer to the original type library that was imported with Tlbimp.exe.</span></span> <span data-ttu-id="32acd-167">Tlbimp.exe를 사용하여 가져온 어셈블리를 참조하는 어셈블리에서 형식 라이브러리를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-167">You can export a type library from an assembly that references assemblies that were imported using Tlbimp.exe.</span></span> <span data-ttu-id="32acd-168">아래의 예제 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32acd-168">See the examples section below.</span></span>  
  
 <span data-ttu-id="32acd-169">Tlbexp.exe를 사용하면 생성된 형식 라이브러리는 현재 작업 디렉터리 또는 출력 파일에 대해 지정된 디렉터리에 놓이며,</span><span class="sxs-lookup"><span data-stu-id="32acd-169">Tlbexp.exe places generated type libraries in the current working directory or the directory specified for the output file.</span></span> <span data-ttu-id="32acd-170">하나의 어셈블리에서 여러 개의 형식 라이브러리가 생성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-170">A single assembly might cause several type libraries to be generated.</span></span>  
  
 <span data-ttu-id="32acd-171">Tlbexp.exe를 사용하면 형식 라이브러리는 생성되지만 등록되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-171">Tlbexp.exe generates a type library but does not register it.</span></span> <span data-ttu-id="32acd-172">즉, 형식 라이브러리의 생성 및 등록을 모두 수행하는 [어셈블리 등록 도구(Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)와는 정반대입니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-172">This is in contrast to the [Assembly Registration tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md), which both generates and registers a type library.</span></span> <span data-ttu-id="32acd-173">따라서 COM을 사용하여 형식 라이브러리를 생성 및 등록하려면 Regasm.exe를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="32acd-173">To generate and register a type library with COM, use Regasm.exe.</span></span>  
  
 <span data-ttu-id="32acd-174">`/win32` 또는 `/win64` 옵션을 지정하지 않으면 Tlbexp.exe는 컴파일을 수행할 컴퓨터(32비트 또는 64비트 컴퓨터)의 형식에 해당하는 32비트 또는 64비트 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-174">If you do not specify either the `/win32` or `/win64` option, Tlbexp.exe generates a 32-bit or 64-bit type library that corresponds to the type of computer on which you are performing the compilation (32-bit or 64-bit computer).</span></span> <span data-ttu-id="32acd-175">크로스 컴파일의 경우 32비트 컴퓨터에서 `/win64` 옵션을 사용하여 64비트 형식 라이브러리를 생성하거나 64비트 컴퓨터에서 `/win32` 옵션을 사용하여 32비트 형식 라이브러리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-175">For cross-compilation purposes, you can use the `/win64` option on a 32-bit computer to generate a 64-bit type library and you can use the `/win32` option on a 64-bit computer to generate a 32-bit type library.</span></span> <span data-ttu-id="32acd-176">32비트 형식 라이브러리에서 <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> 값은 <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN32>로 설정되고</span><span class="sxs-lookup"><span data-stu-id="32acd-176">In 32-bit type libraries, the <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> value is set to <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN32>.</span></span> <span data-ttu-id="32acd-177">64비트 형식 라이브러리에서 <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> 값은 <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN64>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-177">In 64-bit type libraries, the <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> value is set to <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN64>.</span></span> <span data-ttu-id="32acd-178">모든 데이터 형식 변환(예: `IntPtr` 및 `UIntPtr` 같은 포인터 크기의 데이터 형식)이 적절하게 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-178">All data type transformations (for example, pointer-sized data types such as `IntPtr` and `UIntPtr`) are converted appropriately.</span></span>  
  
 <span data-ttu-id="32acd-179"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType> 또는 `VT_UNKOWN`의 `VT_DISPATCH` 값을 지정하면 Tlbexp.exe에서는 이후에 사용하는 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> 필드를 모두 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-179">If you use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify a <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType> value of `VT_UNKOWN` or `VT_DISPATCH`, Tlbexp.exe ignores any subsequent use of the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> field.</span></span> <span data-ttu-id="32acd-180">예를 들어, 다음과 같은 서명을 지정할 경우</span><span class="sxs-lookup"><span data-stu-id="32acd-180">For example, given the following signatures:</span></span>  
  
```  
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_UNKNOWN, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructUnkSafe(){return null;}  
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_DISPATCH, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructDispSafe(){return null;}  
```  
  
 <span data-ttu-id="32acd-181">다음 형식 라이브러리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-181">the following type library is generated:</span></span>  
  
```  
[id(0x60020004)]  
HRESULT StructUnkSafe([out, retval] SAFEARRAY(IUnknown*)* pRetVal);  
[id(0x60020005)]  
HRESULT StructDispSafe([out, retval] SAFEARRAY(IDispatch*)* pRetVal);  
```  
  
 <span data-ttu-id="32acd-182">Tlbexp.exe에서는 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> 필드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-182">Note that Tlbexp.exe ignores the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> field.</span></span>  
  
 <span data-ttu-id="32acd-183">형식 라이브러리가 어셈블리의 모든 정보를 포함할 수 없으므로 변환 프로세스를 통해 내보내는 동안 일부 데이터가 삭제될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-183">Because type libraries cannot accommodate all the information found in assemblies, Tlbexp.exe might discard some data during the export process.</span></span> <span data-ttu-id="32acd-184">변형 프로세스 설명 및 형식 라이브러리에 내보낸 정보에 대한 소스 식별에 대한 자세한 내용은 [어셈블리와 형식 라이브러리 간 변환 요약](http://msdn.microsoft.com/library/3a37eefb-a76c-4000-9080-7dbbf66a4896)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32acd-184">For an explanation of the transformation process and identification of the source of each piece of information emitted to a type library, see the [Assembly to Type Library Conversion Summary](http://msdn.microsoft.com/library/3a37eefb-a76c-4000-9080-7dbbf66a4896).</span></span>  
  
 <span data-ttu-id="32acd-185">형식 라이브러리 내보내기는 <xref:System.TypedReference> 개체가 비관리 코드에서 의미가 없더라도 `VARIANT` 매개 변수가 <xref:System.TypedReference>인 메서드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-185">Note that the Type Library Exporter exports methods that have <xref:System.TypedReference> parameters as `VARIANT`, even though the <xref:System.TypedReference> object has no meaning in unmanaged code.</span></span> <span data-ttu-id="32acd-186"><xref:System.TypedReference> 매개 변수가 있는 메서드를 내보내면 형식 라이브러리 내보내기가 경고나 오류를 생성하지 않으며 결과 형식 라이브러리를 사용하는 비관리 코드가 제대로 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-186">When you export methods that have <xref:System.TypedReference> parameters, the Type Library Exporter will not generate a warning or error and unmanaged code that uses the resulting type library will not run properly.</span></span>  
  
 <span data-ttu-id="32acd-187">형식 라이브러리 내보내기는 Microsoft Windows 2000 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-187">The Type Library Exporter is supported on Microsoft Windows 2000 and later.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="32acd-188">예제</span><span class="sxs-lookup"><span data-stu-id="32acd-188">Examples</span></span>  
 <span data-ttu-id="32acd-189">다음 명령을 사용하여 `myTest.dll`에 있는 어셈블리와 동일한 이름의 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-189">The following command generates a type library with the same name as the assembly found in `myTest.dll`.</span></span>  
  
```  
tlbexp myTest.dll  
```  
  
 <span data-ttu-id="32acd-190">다음 명령을 사용하여 `clipper.tlb`라는 이름의 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-190">The following command generates a type library with the name `clipper.tlb`.</span></span>  
  
```  
tlbexp myTest.dll /out:clipper.tlb  
```  
  
 <span data-ttu-id="32acd-191">다음 예제에서는 Tlbimp.exe를 사용하여 가져온 어셈블리를 참조하는 어셈블리에서 Tlbexp.exe를 사용하여 형식 라이브러리를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-191">The following example illustrates using Tlbexp.exe to export a type library from an assembly that references assemblies that were imported using Tlbimp.exe.</span></span>  
  
 <span data-ttu-id="32acd-192">먼저, Tlbimp.exe를 사용하여 형식 라이브러리 `myLib.tlb`를 가져온 다음 이를 `myLib.dll`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-192">First use Tlbimp.exe to import the type library `myLib.tlb` and save it as `myLib.dll`.</span></span>  
  
```  
tlbimp myLib.tlb /out:myLib.dll  
```  
  
 <span data-ttu-id="32acd-193">다음 명령을 사용하여 앞의 예제에서 생성된 `Sample.dll,`을 참조하는 `myLib.dll`을 C# 컴파일러로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-193">The following command uses the C# compiler to compile the `Sample.dll,` which references `myLib.dll` created in the previous example.</span></span>  
  
```  
CSC Sample.cs /reference:myLib.dll /out:Sample.dll  
```  
  
 <span data-ttu-id="32acd-194">다음 명령을 사용하여 `Sample.dll`을 참조하는 `myLib.dll`에 대한 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="32acd-194">The following command generates a type library for `Sample.dll` that references `myLib.dll`.</span></span>  
  
```  
tlbexp Sample.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="32acd-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32acd-195">See Also</span></span>  
 <xref:System.Runtime.InteropServices.TypeLibExporterFlags>  
 [<span data-ttu-id="32acd-196">도구</span><span class="sxs-lookup"><span data-stu-id="32acd-196">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="32acd-197">Regasm.exe(어셈블리 등록 도구)</span><span class="sxs-lookup"><span data-stu-id="32acd-197">Regasm.exe (Assembly Registration Tool)</span></span>](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 [<span data-ttu-id="32acd-198">어셈블리와 형식 라이브러리 간 변환 요약</span><span class="sxs-lookup"><span data-stu-id="32acd-198">Assembly to Type Library Conversion Summary</span></span>](http://msdn.microsoft.com/library/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 [<span data-ttu-id="32acd-199">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="32acd-199">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="32acd-200">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="32acd-200">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
