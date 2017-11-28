---
title: "SecAnnotate.exe(.NET Security Annotator 도구)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7051e753c324933828e2447752f9c5ea13ed9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="secannotateexe-net-security-annotator-tool"></a><span data-ttu-id="013ca-102">SecAnnotate.exe(.NET Security Annotator 도구)</span><span class="sxs-lookup"><span data-stu-id="013ca-102">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>
<span data-ttu-id="013ca-103">.NET Security Annotator 도구(SecAnnotate.exe)는 하나 이상의 어셈블리의 `SecurityCritical` 및 `SecuritySafeCritical` 부분을 식별하는 명령줄 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-103">The .NET Security Annotator tool (SecAnnotate.exe) is a command-line application that identifies the `SecurityCritical` and `SecuritySafeCritical` portions of one or more assemblies.</span></span>  
  
 <span data-ttu-id="013ca-104">Visual Studio 확장인 [Security Annotator](http://go.microsoft.com/fwlink/?LinkId=198007)는 SecAnnotate.exe에 대한 그래픽 사용자 인터페이스를 제공하며 Visual Studio에서 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-104">A Visual Studio extension, [Security Annotator](http://go.microsoft.com/fwlink/?LinkId=198007), provides a graphical user interface to SecAnnotate.exe and enables you to run the tool from Visual Studio.</span></span>  
  
 <span data-ttu-id="013ca-105">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="013ca-106">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-106">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="013ca-107">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013ca-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="013ca-108">명령 프롬프트에서 다음을 입력하세요. *parameters*는 다음 섹션에서 설명하며 *assemblies*는 공백으로 구분된 하나 이상의 어셈블리 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-108">At the command prompt, type the following, where *parameters* are described in the following section, and *assemblies* consist of one or more assembly names separated by blanks:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013ca-109">구문</span><span class="sxs-lookup"><span data-stu-id="013ca-109">Syntax</span></span>  
  
```  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="013ca-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="013ca-110">Parameters</span></span>  
  
|<span data-ttu-id="013ca-111">옵션</span><span class="sxs-lookup"><span data-stu-id="013ca-111">Option</span></span>|<span data-ttu-id="013ca-112">설명</span><span class="sxs-lookup"><span data-stu-id="013ca-112">Description</span></span>|  
|------------|-----------------|  
|`/a`<br /><br /> <span data-ttu-id="013ca-113">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-113">or</span></span><br /><br /> `/showstatistics`|<span data-ttu-id="013ca-114">분석 중인 어셈블리에서 투명도 사용에 대한 통계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-114">Shows statistics about the use of transparency in assemblies that are being analyzed.</span></span>|  
|<span data-ttu-id="013ca-115">`/d:` *directory*</span><span class="sxs-lookup"><span data-stu-id="013ca-115">`/d:` *directory*</span></span><br /><br /> <span data-ttu-id="013ca-116">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-116">or</span></span><br /><br /> <span data-ttu-id="013ca-117">`/referencedir:` *directory*</span><span class="sxs-lookup"><span data-stu-id="013ca-117">`/referencedir:` *directory*</span></span>|<span data-ttu-id="013ca-118">주석 도중 종속 어셈블리를 검색할 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-118">Specifies a directory to search for dependent assemblies during annotation.</span></span>|  
|`/i`<br /><br /> <span data-ttu-id="013ca-119">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-119">or</span></span><br /><br /> `/includesignatures`|<span data-ttu-id="013ca-120">주석 보고서 파일에 확장된 시그니처 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-120">Includes extended signature information in the annotation report file.</span></span>|  
|`/n`<br /><br /> <span data-ttu-id="013ca-121">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-121">or</span></span><br /><br /> `/nogac`|<span data-ttu-id="013ca-122">전역 어셈블리 캐시에서 참조된 어셈블리를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-122">Suppresses searching for referenced assemblies in the global assembly cache.</span></span>|  
|<span data-ttu-id="013ca-123">`/o:` *output.xml*</span><span class="sxs-lookup"><span data-stu-id="013ca-123">`/o:` *output.xml*</span></span><br /><br /> <span data-ttu-id="013ca-124">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-124">or</span></span><br /><br /> <span data-ttu-id="013ca-125">`/out:` *output.xml*</span><span class="sxs-lookup"><span data-stu-id="013ca-125">`/out:` *output.xml*</span></span>|<span data-ttu-id="013ca-126">출력 주석 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-126">Specifies the output annotation file.</span></span>|  
|<span data-ttu-id="013ca-127">`/p:` *maxpasses*</span><span class="sxs-lookup"><span data-stu-id="013ca-127">`/p:` *maxpasses*</span></span><br /><br /> <span data-ttu-id="013ca-128">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-128">or</span></span><br /><br /> <span data-ttu-id="013ca-129">`/maximumpasses:` *maxpasses*</span><span class="sxs-lookup"><span data-stu-id="013ca-129">`/maximumpasses:` *maxpasses*</span></span>|<span data-ttu-id="013ca-130">새 주석의 생성을 중지하기 전에 어셈블리에 대해 수행할 주석 패스의 최대 횟수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-130">Specifies the maximum number of annotation passes to make on assemblies before stopping the generation of new annotations.</span></span>|  
|`/q`<br /><br /> <span data-ttu-id="013ca-131">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-131">or</span></span><br /><br /> `/quiet`|<span data-ttu-id="013ca-132">주석 처리기가 상태 메시지를 출력하지 않는 자동 모드를 지정합니다. 오류 정보만 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-132">Specifies quiet mode, in which the annotator does not output status messages; it outputs only error information.</span></span>|  
|<span data-ttu-id="013ca-133">`/r:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="013ca-133">`/r:` *assembly*</span></span><br /><br /> <span data-ttu-id="013ca-134">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-134">or</span></span><br /><br /> <span data-ttu-id="013ca-135">`/referenceassembly:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="013ca-135">`/referenceassembly:` *assembly*</span></span>|<span data-ttu-id="013ca-136">주석을 추가하는 동안 종속 어셈블리를 확인할 때 지정한 어셈블리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-136">Includes the specified assembly when resolving dependent assemblies during annotation.</span></span> <span data-ttu-id="013ca-137">참조 어셈블리는 참조 경로에서 발견된 어셈블리를 통해 우선 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-137">Reference assemblies are given priority over assemblies that are found in the reference path.</span></span>|  
|<span data-ttu-id="013ca-138">`/s:` *rulename*</span><span class="sxs-lookup"><span data-stu-id="013ca-138">`/s:` *rulename*</span></span><br /><br /> <span data-ttu-id="013ca-139">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-139">or</span></span><br /><br /> <span data-ttu-id="013ca-140">`/suppressrule:` *rulename*</span><span class="sxs-lookup"><span data-stu-id="013ca-140">`/suppressrule:` *rulename*</span></span>|<span data-ttu-id="013ca-141">입력 어셈블리에 지정된 투명도 규칙의 실행을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-141">Suppresses running the specified transparency rule on the input assemblies.</span></span>|  
|`/t`<br /><br /> <span data-ttu-id="013ca-142">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-142">or</span></span><br /><br /> `/forcetransparent`|<span data-ttu-id="013ca-143">Annotator 도구를 사용하면 투명 주석이 없는 모든 어셈블리를 완전히 투명한 것처럼 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-143">Forces the Annotator tool to treat all assemblies that do not have any transparency annotations as if they were entirely transparent.</span></span>|  
|<span data-ttu-id="013ca-144">`/t`:*assembly*</span><span class="sxs-lookup"><span data-stu-id="013ca-144">`/t`:*assembly*</span></span><br /><br /> <span data-ttu-id="013ca-145">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-145">or</span></span><br /><br /> <span data-ttu-id="013ca-146">`/forcetransparent`:*assembly*</span><span class="sxs-lookup"><span data-stu-id="013ca-146">`/forcetransparent`:*assembly*</span></span>|<span data-ttu-id="013ca-147">현재 어셈블리 수준 주석에 관계없이 지정된 어셈블리를 강제로 투명하게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-147">Force the given assembly to be transparent, regardless of its current assembly-level annotations.</span></span>|  
|||  
|`/v`<br /><br /> <span data-ttu-id="013ca-148">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-148">or</span></span><br /><br /> `/verify`|<span data-ttu-id="013ca-149">어셈블리의 주석이 올바른지만 확인하고, 어셈블리가 확인되지 않은 경우 여러 번의 패스를 수행하여 필요한 모든 주석을 찾는 작업은 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-149">Verifies only that an assembly's annotations are correct; does not attempt to make multiple passes to find all required annotations if the assembly does not verify.</span></span>|  
|`/x`<br /><br /> <span data-ttu-id="013ca-150">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-150">or</span></span><br /><br /> `/verbose`|<span data-ttu-id="013ca-151">주석을 추가하는 동안 자세한 출력을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-151">Specifies verbose output while annotating.</span></span>|  
|<span data-ttu-id="013ca-152">`/y:` *directory*</span><span class="sxs-lookup"><span data-stu-id="013ca-152">`/y:` *directory*</span></span><br /><br /> <span data-ttu-id="013ca-153">또는</span><span class="sxs-lookup"><span data-stu-id="013ca-153">or</span></span><br /><br /> <span data-ttu-id="013ca-154">`/symbolpath:` *directory*</span><span class="sxs-lookup"><span data-stu-id="013ca-154">`/symbolpath:` *directory*</span></span>|<span data-ttu-id="013ca-155">주석을 추가하는 동안 기호 파일을 검색할 때 지정한 디렉터리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-155">Includes the specified directory when searching for symbol files during annotation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="013ca-156">설명</span><span class="sxs-lookup"><span data-stu-id="013ca-156">Remarks</span></span>  
 <span data-ttu-id="013ca-157">매개 변수 및 어셈블리는 명령줄에 지정되고 (@) 기호에 접두사가 있는 응답 파일에 제공될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-157">Parameters and assemblies may also be provided in a response file that is specified on the command line and prefixed with an at sign (@).</span></span> <span data-ttu-id="013ca-158">응답 파일의 각 줄은 단일 매개 변수 또는 어셈블리 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="013ca-158">Each line in the response file should contain a single parameter or assembly name.</span></span>  
  
 <span data-ttu-id="013ca-159">.NET Security Annotator에 대한 자세한 내용은 .NET Security 블로그의 [SecAnnotate를 사용하여 어셈블리의 투명도 위반 분석](http://go.microsoft.com/fwlink/?LinkId=187648) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013ca-159">For more information about the .NET Security Annotator, see the entry [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations](http://go.microsoft.com/fwlink/?LinkId=187648) in the .NET Security blog.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="013ca-160">예제</span><span class="sxs-lookup"><span data-stu-id="013ca-160">Examples</span></span>
