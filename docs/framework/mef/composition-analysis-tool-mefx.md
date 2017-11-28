---
title: "컴퍼지션 분석 도구(Mefx)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 740ba87fd247e05b1bc32e3732819514ba2806ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="composition-analysis-tool-mefx"></a><span data-ttu-id="30021-102">컴퍼지션 분석 도구(Mefx)</span><span class="sxs-lookup"><span data-stu-id="30021-102">Composition Analysis Tool (Mefx)</span></span>
<span data-ttu-id="30021-103">컴퍼지션 분석 도구(Mefx)는 MEF(Managed Extensibility Framework) 파트를 포함하는 라이브러리(.dll) 및 응용 프로그램(.exe) 파일을 분석하는 명령줄 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="30021-103">The Composition Analysis Tool (Mefx) is a command-line application that analyzes library (.dll) and application (.exe) files containing Managed Extensibility Framework (MEF) parts.</span></span> <span data-ttu-id="30021-104">Mefx는 주로 번거로운 추적 코드를 응용 프로그램 자체에 추가할 필요 없이 MEF 응용 프로그램에서 컴퍼지션 실패를 진단하는 방법을 개발자에게 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-104">The primary purpose of Mefx is to provide developers a way to diagnose composition failures in their MEF applications without the requirement to add cumbersome tracing code to the application itself.</span></span> <span data-ttu-id="30021-105">타사에서 제공된 라이브러리의 파트를 이해할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-105">It can also be useful to help understand parts from a library provided by a third party.</span></span> <span data-ttu-id="30021-106">이 항목에서는 Mefx를 사용하는 방법을 설명하고 해당 구문에 대한 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-106">This topic describes how to use Mefx and provides a reference for its syntax.</span></span>  
  
<a name="getting_mefx"></a>   
## <a name="getting-mefx"></a><span data-ttu-id="30021-107">Mefx 가져오기</span><span class="sxs-lookup"><span data-stu-id="30021-107">Getting Mefx</span></span>  
 <span data-ttu-id="30021-108">Mefx는 GitHub에서 [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0)합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-108">Mefx is available on GitHub at [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span></span> <span data-ttu-id="30021-109">도구를 다운로드하고 압축을 풀면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-109">Simply download and unzip the tool.</span></span>  
  
<a name="basic_syntax"></a>   
## <a name="basic-syntax"></a><span data-ttu-id="30021-110">기본 구문</span><span class="sxs-lookup"><span data-stu-id="30021-110">Basic Syntax</span></span>  
 <span data-ttu-id="30021-111">Mefx는 명령줄에서 다음 형식으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-111">Mefx is invoked from the command line in the following format:</span></span>  
  
```  
mefx [files and directories] [action] [options]  
```  
  
 <span data-ttu-id="30021-112">첫 번째 인수 집합은 분석할 파트를 로드할 소스 파일 및 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-112">The first set of arguments specify the files and directories from which to load parts for analysis.</span></span> <span data-ttu-id="30021-113">`/file:` 스위치를 사용하여 파일을 지정하고 `/directory:` 스위치를 사용하여 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-113">Specify a file with the `/file:` switch, and a directory with the `/directory:` switch.</span></span> <span data-ttu-id="30021-114">다음 예제와 같이 여러 파일 또는 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-114">You can specify multiple files or directories, as shown in the following example:</span></span>  
  
```  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
>  <span data-ttu-id="30021-115">각 .dll 또는 .exe는 한 번만 로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-115">Each .dll or .exe should only be loaded one time.</span></span> <span data-ttu-id="30021-116">파일이 여러 번 로드되면 도구가 잘못된 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-116">If a file is loaded multiple times, the tool may return incorrect information.</span></span>  
  
 <span data-ttu-id="30021-117">파일 및 디렉터리 목록 다음에 명령 및 해당 명령의 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-117">After the list of files and directories, you must specify a command, and any options for that command.</span></span>  
  
<a name="listing_available_parts"></a>   
## <a name="listing-available-parts"></a><span data-ttu-id="30021-118">사용 가능한 파트 나열</span><span class="sxs-lookup"><span data-stu-id="30021-118">Listing Available Parts</span></span>  
 <span data-ttu-id="30021-119">`/parts` 작업을 사용하여 로드된 파일에서 선언된 모든 파트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-119">Use the `/parts` action to list all the parts declared in the files loaded.</span></span> <span data-ttu-id="30021-120">결과는 단순한 파트 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="30021-120">The result is a simple list of part names.</span></span>  
  
```  
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 <span data-ttu-id="30021-121">파트에 대한 자세한 내용은 `/verbose` 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="30021-121">For more information about the parts, use the `/verbose` option.</span></span> <span data-ttu-id="30021-122">이를 통해 모든 사용 가능한 파트에 대한 자세한 정보가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-122">This will output more information for all available parts.</span></span> <span data-ttu-id="30021-123">단일 파트에 대한 자세한 정보를 가져오려면 `/type` 대신 `/parts`작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-123">To get more information about a single part, use the `/type` action instead of `/parts`.</span></span>  
  
