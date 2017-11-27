---
title: "입력 대기 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d58c344e-9ee8-4ce2-b199-75b3fe45237f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4e9df410f5f8e6c95baa5ce5fdc9b2d339a190f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="wait-for-input-activity"></a><span data-ttu-id="b24a7-102">입력 대기 활동</span><span class="sxs-lookup"><span data-stu-id="b24a7-102">Wait For Input Activity</span></span>
<span data-ttu-id="b24a7-103">이 샘플은 워크플로에 명명된 책갈피를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-103">This sample demonstrates how to create named bookmarks in a workflow.</span></span> [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="b24a7-104">에서는 선언적 책갈피 작성을 위한 활동을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-104"> does not provide an activity for declarative bookmark creation.</span></span> <span data-ttu-id="b24a7-105">따라서 워크플로에 책갈피가 필요하면 책갈피를 만드는 사용자 지정 활동을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-105">Therefore, when you want to create a bookmark in your workflow, you must write a custom activity that creates it.</span></span> <span data-ttu-id="b24a7-106">이 샘플에 정의되어 있는 `WaitForInput` 활동에서 이러한 기능을 제공하므로 사용자가 워크플로 내에 선언적으로 책갈피를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-106">The `WaitForInput` activity defined in this sample provides this functionality, so that users can create bookmarks declaratively within a workflow.</span></span>  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="b24a7-107">이 샘플의 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b24a7-107">Projects in this sample</span></span>  
  
|<span data-ttu-id="b24a7-108">**프로젝트 이름**</span><span class="sxs-lookup"><span data-stu-id="b24a7-108">**Project Name**</span></span>|<span data-ttu-id="b24a7-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="b24a7-109">**Description**</span></span>|<span data-ttu-id="b24a7-110">**기본 파일**</span><span class="sxs-lookup"><span data-stu-id="b24a7-110">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="b24a7-111">WaitForInput</span><span class="sxs-lookup"><span data-stu-id="b24a7-111">WaitForInput</span></span>|<span data-ttu-id="b24a7-112">`WaitForInput` 활동과 이 활동의 디자이너가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-112">Contains `WaitForInput` activity and its designer</span></span>|<span data-ttu-id="b24a7-113">WaitForInput.cs</span><span class="sxs-lookup"><span data-stu-id="b24a7-113">WaitForInput.cs</span></span><br /><br /> <span data-ttu-id="b24a7-114">`WaitForInput` 활동 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-114">`WaitForInput` activity definition.</span></span>|  
|||<span data-ttu-id="b24a7-115">WaitForInputDesigner.xaml</span><span class="sxs-lookup"><span data-stu-id="b24a7-115">WaitForInputDesigner.xaml</span></span><br /><br /> <span data-ttu-id="b24a7-116">`WaitForInput` 활동에 대한 사용자 지정 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-116">Custom designer for the `WaitForInput` activity.</span></span>|  
|||<span data-ttu-id="b24a7-117">TypeToFirstGenericArgumentConverter.cs</span><span class="sxs-lookup"><span data-stu-id="b24a7-117">TypeToFirstGenericArgumentConverter.cs</span></span><br /><br /> <span data-ttu-id="b24a7-118">디자이너에서 활동의 제네릭 형식을 업데이트하는 데 사용되는 WPF 형식 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-118">WPF type converter used to update the generic type of the activity in the designer.</span></span>|  
|<span data-ttu-id="b24a7-119">WaitForInputTestClient</span><span class="sxs-lookup"><span data-stu-id="b24a7-119">WaitForInputTestClient</span></span>|<span data-ttu-id="b24a7-120">Workflow Designer를 통해 여러 가지 WaitForInput 활동을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-120">Sample client application that configures and runs a workflow using several WaitForInput activities using the workflow designer.</span></span>|<span data-ttu-id="b24a7-121">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="b24a7-121">Sequence1.xaml</span></span><br /><br /> <span data-ttu-id="b24a7-122">`WaitForInput` 활동을 사용하는 순차 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-122">A sequential workflow that uses the `WaitForInput` activity.</span></span>|  
|||<span data-ttu-id="b24a7-123">Program.cs</span><span class="sxs-lookup"><span data-stu-id="b24a7-123">Program.cs</span></span><br /><br /> <span data-ttu-id="b24a7-124">Sequence1.xaml에 정의된 워크플로의 인스턴스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-124">Runs an instance of the workflow defined in Sequence1.xaml.</span></span>|  
  
## <a name="waitforinput-activity"></a><span data-ttu-id="b24a7-125">WaitForInput 활동</span><span class="sxs-lookup"><span data-stu-id="b24a7-125">WaitForInput Activity</span></span>  
 <span data-ttu-id="b24a7-126">`WaitForInput` 활동은 워크플로에 명명된 책갈피를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-126">The `WaitForInput` activity creates a named bookmark in a workflow.</span></span> <span data-ttu-id="b24a7-127">이 책갈피는 신호를 기다리고 미리 구성된 형식의 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-127">The bookmark waits for a signal and receives data of its configured type.</span></span> <span data-ttu-id="b24a7-128">책갈피가 다시 시작되면 워크플로에 전달된 데이터를 `Result` 속성을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-128">After the bookmark is resumed the data passed into the workflow is available through the `Result` property.</span></span>  
  
 <span data-ttu-id="b24a7-129">`WaitForInput` 활동은 <xref:System.Activities.NativeActivity> 클래스를 통해서만 액세스할 수 있는 책갈피를 만들어야 하므로 <xref:System.Activities.NativeActivityContext> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-129">The `WaitForInput` activity derives from the <xref:System.Activities.NativeActivity> class because it must create bookmarks, which are only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
 <span data-ttu-id="b24a7-130">이 활동에는 디자이너를 바인딩하고, 업데이트 가능한 제네릭 인수 기능을 추가하고, 기본 제네릭 형식을 문자열로 설정하기 위한 세 가지 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-130">The activity has three attributes applied to it for binding a designer, adding the generic argument feature that can be updated, and setting the default generic type to string.</span></span> <span data-ttu-id="b24a7-131">이 활동에는 다음 표에 나열된 것과 같은 인수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-131">The activity also has the arguments  listed in the following table.</span></span>  
  
