---
title: "InvokePowerShell 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3ef8b539e490911e5454fe87db483508cc8a5d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="33164-102">InvokePowerShell 활동 사용</span><span class="sxs-lookup"><span data-stu-id="33164-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="33164-103">InvokePowerShell 샘플에서는 `InvokePowerShell` 활동을 사용하여 Windows PowerShell 명령을 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33164-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="33164-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="33164-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="33164-105">Windows PowerShell 명령을 단순화한 새로운 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="33164-106">Windows PowerShell 출력 파이프라인에서 값을 검색한 다음 워크플로 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="33164-107">데이터를 Windows PowerShell에 명령을 실행하기 위한 입력 파이프라인으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33164-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="33164-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="33164-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33164-110">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="33164-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33164-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="33164-112">토론</span><span class="sxs-lookup"><span data-stu-id="33164-112">Discussion</span></span>  
 <span data-ttu-id="33164-113">이 샘플에는 다음 세 개의 프로젝트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="33164-114">프로젝트 이름</span><span class="sxs-lookup"><span data-stu-id="33164-114">Project Name</span></span>|<span data-ttu-id="33164-115">설명</span><span class="sxs-lookup"><span data-stu-id="33164-115">Description</span></span>|<span data-ttu-id="33164-116">기본 파일</span><span class="sxs-lookup"><span data-stu-id="33164-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="33164-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="33164-117">CodedClient</span></span>|<span data-ttu-id="33164-118">PowerShell 활동을 사용하는 샘플 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="33164-119">-   **Program.cs**: InvokePowerShell 활동을 호출 하는 시퀀스 기반 워크플로 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33164-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="33164-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="33164-120">DesignerClient</span></span>|<span data-ttu-id="33164-121">`InvokePowerShell` 사용자 지정 활동 및 기타 사용자 지정 활동이 포함된 사용자 지정 활동 집합과 이를 사용하는 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="33164-122">활동:</span><span class="sxs-lookup"><span data-stu-id="33164-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="33164-123">**PrintCollection.cs**: 콘솔에 컬렉션의 모든 항목을 출력 하는 도우미 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="33164-124">**ReadLine.cs**: 콘솔에서 입력을 읽기 위한 도우미 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="33164-125">파일 시스템:</span><span class="sxs-lookup"><span data-stu-id="33164-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="33164-126">**Copy.xaml**: 파일을 복사 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="33164-127">**CreateFile.xaml**: 파일을 만드는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="33164-128">**DeleteFile.xaml**: 파일을 삭제 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="33164-129">**MakeDir.xaml**: 디렉터리를 만드는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="33164-130">**Move.xaml**: 파일을 이동 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="33164-131">**ReadFile.xaml**: 파일을 읽고 해당 내용을 반환 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="33164-132">**TestPath.xaml**: 경로가 있는지 테스트 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="33164-133">프로세스:</span><span class="sxs-lookup"><span data-stu-id="33164-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="33164-134">**GetProcess.xaml**: 실행 중인 프로세스 목록을 가져오는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="33164-135">**StopProcess.xaml**: 특정 프로세스를 중지 하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="33164-136">**Program.cs**: Sequence1 워크플로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="33164-137">**Sequence1.xaml**: 시퀀스 기반 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="33164-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="33164-138">PowerShell</span></span>|<span data-ttu-id="33164-139">`InvokePowerShell` 활동 및 이 활동과 연결된 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="33164-140">활동 파일</span><span class="sxs-lookup"><span data-stu-id="33164-140">Activity Files</span></span><br /><br /> <span data-ttu-id="33164-141">-   **ExecutePowerShell.cs**: 활동의 기본 실행 논리입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="33164-142">-   **InvokePowerShell.cs**: 제네릭 (반환 값) 버전과 비 제네릭 (비 반환 값) 버전을 포함 하는 주요 실행 논리 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="33164-143">이는 활동의 공용 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="33164-144">-   **NoPersistZone.cs**:이 활동 모든 자식 활동이 지속 하지 않도록 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="33164-145">이 클래스는 `InvokePowerShell` 활동 구현 내에서 실행 도중에 활동이 지속되지 않게 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="33164-146">디자이너 파일:</span><span class="sxs-lookup"><span data-stu-id="33164-146">Designer files:</span></span><br /><br /> <span data-ttu-id="33164-147">1.  **ArgumentDictionaryEditor.cs**: 사용자의 인수를 편집할 수 있는 Windows 대화 상자는 `InvokePowerShell` 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="33164-148">2.  **GenericInvokePowerShellDesigner.xaml** 및 **GenericInvokePowerShellDesigner.xaml.cs**: 제네릭의 모양을 정의 `InvokePowerShell` 활동에 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="33164-149">3.  **InvokePowerShellDesigner.xaml** 및 **InvokePowerShellDesigner.cs**: 제네릭이 아닌의 모양을 정의 `InvokePowerShell` 활동에 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="33164-150">클라이언트 프로젝트의 사용 방법을 이해하면 PowerShell 활동의 내부 기능을 쉽게 이해할 수 있기 때문에 클라이언트 프로젝트에 대해 먼저 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="33164-151">이 샘플의 사용법</span><span class="sxs-lookup"><span data-stu-id="33164-151">Using This Sample</span></span>  
 <span data-ttu-id="33164-152">다음 단원에서는 샘플에 있는 세 개의 프로젝트를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="33164-153">코딩된 클라이언트 프로젝트 사용법</span><span class="sxs-lookup"><span data-stu-id="33164-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="33164-154">샘플 클라이언트는 `InvokePowerShell` 활동의 여러 사용 방법 예제가 포함된 시퀀스 활동을 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33164-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="33164-155">첫 번째 호출에서는 메모장을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="33164-156">두 번째 호출에서는 로컬 컴퓨터에서 실행 중인 프로세스 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33164-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="33164-157">`Output`은 명령의 출력을 저장하는 데 사용되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="33164-158">다음 호출에서는 PowerShell 호출의 각 출력에 대해 후처리 단계를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33164-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="33164-159">`InitializationAction`은 각 프로세스에 대한 문자열 표현을 출력하는 함수로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="33164-160">이 문자열의 컬렉션은 `Output` 활동에 의해 `InvokePowerShell<string>` 변수에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="33164-161">그 다음 `InvokePowerShell` 호출에서는 데이터를 활동에 전달하고 출력과 오류를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33164-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="33164-162">디자이너 클라이언트 프로젝트 사용법</span><span class="sxs-lookup"><span data-stu-id="33164-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="33164-163">디자이너 클라이언트 프로젝트는 사용자 지정 활동 집합으로 구성되며, 그 중 대부분의 활동이 `InvokePowerShell` 활동을 포함하여 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="33164-164">대부분의 활동은 비제네릭 버전의 `InvokePowerShell` 활동을 호출하며 반환 값을 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="33164-165">그 외 활동은 제네릭 버전의 `InvokePowerShell` 활동을 사용하고 `InitializationAction` 인수를 사용하여 결과에 대한 후처리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="33164-166">PowerShell 프로젝트 사용법</span><span class="sxs-lookup"><span data-stu-id="33164-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="33164-167">활동의 기본 동작은 `ExecutePowerShell` 클래스에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="33164-168">PowerShell 명령을 실행할 때 기본 워크플로 스레드가 차단되지 않아야 하기 때문에 <xref:System.Activities.AsyncCodeActivity> 클래스에서 상속하여 비동기 활동이 되도록 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33164-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="33164-169">워크플로 런타임에서 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 메서드를 호출하여 활동을 실행하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="33164-170">PowerShell API를 호출하여 PowerShell 파이프라인을 만드는 작업으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="33164-171">그런 다음 PowerShell 명령을 만들고 매개 변수 및 변수로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="33164-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="33164-172">이때 전송된 입력도 파이프라인으로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="33164-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="33164-173">마지막으로 파이프라인이 `PipelineInvokerAsyncResult` 개체에 래핑되고 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="33164-174">`PipelineInvokerAsyncResult` 개체는 수신기를 등록하고 파이프라인을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="33164-175">실행이 완료되면 출력과 오류가 동일한 `PipelineInvokerAsyncResult` 개체 내에 저장되고 원래 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>에 전달된 콜백 메서드를 호출하여 컨트롤이 워크플로 런타임에 다시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="33164-176">메서드 실행이 끝나면 워크플로 런타임이 활동의 <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="33164-177">`InvokePowerShell` 클래스는 `ExecutePowerShellCommand` 클래스를 래핑하고 두 버전의 활동, 즉 제네릭 버전과 비제네릭 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33164-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="33164-178">제네릭 버전은 개별 결과를 제네릭 형식으로 변환하는 반면 비제네릭 버전은 PowerShell 실행 출력을 직접 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="33164-179">제네릭 버전의 활동은 `ExecutePowerShellCommand`를 호출하고 결과에 대한 후처리 작업을 수행하는 순차 워크플로로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="33164-180">결과 컬렉션의 각 요소에 대한 후처리 단계가 설정되어 있으면 `InitializationAction`을 호출하고,</span><span class="sxs-lookup"><span data-stu-id="33164-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="33164-181">그렇지 않으면 간단한 캐스팅을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="33164-182">두 `InvokePowerShell` 활동(제네릭 및 비제네릭 버전) 각각에 대해 디자이너를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="33164-183">InvokePowerShellDesigner.xaml 및 이 파일과 연결된 .cs 파일은 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]에서 비제네릭 버전의 `InvokePowerShell` 활동에 대한 모양을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="33164-184">InvokePowerShellDesigner.xaml 내부에서 <xref:System.Windows.Controls.DockPanel>은 그래픽 인터페이스를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33164-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="33164-185">텍스트 상자의 `Text` 속성은 활동의 `CommandText` 속성을 디자이너에 대한 입력 값과 동일하게 만드는 양방향 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="33164-186">GenericInvokePowerShellDesigner.xaml 및 이 파일과 연결된 .cs 파일은 제네릭 `InvokePowerShell` 활동의 그래픽 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="33164-187">디자이너는 사용자가 `InitializationAction`을 설정할 수 있게 하므로 조금 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="33164-188"><xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 자식 활동을 `InvokePowerShell` 디자이너 화면으로 끌어서 놓을 수 있게 한다는 점이 주요 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="33164-189">디자이너 사용자 지정은 디자인 캔버스에서 활동의 모양을 정의하는 .xaml 파일로 끝나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="33164-190">활동의 매개 변수를 표시하는 데 사용되는 대화 상자도 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="33164-191">이 매개 변수와 PowerShell 변수는 PowerShell 명령의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33164-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="33164-192">작업으로 노출 <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="33164-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="33164-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml 및 PropertyEditorResources.cs는 이러한 형식을 편집할 수 있는 대화 상자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="33164-194">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="33164-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="33164-195">이 샘플을 실행하려면 Windows PowerShell을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="33164-196">Windows PowerShell이이 위치에서 설치할 수 있습니다: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383)합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-196">Windows PowerShell can be installed from this location: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="33164-197">코딩된 클라이언트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="33164-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="33164-198">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 PowerShell.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33164-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="33164-199">솔루션을 마우스 오른쪽 단추로 클릭하고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="33164-200">마우스 오른쪽 단추로 클릭는 **CodedClient** 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="33164-201">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="33164-202">디자이너 클라이언트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="33164-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="33164-203">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 PowerShell.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="33164-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="33164-204">솔루션을 마우스 오른쪽 단추로 클릭하고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="33164-205">마우스 오른쪽 단추로 클릭는 **빌드됩니다** 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="33164-206">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="33164-207">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="33164-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="33164-208">다른 프로젝트의 `InvokePowerShell` 활동 어셈블리 또는 프로젝트를 참조할 때 빌드 오류가 발생하는 경우 새 프로젝트의 .csproj 파일에서 `<SpecificVersion>True</SpecificVersion>`을 참조하는 줄 아래에 `InvokePowerShell` 요소를 수동으로 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="33164-209">Windows PowerShell 설치 되지 않은 경우 다음과 같은 오류 메시지가 추가 되는 즉시 Visual Studio에서 표시 됩니다는 `InvokePowerShell` 활동을 워크플로에:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="33164-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="33164-210">Windows PowerShell 2.0에서 `$input.MoveNext()`를 프로그래밍 방식으로 호출하면 실패하며 `$input.MoveNext()`를 사용하는 스크립트에서 의도하지 않은 오류 및 결과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="33164-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="33164-211">이 문제를 해결하려면 배열을 반복할 때 `foreach`를 호출하는 대신 PowerShell 동사 `MoveNext()`를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="33164-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33164-212">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="33164-213">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="33164-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33164-214">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="33164-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33164-215">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33164-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`