```  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>   
## <a name="listing-imports-and-exports"></a><span data-ttu-id="30021-124">가져오기 및 내보내기 나열</span><span class="sxs-lookup"><span data-stu-id="30021-124">Listing Imports and Exports</span></span>  
 <span data-ttu-id="30021-125">`/imports` 및 `/exports` 작업은 각각 모든 가져온 파트 및 모든 내보낸 파트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-125">The `/imports` and `/exports` actions will list all the imported parts and all the exported parts, respectively.</span></span> <span data-ttu-id="30021-126">`/importers` 또는 `/exporters` 작업을 사용하여 특정 형식을 가져오거나 내보내는 파트를 나열할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-126">You can also list the parts that import or export a particular type by using the `/importers` or `/exporters` actions.</span></span>  
  
```  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 <span data-ttu-id="30021-127">이들 작업에 `/verbose` 옵션을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-127">You can also apply the `/verbose` option to these actions.</span></span>  
  
<a name="finding_rejected_parts"></a>   
## <a name="finding-rejected-parts"></a><span data-ttu-id="30021-128">거부된 파트 찾기</span><span class="sxs-lookup"><span data-stu-id="30021-128">Finding Rejected Parts</span></span>  
 <span data-ttu-id="30021-129">사용 가능한 파트를 로드한 후 Mefx는 MEF 컴퍼지션 엔진을 사용하여 파트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-129">Once it has loaded the available parts, Mefx uses the MEF composition engine to compose them.</span></span> <span data-ttu-id="30021-130">성공적으로 구성할 수 없는 파트를 *거부됨*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-130">Parts that cannot be successfully composed are referred to as *rejected*.</span></span> <span data-ttu-id="30021-131">거부된 파트를 모두 나열하려면 `/rejected` 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-131">To list all the rejected parts, use the `/rejected` action.</span></span>  
  
 <span data-ttu-id="30021-132">`/verbose` 옵션을 `/rejected` 작업과 함께 사용하여 거부된 파트에 대한 자세한 정보를 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-132">You can use the `/verbose` option with the `/rejected` action to print detailed information about rejected parts.</span></span> <span data-ttu-id="30021-133">다음 예제에서 `ClassLibrary1` DLL은 `AddIn` 및 `MemberPart` 파트를 가져오는 `ChainOne` 파트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-133">In the following example, the `ClassLibrary1` DLL contains the `AddIn` part, which imports the `MemberPart` and `ChainOne` parts.</span></span> <span data-ttu-id="30021-134">`ChainOne` 은 `ChainTwo`를 가져오지만 `ChainTwo` 가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-134">`ChainOne` imports `ChainTwo`, but `ChainTwo` does not exist.</span></span> <span data-ttu-id="30021-135">즉, `ChainOne` 이 거부되어 `AddIn` 도 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-135">This means that `ChainOne` is rejected, which causes `AddIn` to be rejected.</span></span>  
  
```  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 <span data-ttu-id="30021-136">다음은 이전 명령의 전체 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30021-136">The following shows the complete output of the previous command:</span></span>  
  
```  
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 <span data-ttu-id="30021-137">관심 있는 정보는 `[Exception]` 및 `[Unsuitable]` 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-137">The interesting information is contained in the `[Exception]` and `[Unsuitable]` results.</span></span> <span data-ttu-id="30021-138">`[Exception]` 결과는 파트가 거부된 이유에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-138">The `[Exception]` result provides information about why a part was rejected.</span></span> <span data-ttu-id="30021-139">`[Unsuitable]` 결과는 이외의 경우 일치하는 파트가 가져오기를 채우는 데 사용될 수 없는 이유를 나타냅니다. 이 경우 누락된 가져오기로 인해 해당 파트가 거부되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="30021-139">The `[Unsuitable]` result indicates why an otherwise-matching part could not be used to fill an import; in this case, because that part was itself rejected for missing imports.</span></span>  
  
