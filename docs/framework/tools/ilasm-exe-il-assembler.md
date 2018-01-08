---
title: "Ilasm.exe(IL 어셈블러)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
caps.latest.revision: "41"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2507acc7ddf41d921af0b86622b1e85208191767
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="edd23-102">Ilasm.exe(IL 어셈블러)</span><span class="sxs-lookup"><span data-stu-id="edd23-102">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="edd23-103">IL 어셈블러는 IL(Intermediate Language)로 PE(이식 가능한 실행) 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-103">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="edd23-104">IL에 대한 자세한 내용은 [관리되는 실행 프로세스](../../../docs/standard/managed-execution-process.md)를 참조하세요. 이렇게 생성된 실행 파일에는 IL 및 필요한 메타데이터가 들어 있으며, 이 파일을 실행하면 IL이 예상대로 실행되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-104">(For more information on IL, see [Managed Execution Process](../../../docs/standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="edd23-105">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="edd23-106">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-106">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="edd23-107">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="edd23-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="edd23-108">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="edd23-109">구문</span><span class="sxs-lookup"><span data-stu-id="edd23-109">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

#### <a name="parameters"></a><span data-ttu-id="edd23-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="edd23-110">Parameters</span></span>

| <span data-ttu-id="edd23-111">인수</span><span class="sxs-lookup"><span data-stu-id="edd23-111">Argument</span></span> | <span data-ttu-id="edd23-112">설명</span><span class="sxs-lookup"><span data-stu-id="edd23-112">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="edd23-113">.il 소스 파일의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-113">The name of the .il source file.</span></span> <span data-ttu-id="edd23-114">이 파일은 메타데이터 선언 지시문과 기호화된 IL 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-114">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="edd23-115">*Ilasm.exe*를 사용하여 여러 개의 소스 파일 인수를 제공하면 하나의 PE 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-115">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="edd23-116">**참고:** .il 소스 파일의 마지막 코드 줄에는 후행 공백이나 줄 끝(EOL) 문자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-116">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="edd23-117">옵션</span><span class="sxs-lookup"><span data-stu-id="edd23-117">Option</span></span> | <span data-ttu-id="edd23-118">설명</span><span class="sxs-lookup"><span data-stu-id="edd23-118">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="edd23-119">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="edd23-119">**/32bitpreferred**</span></span>|<span data-ttu-id="edd23-120">32비트 우선의 이미지(PE32)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-120">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="edd23-121">**/alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="edd23-121">**/alignment:** `integer`</span></span>|<span data-ttu-id="edd23-122">FileAlignment를 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-122">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="edd23-123">.alignment IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-123">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="edd23-124">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="edd23-124">**/appcontainer**</span></span>|<span data-ttu-id="edd23-125">Windows 앱 컨테이너에서 출력으로 실행되는 *.dll* 또는 *.exe* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-125">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="edd23-126">**/arm**</span><span class="sxs-lookup"><span data-stu-id="edd23-126">**/arm**</span></span>|<span data-ttu-id="edd23-127">Advanced RISC Machine(ARM)을 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-127">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="edd23-128">이미지 비트가 지정되지 않은 경우 기본값은 **/32bitpreferred**입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-128">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="edd23-129">**/base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="edd23-129">**/base:** `integer`</span></span>|<span data-ttu-id="edd23-130">ImageBase를 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-130">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="edd23-131">.imagebase IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-131">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="edd23-132">**/clock**</span><span class="sxs-lookup"><span data-stu-id="edd23-132">**/clock**</span></span>|<span data-ttu-id="edd23-133">지정된 .il 소스 파일에 대해 다음 컴파일 타임을 밀리초 단위로 측정하여 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-133">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="edd23-134">**Total Run**: 다음의 특정 작업을 모두 수행하는 데 걸린 총 시간</span><span class="sxs-lookup"><span data-stu-id="edd23-134">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="edd23-135">**Startup**: 파일 로드 및 열기</span><span class="sxs-lookup"><span data-stu-id="edd23-135">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="edd23-136">**Emitting MD**: 메타데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="edd23-136">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="edd23-137">**Ref to Def Resolution**: 파일의 참조를 정의로 확인</span><span class="sxs-lookup"><span data-stu-id="edd23-137">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="edd23-138">**CEE File Generation**: 메모리에 파일 이미지 생성</span><span class="sxs-lookup"><span data-stu-id="edd23-138">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="edd23-139">**PE File Writing**: PE 파일에 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="edd23-139">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="edd23-140">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="edd23-140">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="edd23-141">지역 변수 및 인수 이름과 줄 번호 등의 디버깅 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-141">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="edd23-142">PDB 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-142">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="edd23-143">**/debug** 에 추가 값을 지정하지 않으면 JIT 최적화를 사용할 수 없고 PDB 파일의 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-143">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="edd23-144">**IMPL** 은 JIT 최적화를 사용할 수 없도록 하고 암시적 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-144">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="edd23-145">**OPT** 는 JIT 최적화를 사용할 수 있도록 하고 암시적 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-145">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="edd23-146">**/dll**</span><span class="sxs-lookup"><span data-stu-id="edd23-146">**/dll**</span></span>|<span data-ttu-id="edd23-147">*.dll* 파일을 출력 파일로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-147">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="edd23-148">**/enc:** `file`</span><span class="sxs-lookup"><span data-stu-id="edd23-148">**/enc:** `file`</span></span>|<span data-ttu-id="edd23-149">지정한 소스 파일에서 편집하며 계속하기 델타를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-149">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="edd23-150">이 인수는 교육용 버전에서만 사용되며, 상업용 버전에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-150">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="edd23-151">**/exe**</span><span class="sxs-lookup"><span data-stu-id="edd23-151">**/exe**</span></span>|<span data-ttu-id="edd23-152">실행 파일을 출력 파일로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-152">Produces an executable file as output.</span></span> <span data-ttu-id="edd23-153">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-153">This is the default.</span></span>|
|<span data-ttu-id="edd23-154">**/flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="edd23-154">**/flags:** `integer`</span></span>|<span data-ttu-id="edd23-155">ImageFlags를 공용 언어 런타임 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-155">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="edd23-156">.corflags IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-156">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="edd23-157">*integer*의 올바른 값 목록은 CorHdr.h, COMIMAGE_FLAGS를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edd23-157">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="edd23-158">**/fold**</span><span class="sxs-lookup"><span data-stu-id="edd23-158">**/fold**</span></span>|<span data-ttu-id="edd23-159">동일한 메서드 본문을 하나로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-159">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="edd23-160">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="edd23-160">/**highentropyva**</span></span>|<span data-ttu-id="edd23-161">높은 엔트로피 주소 공간 레이아웃 불규칙화(ASLR)가 지원되는 출력 실행 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-161">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="edd23-162">( **/appcontainer**의 기본값)</span><span class="sxs-lookup"><span data-stu-id="edd23-162">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="edd23-163">**/include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="edd23-163">**/include:** `includePath`</span></span>|<span data-ttu-id="edd23-164">`#include`에 포함된 파일을 검색할 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-164">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="edd23-165">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="edd23-165">**/itanium**</span></span>|<span data-ttu-id="edd23-166">Intel Itanium을 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-166">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="edd23-167">이미지 비트가 지정되지 않은 경우 기본값은 **/pe64**입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-167">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="edd23-168">**/key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="edd23-168">**/key:** `keyFile`</span></span>|<span data-ttu-id="edd23-169">`keyFile`에 들어 있는 개인 키를 사용하여 강력한 시그니처가 있는 `filename`을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-169">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="edd23-170">**/key:** @`keySource`</span><span class="sxs-lookup"><span data-stu-id="edd23-170">**/key:** @`keySource`</span></span>|<span data-ttu-id="edd23-171">`keySource`에 생성된 개인 키를 사용하여 강력한 시그니처가 있는 `filename`을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-171">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="edd23-172">**/listing**</span><span class="sxs-lookup"><span data-stu-id="edd23-172">**/listing**</span></span>|<span data-ttu-id="edd23-173">표준 출력 파일에 대한 목록 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-173">Produces a listing file on the standard output.</span></span> <span data-ttu-id="edd23-174">이 옵션을 생략하면 목록 파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-174">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="edd23-175">이 매개 변수는 .NET Framework 2.0 이상에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-175">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="edd23-176">**/mdv:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="edd23-176">**/mdv:** `versionString`</span></span>|<span data-ttu-id="edd23-177">메타데이터 버전 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-177">Sets the metadata version string.</span></span>|
|<span data-ttu-id="edd23-178">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="edd23-178">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="edd23-179">`major` 및 `minor` 가 정수인 메타데이터 스트림 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-179">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="edd23-180">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="edd23-180">**/noautoinherit**</span></span>|<span data-ttu-id="edd23-181">기준 클래스를 지정하지 않으면 <xref:System.Object> 에서 기본 상속을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-181">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="edd23-182">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="edd23-182">**/nocorstub**</span></span>|<span data-ttu-id="edd23-183">CORExeMain 스텁을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-183">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="edd23-184">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="edd23-184">**/nologo**</span></span>|<span data-ttu-id="edd23-185">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-185">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="edd23-186">**/output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="edd23-186">**/output:** `file.ext`</span></span>|<span data-ttu-id="edd23-187">출력 파일 이름 및 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-187">Specifies the output file name and extension.</span></span> <span data-ttu-id="edd23-188">기본적으로 출력 파일 이름은 첫 번째 소스 파일의 이름과 같으며,</span><span class="sxs-lookup"><span data-stu-id="edd23-188">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="edd23-189">기본 확장명은 *.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-189">The default extension is *.exe*.</span></span> <span data-ttu-id="edd23-190">**/dll** 옵션을 지정하는 경우 기본 확장명은 *.dll*입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-190">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="edd23-191">**참고:** **/output**:myfile.dll을 지정하면 **/dll** 옵션이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-191">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="edd23-192">**/dll**을 지정하지 않으면 *myfile.dll*이라는 실행 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-192">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="edd23-193">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="edd23-193">**/optimize**</span></span>|<span data-ttu-id="edd23-194">긴 명령을 짧게 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-194">Optimizes long instructions to short.</span></span> <span data-ttu-id="edd23-195">예를 들면, `br` 를 `br.s`로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-195">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="edd23-196">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="edd23-196">**/pe64**</span></span>|<span data-ttu-id="edd23-197">64비트 이미지(PE32+)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-197">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="edd23-198">대상 프로세서가 지정되지 않은 경우 기본값은 `/itanium`입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-198">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="edd23-199">**/pdb**</span><span class="sxs-lookup"><span data-stu-id="edd23-199">**/pdb**</span></span>|<span data-ttu-id="edd23-200">디버그 정보 추적을 사용하지 않고 PDB 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-200">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="edd23-201">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="edd23-201">**/quiet**</span></span>|<span data-ttu-id="edd23-202">자동 모드를 지정하여 어셈블리 진행률을 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-202">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="edd23-203">**/resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="edd23-203">**/resource:** `file.res`</span></span>|<span data-ttu-id="edd23-204">결과로 만들어지는 *.exe* 또는 *.dll* 파일에 \*.res 형식의 지정된 리소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-204">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="edd23-205">**/resource** 옵션을 사용하여 .res 파일을 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-205">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="edd23-206">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="edd23-206">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="edd23-207">NT 선택적 헤더의 하위 시스템 버전 번호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-207">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="edd23-208">**/appcontainer** 및 **/arm** 의 최소 버전 번호는 6.02입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-208">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="edd23-209">**/stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="edd23-209">**/stack:** `stackSize`</span></span>|<span data-ttu-id="edd23-210">NT 선택적 헤더의 SizeOfStackReserve 값을 `stackSize`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-210">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="edd23-211">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="edd23-211">**/stripreloc**</span></span>|<span data-ttu-id="edd23-212">기준 재배치가 필요하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-212">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="edd23-213">**/subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="edd23-213">**/subsystem:** `integer`</span></span>|<span data-ttu-id="edd23-214">하위 시스템을 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-214">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="edd23-215">.subsystem IL 지시문이 파일에 지정된 경우 이 명령을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-215">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="edd23-216">`integer`의 올바른 값 목록은 winnt.h, IMAGE_SUBSYSTEM을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="edd23-216">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="edd23-217">**/x64**</span><span class="sxs-lookup"><span data-stu-id="edd23-217">**/x64**</span></span>|<span data-ttu-id="edd23-218">64비트 AMD 프로세서를 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-218">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="edd23-219">이미지 비트가 지정되지 않은 경우 기본값은 **/pe64**입니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-219">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="edd23-220">**/?**</span><span class="sxs-lookup"><span data-stu-id="edd23-220">**/?**</span></span>|<span data-ttu-id="edd23-221">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-221">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="edd23-222">*Ilasm.exe*의 모든 옵션은 대/소문자가 구분되지 않으며 처음 세 문자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-222">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="edd23-223">예를 들어 **/lis**는 **/listing**과 같고, **/res:**myresfile.res는 **/resource:**myresfile.res와 같습니다. 인수를 지정하는 옵션에는 옵션과 인수 사이의 구분 기호로 콜론(:) 또는 등호(=) 중 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-223">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="edd23-224">예를 들어, **/output**:*file.ext*는 **/output**=*file.ext*와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-224">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="edd23-225">설명</span><span class="sxs-lookup"><span data-stu-id="edd23-225">Remarks</span></span>

<span data-ttu-id="edd23-226">IL 어셈블러를 사용하면 도구 공급업체는 IL 생성기를 쉽게 디자인하여 구현할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="edd23-226">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="edd23-227">*Ilasm.exe*를 사용하면 도구 및 컴파일러 개발자는 IL을 PE 파일 형식으로 내보내는 것에 신경 쓰지 않고 IL 및 메타데이터 생성에만 몰두할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-227">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="edd23-228">*Ilasm.exe*를 사용하면 C# 및 Visual Basic과 같이 런타임을 대상으로 하는 다른 컴파일러처럼 중간 개체 파일이 생성되지 않으며 PE 파일을 만들 때 링크하는 단계가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-228">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="edd23-229">IL 어셈블러를 사용하면 런타임을 대상으로 하는 프로그래밍 언어의 IL 기능 및 기존 메타데이터를 모두 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-229">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="edd23-230">이렇게 하면 이러한 프로그래밍 언어로 작성된 관리 코드를 IL 어셈블러에서 적절히 표현하고 *Ilasm.exe*를 사용하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-230">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="edd23-231">.il 소스 파일의 마지막 코드 줄에 후행 공백이나 줄 끝(EOL) 문자가 없으면 컴파일이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-231">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="edd23-232">*Ilasm.exe*는 자매 도구인 [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-232">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="edd23-233">*Ildasm.exe*는 IL 코드가 포함된 PE 파일을 가져와서 *Ildasm.exe*에 입력하기에 적합한 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-233">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="edd23-234">이렇게 하면 런타임 메타데이터 특성을 모두 지원하지 않는 프로그래밍 언어로 코드를 컴파일할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-234">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="edd23-235">코드를 컴파일하고 *Ildasm.exe*를 사용하여 출력을 실행한 후에는 결과로 만들어지는 IL 텍스트 파일을 수동으로 편집하여 손실된 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-235">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="edd23-236">그런 다음에는 *Ilasm.exe*를 통해 이 텍스트 파일을 실행하여 최종 실행 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-236">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="edd23-237">또한, 이 기술을 사용하면 서로 다른 컴파일러에서 생성된 여러 개의 PE 파일에서 하나의 PE 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-237">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="edd23-238">포함된 네이티브 코드가 들어 있는 PE 파일(예: Visual C++로 생성된 PE 파일)에는 현재 이 방법을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-238">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="edd23-239">가능한 정확하게 *Ildasm.exe* 및 *Ilasm.exe*를 복합적으로 사용하려면, 디폴트로 어셈블러가 IL 소스에서 기록한 (혹은 다른 컴파일러에 의하여 빠뜨려진) 긴 인코딩에 대한 짧은 인코딩을 대체하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-239">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="edd23-240">**/optimize** 옵션을 사용하여 가능한 짧은 인코딩으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-240">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="edd23-241">*Ildasm.exe*는 디스크의 파일에 대해서만 작동하며,</span><span class="sxs-lookup"><span data-stu-id="edd23-241">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="edd23-242">전역 어셈블리 캐시에 설치된 파일에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-242">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="edd23-243">IL 문법에 대한 자세한 내용은 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 asmparse.grammar 파일을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edd23-243">For more information about the grammar of IL, see the asmparse.grammar file in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>

## <a name="version-information"></a><span data-ttu-id="edd23-244">버전 정보</span><span class="sxs-lookup"><span data-stu-id="edd23-244">Version Information</span></span>

<span data-ttu-id="edd23-245">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 다음과 같은 코드를 사용하여 사용자 지정 특성을 인터페이스 구현에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-245">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="edd23-246">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 다음 코드와 같이 원시 이진 표현을 사용하여 임의의 마샬 BLOB(이진 대형 개체)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-246">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="edd23-247">IL 문법에 대한 자세한 내용은 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 asmparse.grammar 파일을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edd23-247">For more information about the grammar of IL, see the asmparse.grammar file in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>

## <a name="examples"></a><span data-ttu-id="edd23-248">예제</span><span class="sxs-lookup"><span data-stu-id="edd23-248">Examples</span></span>

<span data-ttu-id="edd23-249">다음 명령은 IL 파일 *myTestFile.il*을 어셈블하고 실행 파일 *myTestFile.exe*를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-249">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="edd23-250">다음 명령은 IL 파일 *myTestFile.il*을 어셈블하고 *.dll* 파일 *myTestFile.dll*을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-250">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="edd23-251">다음 명령은 IL 파일 *myTestFile.il*을 어셈블하고 *.dll* 파일 *myNewTestFile.dll*을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="edd23-252">다음 코드 예제에서는 "Hello World!"를 콘솔에 표시하는 매우 간단한 응용 프로그램을</span><span class="sxs-lookup"><span data-stu-id="edd23-252">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="edd23-253">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-253">to the console.</span></span> <span data-ttu-id="edd23-254">이 코드를 컴파일한 다음 [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 도구를 사용하여 IL 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-254">You can compile this code and then use the [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="edd23-255">다음 IL 코드 예제는 이전 C# 코드 예제에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-255">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="edd23-256">IL 어셈블러 도구를 사용하여 이 코드를 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-256">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="edd23-257">IL과 C# 코드 예제 모두 콘솔에 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="edd23-257">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="edd23-258">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="edd23-258">to the console.</span></span>

```
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="edd23-259">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edd23-259">See also</span></span>

[<span data-ttu-id="edd23-260">도구</span><span class="sxs-lookup"><span data-stu-id="edd23-260">Tools</span></span>](../../../docs/framework/tools/index.md)  
<span data-ttu-id="edd23-261">[*Ildasm.exe* (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)(Ildasm.exe(IL 디스어셈블러))</span><span class="sxs-lookup"><span data-stu-id="edd23-261">[*Ildasm.exe* (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)</span></span>  
[<span data-ttu-id="edd23-262">관리되는 실행 프로세스</span><span class="sxs-lookup"><span data-stu-id="edd23-262">Managed Execution Process</span></span>](../../../docs/standard/managed-execution-process.md)  
[<span data-ttu-id="edd23-263">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="edd23-263">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
