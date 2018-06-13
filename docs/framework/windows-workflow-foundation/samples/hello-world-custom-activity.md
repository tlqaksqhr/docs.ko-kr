---
title: Hello World 사용자 지정 활동
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: 35ae5933515b3280b0d8d95157c8dd5f40f7b320
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515845"
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="7392d-102">Hello World 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="7392d-102">Hello World Custom Activity</span></span>
<span data-ttu-id="7392d-103">이 샘플의 Windows WF (Workflow Foundation), 단순한 사용자 지정 활동을 만드는 방법을 비롯 한 몇 가지 주요 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-103">This sample demonstrates several key features of Windows Workflow Foundation (WF), including how to create a simple custom activity.</span></span> <span data-ttu-id="7392d-104">이러한 기능에는 C#으로 사용자 지정 활동을 만들고 `in` 및 `out` 인수(<xref:System.Activities.InArgument> 및 <xref:System.Activities.OutArgument>)를 사용하는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7392d-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7392d-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7392d-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7392d-107">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="7392d-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7392d-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="7392d-109">코드로 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="7392d-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="7392d-110">이 샘플에서는 C# 코드를 사용하여 두 개의 사용자 지정 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="7392d-111">두 사용자 지정 활동 모두 <xref:System.Activities.Activity%601>에서 직접 또는 간접적으로 상속하여 단일 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="7392d-112">비네제릭 <xref:System.Activities.Activity> 클래스에서 상속하지 않고 제네릭 반환 값을 사용하면 <xref:System.Activities.Statements.Assign>과 같은 일부 활동이 구성된 활동의 일부로 사용될 때 반환 값에 액세스할 수 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="7392d-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="7392d-113">AppendString</span></span>  
 <span data-ttu-id="7392d-114">이 활동은 <xref:System.Activities.Activity%601>에서 상속하고, 두 문자열을 연결하는 <xref:System.Activities.Statements.Assign> 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="7392d-115">PrependString</span><span class="sxs-lookup"><span data-stu-id="7392d-115">Prepend String</span></span>  
 <span data-ttu-id="7392d-116">이 활동은 <xref:System.Activities.CodeActivity%601>에서 직접 상속하며, 기존 활동으로 구성되지 않고 코드로 구현된 논리를 사용하는 `AppendString` 활동과 비슷한 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="7392d-117">이 프로젝트에 포함되어 있는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="7392d-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="7392d-118">AppendString.cs</span></span>  
 <span data-ttu-id="7392d-119">문자열을 추가하는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="7392d-120">문자열 가져와서 하 고 정렬 하는 리터럴 텍스트 문자열 "says hello world" 양식에 전체 메시지를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="7392d-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="7392d-121">PrependString.cs</span></span>  
 <span data-ttu-id="7392d-122">이 활동은 미리 정의된 문자열을 입력 문자열의 접두사로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="7392d-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="7392d-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="7392d-124">`AppendString` 및 `PrependString` 사용자 지정 활동을 사용하는 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="7392d-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="7392d-125">Program.cs</span></span>  
 <span data-ttu-id="7392d-126">워크플로를 실행하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7392d-127">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7392d-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="7392d-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 HelloWorld.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7392d-129">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7392d-130">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7392d-130">To run the solution, press F5.</span></span>