<a name="analyzing_primary_causes"></a>   
## <a name="analyzing-primary-causes"></a><span data-ttu-id="30021-140">주 원인 분석</span><span class="sxs-lookup"><span data-stu-id="30021-140">Analyzing Primary Causes</span></span>  
 <span data-ttu-id="30021-141">여러 파트가 긴 종속성 체인으로 연결된 경우 아래쪽에 가까운 파트 관련 문제로 인해 전체 체인이 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-141">If several parts are linked in a long dependency chain, a problem involving a part near the bottom may cause the entire chain to be rejected.</span></span> <span data-ttu-id="30021-142">실패의 근본 원인이 항상 분명한 것은 아니므로 이들 문제를 진단하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-142">Diagnosing these problems can be difficult because the root cause of the failure is not always obvious.</span></span> <span data-ttu-id="30021-143">문제에 도움이 되도록 연속 거부의 근본 원인을 찾으려고 시도하는 `/causes` 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-143">To help with the problem, you can use the `/causes` action, which attempts to find the root cause of any cascading rejection.</span></span>  
  
 <span data-ttu-id="30021-144">이전 예제에서 `/causes` 작업을 사용하면 채워지지 않은 가져오기가 `ChainOne`거부의 근본 원인인 `AddIn`에 대한 정보만 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-144">Using the `/causes` action on the previous example would list only information for `ChainOne`, whose unfilled import is the root cause of the rejection of `AddIn`.</span></span> <span data-ttu-id="30021-145">`/causes` 작업은 일반 및 `/verbose` 옵션에서 둘 다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-145">The `/causes` action can be used in both normal and `/verbose` options.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30021-146">대부분 경우에 Mefx는 연속 실패의 근본 원인을 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-146">In most cases, Mefx will be able to diagnose the root cause of a cascading failure.</span></span> <span data-ttu-id="30021-147">그러나 파트가 컨테이너에 프로그래밍 방식으로 추가된 경우, 계층적 컨테이너가 관련된 경우 또는 사용자 지정 `ExportProvider` 구현이 관련된 경우 Mefx는 원인을 진단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-147">However, in cases where parts are added programmatically to a container, cases involving hierarchical containers, or cases involving custom `ExportProvider` implementations, Mefx will not be able to diagnose the cause.</span></span> <span data-ttu-id="30021-148">일반적으로 실패를 진단하기 어려우므로 가능하면 앞에서 설명된 경우를 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30021-148">In general, the previously described cases should be avoided where possible, as failures are generally difficult to diagnose.</span></span>  
  
<a name="white_lists"></a>   
## <a name="white-lists"></a><span data-ttu-id="30021-149">허용 목록</span><span class="sxs-lookup"><span data-stu-id="30021-149">White Lists</span></span>  
 <span data-ttu-id="30021-150">`/whitelist` 옵션을 사용하여 거부될 것으로 예상되는 파트를 나열하는 텍스트 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-150">The `/whitelist` option enables you to specify a text file that lists parts that are expected to be rejected.</span></span> <span data-ttu-id="30021-151">이에 따라 예기치 않은 거부에 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-151">Unexpected rejections will then be flagged.</span></span> <span data-ttu-id="30021-152">불완전한 라이브러리 또는 일부 종속성이 누락된 하위 라이브러리를 분석할 때 이 방법이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-152">This can be useful when you analyze an incomplete library, or a sub-library that is missing some dependencies.</span></span> <span data-ttu-id="30021-153">`/whitelist` 옵션을 `/rejected` 또는 `/causes` 작업에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30021-153">The `/whitelist` option can be applied to the `/rejected` or `/causes` actions.</span></span>  
  
 <span data-ttu-id="30021-154">"ClassLibrary1.ChainOne" 텍스트를 포함하는 test.txt 파일을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="30021-154">Consider a file named test.txt that contains the text "ClassLibrary1.ChainOne".</span></span> <span data-ttu-id="30021-155">이전 예제에서 `/rejected` 작업을 `/whitelist` 옵션과 함께 실행하면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="30021-155">If you run the `/rejected` action with the `/whitelist` option on the previous example, it will produce the following output:</span></span>  
  
```  
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