|<span data-ttu-id="b24a7-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="b24a7-132">**Name**</span></span>|<span data-ttu-id="b24a7-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="b24a7-133">**Type**</span></span>|<span data-ttu-id="b24a7-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="b24a7-134">**Description**</span></span>|  
|-|-|-|  
|<span data-ttu-id="b24a7-135">TResult</span><span class="sxs-lookup"><span data-stu-id="b24a7-135">TResult</span></span>|<span data-ttu-id="b24a7-136">제네릭 인수(TResult)</span><span class="sxs-lookup"><span data-stu-id="b24a7-136">Generic argument (TResult)</span></span>|<span data-ttu-id="b24a7-137">책갈피의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-137">Type of the bookmark.</span></span> <span data-ttu-id="b24a7-138">이는 책갈피를 다시 시작할 때 책갈피에 전달할 데이터의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-138">This is the type of the data to be passed to the bookmark when resumed.</span></span>|  
|<span data-ttu-id="b24a7-139">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="b24a7-139">BookmarkName</span></span>|<span data-ttu-id="b24a7-140">InArgument\<문자열 ></span><span class="sxs-lookup"><span data-stu-id="b24a7-140">InArgument\<string></span></span>|<span data-ttu-id="b24a7-141">책갈피의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-141">Name of the bookmark.</span></span>|  
|<span data-ttu-id="b24a7-142">결과</span><span class="sxs-lookup"><span data-stu-id="b24a7-142">Result</span></span>|<span data-ttu-id="b24a7-143">InArgument\<TResult ></span><span class="sxs-lookup"><span data-stu-id="b24a7-143">InArgument\<TResult></span></span>|<span data-ttu-id="b24a7-144">책갈피를 다시 시작할 때 활동에 전달할 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-144">Data passed to the activity when the bookmark is resumed.</span></span>|  
  
## <a name="waitforinput-activity-designer"></a><span data-ttu-id="b24a7-145">WaitForInput 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="b24a7-145">WaitForInput activity designer</span></span>  
 <span data-ttu-id="b24a7-146">`WaitForInput` 활동 디자이너는 WaitForInputDesigner.xaml 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-146">The `WaitForInput` activity designer is implemented in the WaitForInputDesigner.xaml file.</span></span> <span data-ttu-id="b24a7-147">`WaitForInput` 활동과 이 활동의 디자이너는 동일한 어셈블리에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-147">The `WaitForInput` activity and its designer are included in the same assembly.</span></span> <span data-ttu-id="b24a7-148">다음 그래픽에서는 어셈블리와 이름이 같은 범주 내 도구 상자의 `WaitForInput` 활동을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-148">The following graphic shows the `WaitForInput` activity in the toolbox within a category that has the same name as the assembly.</span></span>  
  
 <span data-ttu-id="b24a7-149">![WaitForInput 도구 상자 스크린 샷](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputtoolbox.jpg "WaitForInputToolbox")</span><span class="sxs-lookup"><span data-stu-id="b24a7-149">![WaitForInput toolbox screenshot](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputtoolbox.jpg "WaitForInputToolbox")</span></span>  
  
 <span data-ttu-id="b24a7-150">다음 그래픽에서는 `WaitForInput` 디자이너를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-150">The following graphic shows the `WaitForInput` designer.</span></span> <span data-ttu-id="b24a7-151">`WaitForInput`은 매우 기본적인 활동이므로 디자이너 화면에서 해당 인수를 모두 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-151">Because, the `WaitForInput` activity is very basic, the designer allows setting all its arguments directly in the designer surface.</span></span>  
  
 <span data-ttu-id="b24a7-152">![WaitForInput 활동 디자이너](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputdesigner.jpg "WaitForInputDesigner")</span><span class="sxs-lookup"><span data-stu-id="b24a7-152">![WaitForInput Activity Designer](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputdesigner.jpg "WaitForInputDesigner")</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b24a7-153">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b24a7-153">To use this sample</span></span>  
  
1.  <span data-ttu-id="b24a7-154">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 WaitForInput.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-154">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WaitForInput.sln file.</span></span>  
  
2.  <span data-ttu-id="b24a7-155">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-155">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b24a7-156">샘플을 디버깅하지 않고 시작하려면 Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-156">To start the sample without debugging, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b24a7-157">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-157">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b24a7-158">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b24a7-158">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b24a7-159">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b24a7-159">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b24a7-160">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b24a7-160">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\WaitForInput`  
  
## <a name="see-also"></a><span data-ttu-id="b24a7-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b24a7-161">See Also</span></span>
