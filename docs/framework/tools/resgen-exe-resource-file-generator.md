---
title: "Resgen.exe(리소스 파일 생성기)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource files, .resources files
- resource files, .resx files
- resx files (resource files)
- .resources files
- files, converting
- Resource File Generator
- .resx files
- Resgen.exe
- resource files, converting
- converting files, Resource File Generator
- binary resources files
- embedding files in runtime binary executable
ms.assetid: 8ef159de-b660-4bec-9213-c3fbc4d1c6f4
caps.latest.revision: "46"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca54817183b5e659b62ef04b1693698bd689370b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="resgenexe-resource-file-generator"></a><span data-ttu-id="38464-102">Resgen.exe(리소스 파일 생성기)</span><span class="sxs-lookup"><span data-stu-id="38464-102">Resgen.exe (Resource File Generator)</span></span>
<span data-ttu-id="38464-103">리소스 파일 생성기(Resgen.exe)를 사용하면 텍스트 파일(.txt 또는 .restext)과 XML 기반 리소스 형식 파일(.resx)을 런타임 이진 실행 파일에 포함하거나 위성 어셈블리에 포함할 수 있는 공용 언어 런타임의 이진 파일(.resources)로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-103">The Resource File Generator (Resgen.exe) converts text (.txt or .restext) files and XML-based resource format (.resx) files to common language runtime binary (.resources) files that can be embedded in a runtime binary executable or satellite assembly.</span></span> <span data-ttu-id="38464-104">[리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-104">(See [Creating Resource Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).)</span></span>  
  
 <span data-ttu-id="38464-105">Resgen.exe는 다음 작업을 수행하는 범용 리소스 변환 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-105">Resgen.exe is a general-purpose resource conversion utility that performs the following tasks:</span></span>  
  
-   <span data-ttu-id="38464-106">.txt 또는 .restext 파일을 .resources 또는 .resx 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-106">Converts .txt or .restext files to .resources or .resx files.</span></span> <span data-ttu-id="38464-107">.restext 파일의 형식은 .txt 파일의 형식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-107">(The format of .restext files is identical to the format of .txt files.</span></span> <span data-ttu-id="38464-108">그러나 .restext 확장명을 통해 리소스 정의를 포함하고 있는 텍스트 파일을 보다 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-108">However, the .restext extension helps you identify text files that contain resource definitions more easily.)</span></span>  
  
-   <span data-ttu-id="38464-109">.resources 파일을 텍스트 또는 .resx 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-109">Converts .resources files to text or .resx files.</span></span>  
  
-   <span data-ttu-id="38464-110">.resx 파일을 텍스트 또는 .resources 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-110">Converts .resx files to text or .resources files.</span></span>  
  
-   <span data-ttu-id="38464-111">어셈블리로부터 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서 사용하기 적합한 .resw 파일로 문자열 리소스를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-111">Extracts the string resources from an assembly into a .resw file that is suitable for use in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span>  
  
-   <span data-ttu-id="38464-112">개별 명명된 리소스와 <xref:System.Resources.ResourceManager> 인스턴스에 대한 액세스를 제공하는 강력한 형식의 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-112">Creates a strongly typed class that provides access to individual named resources and to the <xref:System.Resources.ResourceManager> instance.</span></span>  
  
 <span data-ttu-id="38464-113">Resgen.exe에서 어떤 이유로든 오류가 발생하면 –1 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-113">If Resgen.exe fails for any reason, the return value is –1.</span></span>  
  
 <span data-ttu-id="38464-114">Resgen.exe의 도움말을 보려면 다음 명령을 명령 구문 및 Resgen.exe에 대한 옵션을 표시하도록 지정하는 옵션 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-114">To get help with Resgen,exe, you can use the following command, with no options specified, to display the command syntax and options for Resgen.exe:</span></span>  
  
```  
resgen  
```  
  
 <span data-ttu-id="38464-115">또한 `/?` 스위치를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-115">You can also use the `/?` switch:</span></span>  
  
```  
resgen /?  
```  
  
 <span data-ttu-id="38464-116">Resgen.exe를 사용하여 이진 .resources 파일을 만드는 경우 언어 컴파일러를 사용하여 이진 파일을 실행 가능 어셈블리에 포함하거나 [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-116">If you use Resgen,exe to generate binary .resources files, you can use a language compiler to embed the binary files into executable assemblies, or you can use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to compile them into satellite assemblies.</span></span>  
  
 <span data-ttu-id="38464-117">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-117">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="38464-118">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-118">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="38464-119">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-119">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="38464-120">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-120">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38464-121">구문</span><span class="sxs-lookup"><span data-stu-id="38464-121">Syntax</span></span>  
  
```  
resgen  [/define:symbol1[,symbol2,...]] [/useSourcePath] filename.extension  | /compile filename.extension... [outputFilename.extension] [/r:assembly] [/str:lang[,namespace[,class[,file]]] [/publicclass]]   
```  
  
```  
resgen filename.extension [outputDirectory]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38464-122">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38464-122">Parameters</span></span>  
  
|<span data-ttu-id="38464-123">매개 변수 또는 스위치</span><span class="sxs-lookup"><span data-stu-id="38464-123">Parameter or switch</span></span>|<span data-ttu-id="38464-124">설명</span><span class="sxs-lookup"><span data-stu-id="38464-124">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="38464-125">`/define:` *symbol1*[, *symbol2*,...]</span><span class="sxs-lookup"><span data-stu-id="38464-125">`/define:` *symbol1*[, *symbol2*,...]</span></span>|<span data-ttu-id="38464-126">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작하며 텍스트 기반(.txt 또는 .restext) 리소스 파일로 된 조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-126">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], supports conditional compilation in text-based (.txt or .restext) resource files.</span></span> <span data-ttu-id="38464-127">*symbol*이 `#ifdef` 구문 안의 입력 텍스트 파일에 포함된 기호에 해당하는 경우 연결된 문자열 리소스가 .resources 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-127">If *symbol* corresponds to a symbol included in the input text file within a `#ifdef` construct, the associated string resource is included in the .resources file.</span></span> <span data-ttu-id="38464-128">입력 텍스트 파일에 `#if !` 문이 `/define` 스위치에 의해 정의되지 않은 기호와 함께 포함되어 있는 경우 연결된 문자열 리소스는 리소스 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-128">If the input text file includes an `#if !` statement with a symbol that is not defined by the `/define` switch, the associated string resource is included in the resources file.</span></span><br /><br /> <span data-ttu-id="38464-129">`/define`은 텍스트가 아닌 파일과 함께 사용하는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-129">`/define` is ignored if it is used with non-text files.</span></span> <span data-ttu-id="38464-130">기호는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-130">Symbols are case-sensitive.</span></span><br /><br /> <span data-ttu-id="38464-131">이 옵션에 대한 자세한 내용은 이 항목의 뒤에 나오는 [리소스 조건부 컴파일](#Conditional)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-131">For more information about this option, see [Conditionally Compiling Resources](#Conditional) later in this topic.</span></span>|  
|`useSourcePath`|<span data-ttu-id="38464-132">입력 파일의 현재 디렉터리를 사용하여 상대 경로를 확인하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-132">Specifies that the input file's current directory is to be used to resolve relative file paths.</span></span>|  
|`/compile`|<span data-ttu-id="38464-133">단일 일괄 작업을 통해 여러 .resources 파일로 변환할 여러 .resx 또는 텍스트 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-133">Enables you to specify multiple .resx or text files to convert to multiple .resources files in a single bulk operation.</span></span> <span data-ttu-id="38464-134">이 옵션을 지정하지 않으면 입력 파일 인수를 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-134">If you do not specify this option, you can specify only one input file argument.</span></span> <span data-ttu-id="38464-135">출력 파일의 이름은 *filename*.resources입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-135">Output files are named *filename*.resources.</span></span><br /><br /> <span data-ttu-id="38464-136">이 옵션은 `/str:` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-136">This option cannot be used with the `/str:` option.</span></span><br /><br /> <span data-ttu-id="38464-137">이 옵션에 대한 자세한 내용은 이 항목의 뒤에 나오는 [다중 파일 컴파일 또는 변환](#Multiple)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-137">For more information about this option, see [Compiling or Converting Multiple Files](#Multiple) later in this topic.</span></span>|  
|<span data-ttu-id="38464-138">`/r:` `assembly`</span><span class="sxs-lookup"><span data-stu-id="38464-138">`/r:` `assembly`</span></span>|<span data-ttu-id="38464-139">지정한 어셈블리에서 메타데이터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-139">References metadata from the specified assembly.</span></span> <span data-ttu-id="38464-140">.Resx 파일을 변환할 때 사용하고 Resgen.exe를 통해 개체 리소스를 serialize하거나 deserialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-140">It is used when converting .resx files and allows Resgen.exe to serialize or deserialize object resources.</span></span> <span data-ttu-id="38464-141">C# 및 Visual Basic 컴파일러에 대한 `/reference:` 또는 `/r:` 옵션과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-141">It is similar to the `/reference:` or `/r:` options for the C# and Visual Basic compilers.</span></span>|  
|`filename.extension`|<span data-ttu-id="38464-142">변환할 입력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-142">Specifies the name of the input file to convert.</span></span> <span data-ttu-id="38464-143">이 테이블 앞에 나타난 첫째, 긴 명령줄 구문을 사용하는 경우 `extension`은 다음 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-143">If you're using the first, lengthier command-line syntax presented before this table,  `extension` must be one of the following:</span></span><br /><br /> <span data-ttu-id="38464-144">.txt 또는 .restext</span><span class="sxs-lookup"><span data-stu-id="38464-144">.txt or .restext</span></span><br /> <span data-ttu-id="38464-145">.resources 또는 .resx 파일로 변환할 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-145">A text file to convert to a .resources or a .resx file.</span></span> <span data-ttu-id="38464-146">텍스트 파일에는 문자열 리소스만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-146">Text files can contain only string resources.</span></span> <span data-ttu-id="38464-147">파일 형식에 대한 자세한 내용은 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)에서 "텍스트 파일의 리소스" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-147">For information about the file format, see the "Resources in Text Files" section of [Creating Resource Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).</span></span><br /><br /> <span data-ttu-id="38464-148">.resx</span><span class="sxs-lookup"><span data-stu-id="38464-148">.resx</span></span><br /> <span data-ttu-id="38464-149">.resources 또는 텍스트 파일(.txt 또는 .restext)로 변환할 XML 기반 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-149">An XML-based resource file to convert to a .resources or a text (.txt or .restext) file.</span></span><br /><br /> <span data-ttu-id="38464-150">.resources</span><span class="sxs-lookup"><span data-stu-id="38464-150">.resources</span></span><br /> <span data-ttu-id="38464-151">.resx 또는 텍스트(.txt 또는 .restext) 파일로 변환할 이진 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-151">A binary resource file to convert to a .resx or a text (.txt or .restext) file.</span></span><br /><br /> <span data-ttu-id="38464-152">이 테이블 앞에 표시되는 두 번째, 짧은 명령줄 구문을 사용하는 경우 `extension`은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-152">If you're using the second, shorter command-line syntax presented before this table, `extension` must be the following:</span></span><br /><br /> <span data-ttu-id="38464-153">.exe 또는 .dll</span><span class="sxs-lookup"><span data-stu-id="38464-153">.exe or .dll</span></span><br /> <span data-ttu-id="38464-154">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 개발하는 데 사용하는 .resw 파일로 문자열 리소스를 추출할 .NET Framework 어셈블리(실행 파일 또는 라이브러리)입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-154">A .NET Framework assembly (executable or library) whose string resources are to be extracted to a .resw file for use in developing [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>|  
|`outputFilename.extension`|<span data-ttu-id="38464-155">만들 리소스 파일의 이름 및 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-155">Specifies the name and type of the resource file to create.</span></span><br /><br /> <span data-ttu-id="38464-156">.txt, .restext 또는 .resx 파일을 .resources 파일로 변환하는 경우 이 인수는 선택적 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-156">This argument is optional when converting from a .txt, .restext, or .resx file to a .resources file.</span></span> <span data-ttu-id="38464-157">`outputFilename`을 지정하지 않으면 Resgen.exe에서는 입력 `filename`에 .resources 확장명을 추가하고 `filename,extension`이 들어 있는 디렉터리에 해당 파일을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="38464-157">If you do not specify `outputFilename`, Resgen.exe appends a .resources extension to the input `filename` and writes the file to the directory that contains `filename,extension`.</span></span><br /><br /> <span data-ttu-id="38464-158">`outputFilename.extension` 인수는 .resources 파일에서 변환할 때 사용되는 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-158">The `outputFilename.extension` argument is mandatory when converting from a .resources file.</span></span> <span data-ttu-id="38464-159">.resources 파일을 XML 기반 리소스 파일로 변환할 때에는 .resx 확장명을 갖는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-159">Specify a file name with the .resx extension when converting a .resources file to an XML-based resource file.</span></span> <span data-ttu-id="38464-160">.resources 파일을 텍스트 파일로 변환할 때는 .txt 또는 .restext 확장명을 갖는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-160">Specify a file name with the .txt or .restext extension when converting a .resources file to a text file.</span></span> <span data-ttu-id="38464-161">.resources 파일에 문자열 값만 있는 경우에는 .resources 파일을 .txt 파일로만 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-161">You should convert a .resources file to a .txt file only when the .resources file contains only string values.</span></span>|  
|`outputDirectory`|<span data-ttu-id="38464-162">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램의 경우 `filename.extension`에 있는 문자열 리소스를 포함하는 .resw 파일은 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-162">For [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, specifies the directory in which a .resw file that contains the string resources in `filename.extension` will be written.</span></span> <span data-ttu-id="38464-163">`outputDirectory`가 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-163">`outputDirectory` must already exist.</span></span>|  
|<span data-ttu-id="38464-164">`/str:` `language[,namespace[,classname[,filename]]]`</span><span class="sxs-lookup"><span data-stu-id="38464-164">`/str:` `language[,namespace[,classname[,filename]]]`</span></span>|<span data-ttu-id="38464-165">`language` 옵션에 지정된 프로그래밍 언어로 강력한 형식의 리소스 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-165">Creates a strongly typed resource class file in the programming language specified in the `language` option.</span></span> <span data-ttu-id="38464-166">`language`는 다음과 같은 리터럴 중 하나로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-166">`language` can consist of one of the following literals:</span></span><br /><br /> <span data-ttu-id="38464-167">-   C#의 경우: `c#`, `cs` 또는 `csharp`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-167">-   For C#: `c#`, `cs`, or `csharp`.</span></span><br /><span data-ttu-id="38464-168">-   Visual Basic의 경우: `vb` 또는 `visualbasic`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-168">-   For Visual Basic: `vb` or `visualbasic`.</span></span><br /><span data-ttu-id="38464-169">-   VBScript의 경우: `vbs` 또는 `vbscript`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-169">-   For VBScript: `vbs` or `vbscript`.</span></span><br /><span data-ttu-id="38464-170">-   C++의 경우: `c++`, `mc` 또는 `cpp`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-170">-   For C++: `c++`, `mc`, or `cpp`.</span></span><br /><span data-ttu-id="38464-171">-   JavaScript의 경우: `js`, `jscript` 또는 `javascript`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-171">-   For JavaScript: `js`, `jscript`, or `javascript`.</span></span><br /><br /> <span data-ttu-id="38464-172">`namespace` 옵션은 프로젝트의 기본 네임스페이스를 지정하고, `classname` 옵션은 생성되는 클래스의 이름을 지정하고, `filename` 옵션은 클래스 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-172">The `namespace` option specifies the project's default namespace, the `classname` option specifies the name of the generated class, and the `filename` option specifies the name of the class file.</span></span><br /><br /> <span data-ttu-id="38464-173">`/str:` 옵션에서는 입력 파일을 하나만 지정할 수 있으므로 이 옵션과 `/compile` 옵션을 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-173">The `/str:` option allows only one input file, so it cannot be used with the `/compile` option.</span></span><br /><br /> <span data-ttu-id="38464-174">`namespace`만 지정하고 `classname`은 지정하지 않을 경우 출력 파일 이름에서 마침표를 밑줄로 대체하는 등의 방식으로 클래스 이름이 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-174">If `namespace` is specified but `classname` is not, the class name is derived from the output file name (for example, underscores are substituted for periods).</span></span> <span data-ttu-id="38464-175">따라서 강력한 형식의 리소스가 제대로 작동하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-175">The strongly typed resources might not work correctly as a result.</span></span> <span data-ttu-id="38464-176">이 문제를 방지하려면 클래스 이름과 출력 파일 이름을 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-176">To avoid this, specify both class name and output file name.</span></span><br /><br /> <span data-ttu-id="38464-177">이 옵션에 대한 자세한 내용은 이 항목의 뒤에 나오는 [강력한 형식의 리소스 클래스 생성](#Strong)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-177">For more information about this option, see [Generating a Strongly Typed Resource Class](#Strong) later in this topic.</span></span>|  
|`/publicClass`|<span data-ttu-id="38464-178">공용 클래스로 강력한 형식의 리소스 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-178">Creates a strongly typed resource class as a public class.</span></span> <span data-ttu-id="38464-179">기본적으로 리소스 클래스는 C#에서 `internal`이고 Visual Basic에서는 `Friend`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-179">By default, the resource class is `internal` in C# and `Friend` in Visual Basic.</span></span><br /><br /> <span data-ttu-id="38464-180">`/str:` 옵션을 사용하지 않으면 이 옵션은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-180">This option is ignored if the `/str:` option is not used.</span></span>|  
  
## <a name="resgenexe-and-resource-file-types"></a><span data-ttu-id="38464-181">Resgen.exe 및 리소스 파일 생성기</span><span class="sxs-lookup"><span data-stu-id="38464-181">Resgen.exe and Resource File Types</span></span>  
 <span data-ttu-id="38464-182">Resgen.exe를 통해 리소스를 성공적으로 변환하기 위해 텍스트 및 .resx 파일은 올바른 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-182">In order for Resgen.exe to successfully convert resources, text and .resx files must follow the correct format.</span></span>  
  
### <a name="text-txt-and-restext-files"></a><span data-ttu-id="38464-183">텍스트(.txt 및 .restext) 파일</span><span class="sxs-lookup"><span data-stu-id="38464-183">Text (.txt and .restext) Files</span></span>  
 <span data-ttu-id="38464-184">텍스트 파일(.txt 또는 .restext)은 문자열 리소스만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-184">Text (.txt or .restext) files may contain only string resources.</span></span> <span data-ttu-id="38464-185">문자열을 여러 가지 언어로 번역해야 하는 응용 프로그램을 작성하는 경우에는 문자열 리소스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-185">String resources are useful if you are writing an application that must have strings translated into several languages.</span></span> <span data-ttu-id="38464-186">예를 들어, 해당 문자열 리소스를 사용하면 메뉴 문자열을 쉽게 지역화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-186">For example, you can easily regionalize menu strings by using the appropriate string resource.</span></span> <span data-ttu-id="38464-187">Resgen.exe를 사용하여 이름/값 쌍이 들어 있는 텍스트 파일을 읽습니다. 여기에서 이름은 해당 리소스를 설명하는 문자열이고, 값은 리소스 문자열 자체입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-187">Resgen.exe reads text files that contain name/value pairs, where the name is a string that describes the resource and the value is the resource string itself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38464-188">.txt 및 .restext 파일 형식에 대한 자세한 내용은 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)에서 "텍스트 파일의 리소스" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-188">For information about the format of .txt and .restext files, see the "Resources in Text Files" section of [Creating Resource Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>  
  
 <span data-ttu-id="38464-189">리소스를 포함하고 있는 텍스트 파일은 기본 라틴 범위(U+007F까지)의 문자만 포함하지 않는 경우 UTF-8 또는 유니코드(UTF-16) 인코딩으로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-189">A text file that contains resources must be saved with UTF-8 or Unicode (UTF-16) encoding unless it contains only characters in the Basic Latin range (to U+007F).</span></span> <span data-ttu-id="38464-190">Resgen.exe에서는 ANSI 인코딩으로 저장된 텍스트 파일을 처리할 때 확장된 ANSI 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-190">Resgen.exe removes extended ANSI characters when it processes a text file that is saved using ANSI encoding.</span></span>  
  
 <span data-ttu-id="38464-191">Resgen.exe를 사용하여 텍스트 파일에 중복된 리소스 이름이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-191">Resgen.exe checks the text file for duplicate resource names.</span></span> <span data-ttu-id="38464-192">텍스트 파일에 중복된 리소스 이름이 있으면 Resgen.exe에서는 경고를 표시하고 두 번째 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-192">If the text file contains duplicate resource names, Resgen.exe will emit a warning and ignore the second value.</span></span>  
  
### <a name="resx-files"></a><span data-ttu-id="38464-193">.resx 파일</span><span class="sxs-lookup"><span data-stu-id="38464-193">.resx Files</span></span>  
 <span data-ttu-id="38464-194">.resx 리소스 파일 형식은 XML 엔트리로 구성되며</span><span class="sxs-lookup"><span data-stu-id="38464-194">The .resx resource file format consists of XML entries.</span></span> <span data-ttu-id="38464-195">텍스트 파일과 유사한 방식으로 이 XML 엔트리 내에 문자열 리소스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-195">You can specify string resources within these XML entries, as you would in text files.</span></span> <span data-ttu-id="38464-196">텍스트 파일과 비교했을 때 .resx 파일에는 개체를 포함하거나 지정할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-196">A primary advantage of .resx files over text files is that you can also specify or embed objects.</span></span> <span data-ttu-id="38464-197">.resx 파일을 볼 때 그림과 같은 포함 개체의 이진 형식이 리소스 매니페스트의 일부인 경우에는 해당 이진 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-197">When you view a .resx file, you can see the binary form of an embedded object (for example, a picture) when this binary information is a part of the resource manifest.</span></span> <span data-ttu-id="38464-198">텍스트 파일과 마찬가지로 .resx 파일을 텍스트 편집기(예: 메모장 또는 Microsoft Word)에서 열어 내용을 쓰고 구문 분석 및 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-198">As with text files, you can open a .resx file with a text editor (such as Notepad or Microsoft Word) and write, parse, and manipulate its contents.</span></span> <span data-ttu-id="38464-199">이러한 작업을 수행하려면 XML 태그 및 .resx 파일의 구조에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-199">Note that this requires a good knowledge of XML tags and the .resx file structure.</span></span> <span data-ttu-id="38464-200">.resx 파일 형식에 대한 자세한 내용은 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)에서 ".resx 파일의 리소스" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-200">For more details on the .resx file format, see the "Resources in .resx Files" section of [Creating Resource Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>  
  
 <span data-ttu-id="38464-201">비문자열 포함 개체가 들어 있는 .resources 파일을 만들려면 Resgen.exe를 사용하여 개체가 들어 있는 .resx 파일을 변환하거나, <xref:System.Resources.ResourceWriter> 클래스에서 제공하는 메서드를 호출하여 코드에서 개체 리소스를 해당 파일에 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-201">In order to create a .resources file that contains embedded nonstring objects, you must either use Resgen.exe to convert a .resx file containing objects or add the object resources to your file directly from code by calling the methods provided by the <xref:System.Resources.ResourceWriter> class.</span></span>  
  
 <span data-ttu-id="38464-202">개체가 들어 있는 .resx 또는 .resources 파일을 Resgen.exe를 사용하여 텍스트 파일로 변환하면 모든 문자열 리소스는 올바르게 변환되지만 문자열이 아닌 개체의 데이터 형식도 파일에 문자열로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-202">If your .resx or .resources file contains objects and you use Resgen.exe to convert it to a text file, all the string resources will be converted correctly, but the data types of the nonstring objects will also be written to the file as strings.</span></span> <span data-ttu-id="38464-203">따라서 변환 시 포함 개체가 손실되고 Resgen.exe에서는 리소스 검색 시 오류가 발생했다는 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-203">You will lose the embedded objects in the conversion, and Resgen.exe will report that an error occurred in retrieving the resources.</span></span>  
  
### <a name="converting-between-resources-file-types"></a><span data-ttu-id="38464-204">리소스 파일 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="38464-204">Converting Between Resources File Types</span></span>  
 <span data-ttu-id="38464-205">다른 리소스 파일 형식 사이에 변환하는 경우, Resgen.exe는 변환을 수행할 수 없거나 원본 및 대상 파일 형식에 따라 특정 리소스에 대한 정보가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-205">When you convert between different resource file types, Resgen.exe may not be able to perform the conversion or may lose information about specific resources, depending on the source and target file types.</span></span> <span data-ttu-id="38464-206">다음 표에서는 리소스 파일 형식을 다른 형식으로 변환하는 경우 성공적으로 수행되는 변환의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-206">The following table specifies the types of conversions that are successful when converting from one resource file type to another.</span></span>  
  
|<span data-ttu-id="38464-207">변환 원본</span><span class="sxs-lookup"><span data-stu-id="38464-207">Convert from</span></span>|<span data-ttu-id="38464-208">텍스트 파일로</span><span class="sxs-lookup"><span data-stu-id="38464-208">To text file</span></span>|<span data-ttu-id="38464-209">.resx 파일로</span><span class="sxs-lookup"><span data-stu-id="38464-209">To .resx file</span></span>|<span data-ttu-id="38464-210">.resw 파일로</span><span class="sxs-lookup"><span data-stu-id="38464-210">To .resw file</span></span>|<span data-ttu-id="38464-211">.resources 파일로</span><span class="sxs-lookup"><span data-stu-id="38464-211">To .resources file</span></span>|  
|------------------|------------------|-------------------|-------------------|------------------------|  
|<span data-ttu-id="38464-212">텍스트(.txt 또는 .restext) 파일</span><span class="sxs-lookup"><span data-stu-id="38464-212">Text (.txt or .restext) file</span></span>|--|<span data-ttu-id="38464-213">문제 없음</span><span class="sxs-lookup"><span data-stu-id="38464-213">No issues</span></span>|<span data-ttu-id="38464-214">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-214">Not supported</span></span>|<span data-ttu-id="38464-215">문제 없음</span><span class="sxs-lookup"><span data-stu-id="38464-215">No issues</span></span>|  
|<span data-ttu-id="38464-216">.resx 파일</span><span class="sxs-lookup"><span data-stu-id="38464-216">.resx file</span></span>|<span data-ttu-id="38464-217">파일에 문자열이 아닌 리소스(파일 링크 포함)를 포함하는 경우 변환 실패</span><span class="sxs-lookup"><span data-stu-id="38464-217">Conversion fails if file contains non-string resources (including file links)</span></span>|--|<span data-ttu-id="38464-218">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-218">Not supported</span></span>|<span data-ttu-id="38464-219">문제 없음</span><span class="sxs-lookup"><span data-stu-id="38464-219">No issues</span></span>|  
|<span data-ttu-id="38464-220">.resources 파일</span><span class="sxs-lookup"><span data-stu-id="38464-220">.resources file</span></span>|<span data-ttu-id="38464-221">파일에 문자열이 아닌 리소스(파일 링크 포함)를 포함하는 경우 변환 실패</span><span class="sxs-lookup"><span data-stu-id="38464-221">Conversion fails if file contains non-string resources (including file links)</span></span>|<span data-ttu-id="38464-222">문제 없음</span><span class="sxs-lookup"><span data-stu-id="38464-222">No issues</span></span>|<span data-ttu-id="38464-223">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-223">Not supported</span></span>|--|  
|<span data-ttu-id="38464-224">.exe 또는 .dll 어셈블리</span><span class="sxs-lookup"><span data-stu-id="38464-224">.exe or .dll assembly</span></span>|<span data-ttu-id="38464-225">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-225">Not supported</span></span>|<span data-ttu-id="38464-226">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-226">Not supported</span></span>|<span data-ttu-id="38464-227">문자열 리소스(경로 이름 포함)만 리소스로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-227">Only string resources (including path names) are recognized as resources</span></span>|<span data-ttu-id="38464-228">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="38464-228">Not supported</span></span>|  
  
## <a name="performing-specific-resgenexe-tasks"></a><span data-ttu-id="38464-229">특정 Resgen.exe 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-229">Performing Specific Resgen.exe Tasks</span></span>  
 <span data-ttu-id="38464-230">텍스트 기반 또는 XML 기반 리소스 파일을 바이너리 파일로 컴파일, <xref:System.Resources.ResourceManager> 기능 래핑, 리소스로의 액세스를 제공하는 클래스 생성 등 다양한 방법으로 Resgen.exe를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-230">You can use Resgen.exe in diverse ways: to compile a text-based or XML-based resource file into a binary file, to convert between resource file formats, and to generate a class that wraps <xref:System.Resources.ResourceManager> functionality and provides access to resources.</span></span> <span data-ttu-id="38464-231">이 단원에서는 각 작업에 대해 자세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-231">This section provides detailed information about each task:</span></span>  
  
-   [<span data-ttu-id="38464-232">이진 파일에 리소스 컴파일</span><span class="sxs-lookup"><span data-stu-id="38464-232">Compiling Resources into a Binary File</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Compiling)  
  
-   [<span data-ttu-id="38464-233">리소스 파일 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="38464-233">Converting Between Resource File Types</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Convert)  
  
-   [<span data-ttu-id="38464-234">다중 파일 컴파일 또는 변환</span><span class="sxs-lookup"><span data-stu-id="38464-234">Compiling or Converting Multiple Files</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Multiple)  
  
-   [<span data-ttu-id="38464-235">.resw 파일에 리소스 내보내기</span><span class="sxs-lookup"><span data-stu-id="38464-235">Exporting Resources to a .resw File</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Exporting)  
  
-   [<span data-ttu-id="38464-236">리소스 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="38464-236">Conditionally Compiling Resources</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Conditional)  
  
-   [<span data-ttu-id="38464-237">강력한 형식의 리소스 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="38464-237">Generating a Strongly Typed Resource Class</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Strong)  
  
<a name="Compiling"></a>   
### <a name="compiling-resources-into-a-binary-file"></a><span data-ttu-id="38464-238">이진 파일에 리소스 컴파일</span><span class="sxs-lookup"><span data-stu-id="38464-238">Compiling Resources into a Binary File</span></span>  
 <span data-ttu-id="38464-239">resgen.exe는 텍스트 기반 리소스 파일(.txt 또는 .restext) 또는 XML 기반 리소스 파일(.resx 파일)을 이진 .resources 파일로 컴파일하는 데 가장 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-239">The most common use of Resgen.exe is to compile a text-based resource file (a .txt or .restext file) or an XML-based resource file (a .resx file) into a binary .resources file.</span></span> <span data-ttu-id="38464-240">언어 컴파일러를 사용하여 메인 어셈블리에 출력 파일을 포함시키거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-240">The output file then can be embedded in a main assembly by a language compiler or in a satellite assembly by [Assembly Linker (AL.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
 <span data-ttu-id="38464-241">리소스 파일을 컴파일하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-241">The syntax to compile a resource file is:</span></span>  
  
```  
resgen inputFilename [outputFilename]   
```  
  
 <span data-ttu-id="38464-242">여기서 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-242">where the parameters are:</span></span>  
  
 `inputFilename`  
 <span data-ttu-id="38464-243">컴파일할 리소스 파일의 파일 이름(확장명 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-243">The file name, including the extension, of the resource file to compile.</span></span> <span data-ttu-id="38464-244">Resgen.exe는 .txt, .restext 또는 .resx 확장명을 가진 파일만 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-244">Resgen.exe only compiles files with extensions of .txt, .restext, or .resx.</span></span>  
  
 `outputFilename`  
 <span data-ttu-id="38464-245">출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-245">The name of the output file.</span></span> <span data-ttu-id="38464-246">`outputFilename`을 생략하면 Resgen.exe가 `inputFilename`과 같은 디렉터리에 루트 파일 이름이 `inputFilename`인 .resources 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-246">If you omit `outputFilename`, Resgen.exe creates a .resources file with the root file name of `inputFilename` in the same directory as `inputFilename`.</span></span> <span data-ttu-id="38464-247">`outputFilename`에 디렉터리 경로가 포함되는 경우 디렉터리가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-247">If `outputFilename` includes a directory path, the directory must exist.</span></span>  
  
 <span data-ttu-id="38464-248">파일 이름에 지정하고 루트 파일 이름과 마침표로 구분하여 .resources 파일에 대한 완전히 정규화된 네임스페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-248">You provide a fully qualified namespace for the .resources file by specifying it in the file name and separating it from the root file name by a period.</span></span> <span data-ttu-id="38464-249">예를 들어 `outputFilename`이 `MyCompany.Libraries.Strings.resources`이면 네임스페이스는 MyCompany.Libraries입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-249">For example, if `outputFilename` is `MyCompany.Libraries.Strings.resources`, the namespace is MyCompany.Libraries.</span></span>  
  
 <span data-ttu-id="38464-250">다음 명령을 사용하여 Resources.txt에 있는 이름/값 쌍을 읽고 Resources.resources라는 이진 리소스 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-250">The following command reads the name/value pairs in Resources.txt and writes a binary .resources file named Resources.resources.</span></span> <span data-ttu-id="38464-251">출력 파일 이름은 명시적으로 지정되지 않기 때문에 기본적으로 입력 파일과 같은 이름을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-251">Because the output file name is not specified explicitly, it receives the same name as the input file by default.</span></span>  
  
```  
resgen Resources.txt   
```  
  
 <span data-ttu-id="38464-252">다음 명령을 사용하여 Resources.restext에 있는 이름/값 쌍을 읽고 StringResources.resources라는 이진 리소스 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-252">The following command reads the name/value pairs in Resources.restext and writes a binary resources file named StringResources.resources.</span></span>  
  
```  
resgen Resources.restext StringResources.resources  
```  
  
 <span data-ttu-id="38464-253">다음 명령을 사용하여 Resources.resx라는 XML 기반 입력 파일을 읽고 Resources.resources라는 이진 .resources 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-253">The following command reads an XML-based input file named Resources.resx and writes a binary .resources file named Resources.resources.</span></span>  
  
```  
resgen Resources.resx Resources.resources  
```  
  
<a name="Convert"></a>   
### <a name="converting-between-resource-file-types"></a><span data-ttu-id="38464-254">리소스 파일 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="38464-254">Converting Between Resource File Types</span></span>  
 <span data-ttu-id="38464-255">텍스트 기반 또는 XML 기반 리소스 파일을 이진 .resources 파일로 컴파일하는 것 이외에, Resgen.exe는 지원되는 모든 파일 형식을 지원되는 다른 파일 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-255">In addition to compiling text-based or XML-based resource files into binary .resources files, Resgen.exe can convert any supported file type to any other supported file type.</span></span> <span data-ttu-id="38464-256">이것은 다음과 변환을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-256">This means that it can perform the following conversions:</span></span>  
  
-   <span data-ttu-id="38464-257">.txt 및 .restext 파일을 .resx 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-257">.txt and .restext files to .resx files.</span></span>  
  
-   <span data-ttu-id="38464-258">.resx 파일을 .txt 및 .restext 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-258">.resx files to .txt and .restext files.</span></span>  
  
-   <span data-ttu-id="38464-259">.resources 파일을 .txt 및 .restext 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-259">.resources files to .txt and .restext files.</span></span>  
  
-   <span data-ttu-id="38464-260">.resources 파일을 .resx 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-260">.resources files to .resx files.</span></span>  
  
 <span data-ttu-id="38464-261">구문은 이전 단원에 나와 있는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-261">The syntax is the same as that shown in the previous section.</span></span>  
  
 <span data-ttu-id="38464-262">또한, Resgen.exe을 사용하여 .NET Framework 어셈블리의 포함 리소스를 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램용 .resw 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-262">In addition, you can use Resgen.exe to convert embedded resources in a .NET Framework assembly to a .resw file tor [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 <span data-ttu-id="38464-263">다음 명령을 사용하여 이진 리소스 파일 Resources.resources를 읽고 Resources.resx라는 XML 기반 출력 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-263">The following command reads a binary resources file Resources.resources and writes an XML-based output file named Resources.resx.</span></span>  
  
```  
resgen Resources.resources Resources.resx  
```  
  
 <span data-ttu-id="38464-264">다음 명령을 사용하여 StringResources.txt라는 텍스트 기반 리소스 파일을 읽고, LibraryResources.resx라는 XML 기반 입력 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-264">The following command reads a text-based resources file named StringResources.txt and writes an XML-based resources file named LibraryResources.resx.</span></span> <span data-ttu-id="38464-265">문자열 리소스를 포함하는 용도 외에 .resx 파일은 문자열 이외의 리소스를 저장하는 데에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-265">In addition to containing string resources, the .resx file could also be used to store non-string resources.</span></span>  
  
```  
resgen StringResources.txt LibraryResources.resx  
```  
  
 <span data-ttu-id="38464-266">다음 두 명령은 Resources.resx라는 XML 기반 입력 파일을 읽고 Resources.txt 및 Resources.restext라는 텍스트 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-266">The following two commands read an XML-based resources file named Resources.resx and write text files named Resources.txt and Resources.restext.</span></span> <span data-ttu-id="38464-267">.resx 파일에 포함 개체가 있으면 텍스트 파일로 정확하게 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-267">Note that if the .resx file contains any embedded objects, they will not be accurately converted into the text files.</span></span>  
  
```  
resgen Resources.resx Resources.txt  
resgen Resources.resx Resources.restext  
```  
  
<a name="Multiple"></a>   
### <a name="compiling-or-converting-multiple-files"></a><span data-ttu-id="38464-268">다중 파일 컴파일 또는 변환</span><span class="sxs-lookup"><span data-stu-id="38464-268">Compiling or Converting Multiple Files</span></span>  
 <span data-ttu-id="38464-269">`/compile` 스위치를 사용하여 단일 연산에서 하나의 포맷으로부터 다른 포맷으로 리소스 파일 목록을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-269">You can use the `/compile` switch to convert a list of resource files from one format to another in a single operation.</span></span> <span data-ttu-id="38464-270">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-270">The syntax is:</span></span>  
  
```  
resgen /compile filename.extension [filename.extension...]  
```  
  
 <span data-ttu-id="38464-271">다음 명령은 세 파일, StringResources.txt, TableResources.resw 및 ImageResources.resw를 StringResources.resources, TableResources.resources 및 ImageResources.resources라는 별도의 resources 파일로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-271">The following command compiles three files, StringResources.txt, TableResources.resw, and ImageResources.resw, into separate .resources files named StringResources.resources, TableResources.resources, and ImageResources.resources.</span></span>  
  
```  
resgen /compile StringResources.txt TableResources.resx ImageResources.resx  
```  
  
<a name="Exporting"></a>   
### <a name="exporting-resources-to-a-resw-file"></a><span data-ttu-id="38464-272">.resw 파일에 리소스 내보내기</span><span class="sxs-lookup"><span data-stu-id="38464-272">Exporting Resources to a .resw File</span></span>  
 <span data-ttu-id="38464-273">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 개발하는 경우, 기존 데스크톱 응용 프로그램의 리소스를 사용하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-273">If you're developing a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, you may want to use resources from an existing desktop app.</span></span> <span data-ttu-id="38464-274">하지만 두 종류의 응용 프로그램은 다른 파일 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-274">However, the two kinds of applications support different file formats.</span></span> <span data-ttu-id="38464-275">데스크톱 응용 프로그램에서 텍스트(.txt 또는.restext) 또는.resx 파일의 리소스는 이진 .resources 파일로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-275">In desktop apps, resources in text (.txt or .restext) or .resx files are compiled into binary .resources files.</span></span> <span data-ttu-id="38464-276">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서 .resw 파일은 이진 패키지 리소스 인덱스(PRI) 파일로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-276">In [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, .resw files are compiled into binary package resource index (PRI) files.</span></span> <span data-ttu-id="38464-277">실행 가능한 또는 위성 어셈블리에서 리소스를 추출하거나 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램 개발 시 사용할 수 있는 하나 이상의 .resw 파일을 작성하여 이 간격을 연결하는 데 Resgen.exe을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-277">You can use Resgen.exe to bridge this gap by extracting resources from an executable or a satellite assembly and writing them to one or more .resw files that can be used when developing a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38464-278">Visual Studio는 휴대용 라이브러리에서 리소스를 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에 통합시키는 데 필요한 모든 변환을 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-278">Visual Studio automatically handles all conversions necessary for incorporating the resources in a portable library into a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="38464-279">어셈블리에서 리소스를 .resw 파일 형식으로 변환하기 위해 .Resgen.exe를 직접 사용하는 것은 Visual Studio 외부에서 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 개발하려고 하는 개발자에게만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-279">Using Resgen.exe directly to convert the resources in an assembly to .resw file format is of interest only to developers who want to develop a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app outside of Visual Studio.</span></span>  
  
 <span data-ttu-id="38464-280">어셈블리에서 .resw 파일을 생성하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-280">The syntax to generate .resw files from an assembly is:</span></span>  
  
```  
resgen filename.extension  [outputDirectory]  
```  
  
 <span data-ttu-id="38464-281">여기서 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-281">where the parameters are:</span></span>  
  
 `filename.extension`  
 <span data-ttu-id="38464-282">.NET Framework 어셈블리(실행 파일 또는 .DLL)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-282">The name of a .NET Framework assembly (an executable or .DLL).</span></span> <span data-ttu-id="38464-283">파일에 리소스가 포함되어 있으면 Resgen.exe는 파일을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-283">If the file contains no resources, Resgen.exe does not create any files.</span></span>  
  
 `outputDirectory`  
 <span data-ttu-id="38464-284">.resw 파일을 쓸 기존 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-284">The existing directory to which to write the .resw files.</span></span> <span data-ttu-id="38464-285">`outputDirectory`를 생략하면 .resw 파일이 현재 디렉터리에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-285">If `outputDirectory` is omitted, .resw files are written to the current directory.</span></span> <span data-ttu-id="38464-286">Resgen.exe는 어셈블리에 각 .resources 파일에 대한 .resw 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-286">Resgen.exe creates one .resw file for each .resources file in the assembly.</span></span> <span data-ttu-id="38464-287">.resw 파일의 루트 파일 이름은 .resources 파일의 루트 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-287">The root file name of the .resw file is the same as the root name of the .resources file.</span></span>  
  
 <span data-ttu-id="38464-288">다음 명령은 MyApp.exe에 포함된 각 resources 파일에 대한 Win8Resources 디렉터리에 .resw 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-288">The following command creates a .resw file in the Win8Resources directory for each .resources file embedded in MyApp.exe:</span></span>  
  
```  
resgen MyApp.exe Win8Resources  
```  
  
<a name="Conditional"></a>   
### <a name="conditionally-compiling-resources"></a><span data-ttu-id="38464-289">리소스 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="38464-289">Conditionally Compiling Resources</span></span>  
 <span data-ttu-id="38464-290">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작하는 Resgen.exe에서는 텍스트(.txt 및 .restext) 파일로 된 문자열 리소스의 조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-290">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Resgen.exe supports conditional compilation of string resources in text (.txt and .restext) files.</span></span> <span data-ttu-id="38464-291">이것은 여러 빌드 구성에 단일 텍스트 기반 리소스 파일을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-291">This enables you to use a single text-based resource file in multiple build configurations.</span></span>  
  
 <span data-ttu-id="38464-292">.txt 또는 .restext 파일에서 기호가 정의된 경우 `#ifdef`...`#endif`</span><span class="sxs-lookup"><span data-stu-id="38464-292">In a .txt or .restext file, you use the `#ifdef`…`#endif`</span></span> <span data-ttu-id="38464-293">구문을 사용하며 이진 .resources 파일에 리소스를 포함하고, 기호가 정의되지 않은 경우 `#if !`...`#endif` 구문을 사용하여 리소스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-293">construct to include a resource in the binary .resources file if a symbol is defined, and you use the `#if !`... `#endif` construct to include a resource if a symbol is not defined.</span></span> <span data-ttu-id="38464-294">컴파일할 때 `/define:` 옵션과 쉼표로 구분된 기호 목록을 사용하여 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-294">At compile time, you then define symbols by using the `/define:` option followed by a comma-delimited list of symbols.</span></span> <span data-ttu-id="38464-295">비교는 대/소문자를 구분합니다. `/define`으로 정의된 기호의 대/소문자는 컴파일될 텍스트 파일에 있는 기호의 대/소문자와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-295">The comparison is cased-sensitive; the case of symbols defined by `/define` must match the case of symbols in the text files to be compiled.</span></span>  
  
 <span data-ttu-id="38464-296">예를 들어, 다음의 UIResources.rext라는 파일에는 `AppTitle`, `PRODUCTION` 또는 `CONSULT`이라는 기호가 정의되어 있는지 여부에 따라 3개의 값 중 하나를 사용할 수 있는 `RETAIL`이라는 문자열 리소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-296">For example, the following file named UIResources.rext includes a string resource named `AppTitle` that can take one of three values, depending on whether symbols named `PRODUCTION`, `CONSULT`, or `RETAIL` are defined.</span></span>  
  
```  
#ifdef PRODUCTION  
AppTitle=My Software Company Project Manager   
#endif  
#ifdef CONSULT  
AppTitle=My Consulting Company Project Manager  
#endif  
#ifdef RETAIL  
AppTitle=My Retail Store Project Manager  
#endif  
FileMenuName=File  
```  
  
 <span data-ttu-id="38464-297">그런 다음 파일은 다음 명령을 사용하여 이진 .resources 파일로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-297">The file can then be compiled into a binary .resources file with the following command:</span></span>  
  
```  
resgen /define:CONSULT UIResources.restext  
```  
  
 <span data-ttu-id="38464-298">그러면 두 문자열 리소스가 있는 리소스 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-298">This produces a .resources file that contains two string resources.</span></span> <span data-ttu-id="38464-299">`AppTitle` 리소스 값은 "내 컨설팅 회사 프로젝트 관리자"입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-299">The value of the `AppTitle` resource is "My Consulting Company Project Manager".</span></span>  
  
<a name="Strong"></a>   
### <a name="generating-a-strongly-typed-resource-class"></a><span data-ttu-id="38464-300">강력한 형식의 리소스 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="38464-300">Generating a Strongly Typed Resource Class</span></span>  
 <span data-ttu-id="38464-301">Resgen.exe는 강력한 형식의 리소스를 지원하고, 이러한 리소스는 컴파일 타임에 읽기 전용의 정적 속성을 포함하는 클래스를 만들어 리소스에 대한 액세스를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-301">Resgen.exe supports strongly typed resources, which encapsulates access to resources by creating classes that contain a set of static read-only properties.</span></span> <span data-ttu-id="38464-302">이 기능은 리소스를 검색하기 위해 <xref:System.Resources.ResourceManager> 클래스의 메서드를 직접 호출하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-302">This provides an alternative to calling the methods of the <xref:System.Resources.ResourceManager> class directly to retrieve resources.</span></span> <span data-ttu-id="38464-303">`/str` 클래스의 함수를 래핑하는 Resgen.exe의 <xref:System.Resources.Tools.StronglyTypedResourceBuilder> 옵션을 사용하여 강력한 형식의 리소스 지원이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-303">You can enable strongly typed resource support by using the `/str` option in Resgen.exe, which wraps the functionality of the <xref:System.Resources.Tools.StronglyTypedResourceBuilder> class.</span></span> <span data-ttu-id="38464-304">`/str` 옵션을 지정하면 입력 매개 변수에서 참조되는 리소스와 일치하는 강력한 형식의 속성이 포함된 클래스가 Resgen.exe의 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-304">When you specify the `/str` option, the output of Resgen.exe is a class that contains strongly typed properties that match the resources that are referenced in the input parameter.</span></span> <span data-ttu-id="38464-305">이 클래스는 처리된 파일에서 사용할 수 있는 리소스에 대한 강력한 형식의 읽기 전용 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-305">This class provides strongly typed read-only access to the resources that are available in the file processed.</span></span>  
  
 <span data-ttu-id="38464-306">강력한 형식의 리소스를 만드는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-306">The syntax to create a strongly typed resource is:</span></span>  
  
```  
resgen inputFilename [outputFilename] /str:language[,namespace,[classname[,filename]]] [/publicClass]  
```  
  
 <span data-ttu-id="38464-307">매개 변수 및 스위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-307">The parameters and switches are:</span></span>  
  
 `inputFilename`  
 <span data-ttu-id="38464-308">강력한 형식의 리소스 클래스를 생성할 리소스 파일의 파일 이름입니다(확장명 포함).</span><span class="sxs-lookup"><span data-stu-id="38464-308">The file name, including the extension, of the resource file for which to generate a strongly typed resource class.</span></span> <span data-ttu-id="38464-309">파일은 텍스트 기반, XML 기반 또는 이진 .resources 파일일 수 있으며 .txt, .restext, .resw 또는 .resources 확장명을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-309">The file can be a text-based, XML-based, or binary .resources file; it can have an extension of .txt, .restext, .resw, or .resources.</span></span>  
  
 `outputFilename`  
 <span data-ttu-id="38464-310">출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-310">The name of the output file.</span></span> <span data-ttu-id="38464-311">`outputFilename`에 디렉터리 경로가 포함되는 경우 디렉터리가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-311">If `outputFilename` includes a directory path, the directory must exist.</span></span> <span data-ttu-id="38464-312">`outputFilename`을 생략하면 Resgen.exe가 `inputFilename`과 같은 디렉터리에 루트 파일 이름이 `inputFilename`인 .resources 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38464-312">If you omit `outputFilename`, Resgen.exe creates a .resources file with the root file name of `inputFilename` in the same directory as `inputFilename`.</span></span>  
  
 <span data-ttu-id="38464-313">`outputFilename`은 텍스트 기반 XML 기반 또는 이진 .resources 파일일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-313">`outputFilename` can be a text-based, XML-based, or binary .resources file.</span></span> <span data-ttu-id="38464-314">`outputFilename`의 파일 확장명이 `inputFilename`의 파일 확장명과 다를 경우 Resgen.exe는 파일 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-314">If the file extension of `outputFilename` is different from the file extension of `inputFilename`, Resgen.exe performs the file conversion.</span></span>  
  
 <span data-ttu-id="38464-315">`inputFilename`이 .resources 파일인 경우 `outputFilename`도 .resources 파일이면 Resgen.exe가 .resources 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-315">If `inputFilename` is a .resources file, Resgen.exe copies the .resources file if `outputFilename` is also a .resources file.</span></span> <span data-ttu-id="38464-316">`outputFilename`을 생략할 경우 Resgen.exe가 `inputFilename`을 동일한 .resources 파일로 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="38464-316">If `outputFilename` is omitted, Resgen.exe overwrites `inputFilename` with an identical .resources file.</span></span>  
  
 <span data-ttu-id="38464-317">*language*</span><span class="sxs-lookup"><span data-stu-id="38464-317">*language*</span></span>  
 <span data-ttu-id="38464-318">강력한 형식의 리소스 클래스에 대한 소스 코드를 생성할 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-318">The language in which to generate source code for the strongly-typed resource class.</span></span> <span data-ttu-id="38464-319">가능한 값은 `cs`, `C#`, `csharp`(C# 코드), `vb`, `visualbasic`(Visual Basic 코드), `vbs`, `vbscript`(VBScript 코드), `c++`, `mc`, `cpp`(C++ 코드)입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-319">Possible values are `cs`, `C#`, and `csharp` for C# code, `vb` and `visualbasic` for Visual Basic code, `vbs` and `vbscript` for VBScript code, and `c++`, `mc`, and `cpp` for C++ code.</span></span>  
  
 <span data-ttu-id="38464-320">*namespace*</span><span class="sxs-lookup"><span data-stu-id="38464-320">*namespace*</span></span>  
 <span data-ttu-id="38464-321">강력한 형식의 리소스 클래스에 포함된 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-321">The namespace that contains the strongly typed resource class.</span></span> <span data-ttu-id="38464-322">.Resources 파일과 리소스 클래스의 네임스페이스는 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-322">The .resources file and the resource class should have the same namespace.</span></span> <span data-ttu-id="38464-323">`outputFilename`에서 네임스페이스를 지정하는 방법에 대한 자세한 내용은 [이진 파일에 리소스 컴파일](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Compiling)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38464-323">For information about specifying the namespace in the `outputFilename`, see [Compiling Resources into a Binary File](../../../docs/framework/tools/resgen-exe-resource-file-generator.md#Compiling).</span></span> <span data-ttu-id="38464-324">*namespace*를 생략하면 리소스 클래스가 네임스페이스에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-324">If *namespace* is omitted, the resource class is not contained in a namespace.</span></span>  
  
 <span data-ttu-id="38464-325">*classname*</span><span class="sxs-lookup"><span data-stu-id="38464-325">*classname*</span></span>  
 <span data-ttu-id="38464-326">강력한 형식의 리소스 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-326">The name of the strongly typed resource class.</span></span> <span data-ttu-id="38464-327">이 값은 .resources 파일의 루트 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-327">This should correspond to the root name of the .resources file.</span></span> <span data-ttu-id="38464-328">예를 들어, Resgen.exe에서 MyCompany.Libraries.Strings.resources라는 이름의 .resources 파일을 생성하면 강력한 형식의 리소스 클래스의 이름은 Strings입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-328">For example, if Resgen.exe generates a .resources file named MyCompany.Libraries.Strings.resources, the name of the strongly typed resource class is Strings.</span></span> <span data-ttu-id="38464-329">*classname*을 생략할 경우 생성된 클래스는 `outputFilename`의 루트 이름에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-329">If *classname* is omitted, the generated class is derived from the root name of `outputFilename`.</span></span> <span data-ttu-id="38464-330">`outputFilename`을 생략할 경우 생성된 클래스는 `inputFilename`의 루트 이름에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="38464-330">If `outputFilename` is omitted, the generated class is derived from the root name of `inputFilename`.</span></span>  
  
 <span data-ttu-id="38464-331">*classname*은 공백과 같은 유효하지 않은 문자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-331">*classname* cannot contain invalid characters such as embedded spaces.</span></span> <span data-ttu-id="38464-332">*classname*이 공백을 포함하거나 *classname*이 *inputFilename*에서 기본적으로 생성되었고 *inputFilename*이 공백을 포함한다면, Resgen.exe는 유효하지 않은 모든 문자를 밑줄(_)로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-332">If *classname* contains embedded spaces, or if *classname* is generated by default from *inputFilename*, and *inputFilename* contains embedded spaces, Resgen.exe replaces all invalid characters with an underscore (_).</span></span>  
  
 <span data-ttu-id="38464-333">*filename*</span><span class="sxs-lookup"><span data-stu-id="38464-333">*filename*</span></span>  
 <span data-ttu-id="38464-334">클래스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-334">The name of the class file.</span></span>  
  
 `/publicclass`  
 <span data-ttu-id="38464-335">강력한 형식의 리소스 클래스를 `internal`(C#) 또는 `Friend`(Visual Basic)가 아닌 공용으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-335">Makes the strongly typed resource class public rather than `internal` (in C#) or `Friend` (in Visual Basic).</span></span> <span data-ttu-id="38464-336">이렇게 하면 리소스가 포함된 어셈블리 외부에서 리소스를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-336">This allows the resources to be accessed from outside the assembly in which they are embedded.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38464-337">강력한 형식의 리소스 클래스를 만들 때 .resources 파일의 이름은 생성된 코드의 네임스페이스 및 클래스 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-337">When you create a strongly typed resource class, the name of your .resources file must match the namespace and class name of the generated code.</span></span> <span data-ttu-id="38464-338">하지만 Resgen.exe를 사용하면 호환되지 않는 이름을 가진 .resources 파일을 생성하는 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-338">However, Resgen.exe allows you to specify options that produce a .resources file that has an incompatible name.</span></span> <span data-ttu-id="38464-339">이 문제를 해결하려면 생성된 후에 출력 파일 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="38464-339">To work around this behavior, rename the output file after it has been generated.</span></span>  
  
 <span data-ttu-id="38464-340">강력한 형식의 리소스 클래스에는 다음과 같은 구성원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38464-340">The strongly typed resource class has the following members:</span></span>  
  
-   <span data-ttu-id="38464-341">강력한 형식의 리소스 클래스를 인스턴스화하는 데 사용할 수 있는 매개 변수 없는 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-341">A parameterless constructor, which can be used to instantiate the strongly typed resource class..</span></span>  
  
-   <span data-ttu-id="38464-342">강력한 형식의 리소스를 관리하는 `static` 인스턴스를 반환하는 `Shared`(C#) 또는 `ResourceManager`(Visual Basic) 및 읽기 전용 <xref:System.Resources.ResourceManager> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-342">A `static` (C#) or `Shared` (Visual Basic) and read-only `ResourceManager` property, which returns the <xref:System.Resources.ResourceManager> instance that manages the strongly typed resource.</span></span>  
  
-   <span data-ttu-id="38464-343">리소스 검색에 사용되는 문화권을 설정할 수 있도록 하는 정적 `Culture` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-343">A static `Culture` property, which allows you to set the culture used for resource retrieval.</span></span> <span data-ttu-id="38464-344">기본적으로 값은 현재 UI 문화권이 사용됨을 의미하는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-344">By default, its value is `null`, which means that that the current UI culture is used.</span></span>  
  
-   <span data-ttu-id="38464-345">하나의 `static`(C#) 또는 `Shared`(Visual Basic) 및 .resources 파일의 각 리소스에 대한 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-345">One `static` (C#) or `Shared` (Visual Basic) and read-only property for each resource in the .resources file.</span></span> <span data-ttu-id="38464-346">속성 이름은 리소스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38464-346">The name of the property is the name of the resource.-</span></span>  
  
 <span data-ttu-id="38464-347">예를 들어, 다음 명령은 StringResources.txt라는 리소스 파일을 StringResources.resources로 컴파일하고 리소스 관리자에 액세스하는 데 사용할 수 있는 StringResources.vb라는 Visual Basic 소스 코드 파일에서 `StringResources`라는 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="38464-347">For example, the following command compiles a resource file named StringResources.txt into StringResources.resources and generates a class named `StringResources` in a Visual Basic source code file named StringResources.vb that can be used to access the Resource Manager.</span></span>  
  
```  
resgen StringResources.txt /str:vb,,StringResources   
```  
  
## <a name="see-also"></a><span data-ttu-id="38464-348">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38464-348">See Also</span></span>  
 [<span data-ttu-id="38464-349">도구</span><span class="sxs-lookup"><span data-stu-id="38464-349">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="38464-350">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="38464-350">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)  
 [<span data-ttu-id="38464-351">리소스 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="38464-351">Creating Resource Files</span></span>](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)  
 [<span data-ttu-id="38464-352">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="38464-352">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="38464-353">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="38464-353">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
