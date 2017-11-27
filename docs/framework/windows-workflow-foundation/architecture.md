---
title: "Windows Workflow 아키텍처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c34b1af9c5fd93d57e94d959abe69f32572f7b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="windows-workflow-architecture"></a><span data-ttu-id="d8108-102">Windows Workflow 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d8108-102">Windows Workflow Architecture</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="d8108-103">에서는 대화형 장기 실행 응용 프로그램 개발을 위한 추상화 수준을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-103"> raises the abstraction level for developing interactive long-running applications.</span></span> <span data-ttu-id="d8108-104">작업 단위는 활동으로 캡슐화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-104">Units of work are encapsulated as activities.</span></span> <span data-ttu-id="d8108-105">또한 활동은 흐름 제어, 예외 처리, 오류 전파, 상태 데이터 지속성, 메모리에서 진행 중인 워크플로 로드 및 언로드, 추적, 트랜잭션 흐름 등과 같은 기능을 제공하는 환경에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-105">Activities run in an environment that provides facilities for flow control, exception handling, fault propagation, persistence of state data, loading and unloading of in-progress workflows from memory, tracking, and transaction flow.</span></span>  
  
## <a name="activity-architecture"></a><span data-ttu-id="d8108-106">활동 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d8108-106">Activity Architecture</span></span>  
 <span data-ttu-id="d8108-107">활동은 <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 또는 <xref:System.Activities.NativeActivity>에서 파생되는 CLR 형식 또는 <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> 또는 <xref:System.Activities.NativeActivity%601> 값을 반환하는 변형으로 개발됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-107">Activities are developed as CLR types that derive from either <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>, or their variants that return a value, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, or <xref:System.Activities.NativeActivity%601>.</span></span> <span data-ttu-id="d8108-108"><xref:System.Activities.Activity>에서 파생되는 개발 활동을 사용하면 기존 활동을 어셈블하여 워크플로 환경에서 실행되는 작업 단위를 신속하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-108">Developing activities that derive from <xref:System.Activities.Activity> allows the user to assemble pre-existing activities to quickly create units of work that execute in the workflow environment.</span></span> <span data-ttu-id="d8108-109">반면 <xref:System.Activities.CodeActivity>를 사용하면 주로 <xref:System.Activities.CodeActivityContext>를 통해 관리 코드에서 활동 인수에 액세스하는 데 필요한 실행 논리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-109"><xref:System.Activities.CodeActivity>, on the other hand, enables execution logic to be authored in managed code using <xref:System.Activities.CodeActivityContext> primarily for access to activity arguments.</span></span> <span data-ttu-id="d8108-110"><xref:System.Activities.AsyncCodeActivity>는 비동기 작업을 구현하는 데 사용할 수 있다는 점을 제외하고 <xref:System.Activities.CodeActivity>와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-110"><xref:System.Activities.AsyncCodeActivity> is similar to <xref:System.Activities.CodeActivity> except that it can be used to implement asynchronous tasks.</span></span> <span data-ttu-id="d8108-111"><xref:System.Activities.NativeActivity>에서 파생되는 활동을 개발하면 자식 예약, 책갈피 만들기, 비동기 작업 호출, 트랜잭션 등록 등과 같은 기능에 <xref:System.Activities.NativeActivityContext>를 통해 런타임에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-111">Developing activities that derive from <xref:System.Activities.NativeActivity> allows users to access the runtime through the <xref:System.Activities.NativeActivityContext> for functionality like scheduling children, creating bookmarks, invoking asynchronous work, registering transactions, and more.</span></span>  
  
 <span data-ttu-id="d8108-112"><xref:System.Activities.Activity>에서 파생되는 작성 활동은 선언적이며 XAML로 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-112">Authoring activities that derive from <xref:System.Activities.Activity> is declarative and these activities can be authored in XAML.</span></span> <span data-ttu-id="d8108-113">다음 예제에서는 실행 본문에 다른 활동을 사용하여 `Prompt`라는 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-113">In the following example, an activity called `Prompt` is created using other activities for the execution body.</span></span>  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a><span data-ttu-id="d8108-114">활동 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="d8108-114">Activity Context</span></span>  
 <span data-ttu-id="d8108-115"><xref:System.Activities.ActivityContext>는 워크플로 런타임에 대한 활동 작성자 인터페이스이며 풍부한 런타임 기능에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-115">The <xref:System.Activities.ActivityContext> is the activity author's interface to the workflow runtime and provides access to the runtime's wealth of features.</span></span> <span data-ttu-id="d8108-116">다음 예제에서는 실행 컨텍스트를 사용하여 책갈피를 만드는 데 사용하는 활동을 정의합니다. 책갈피는 활동 실행 중에 호스트에서 데이터를 활동에 전달하기 위해 다시 시작할 수 있는 연속 지점을 등록할 수 있는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-116">In the following example, an activity is defined that uses the execution context to create a bookmark (the mechanism that allows an activity to register a continuation point in its execution that can be resumed by a host passing data into the activity).</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a><span data-ttu-id="d8108-117">활동 수명 주기</span><span class="sxs-lookup"><span data-stu-id="d8108-117">Activity Life Cycle</span></span>  
 <span data-ttu-id="d8108-118">활동 인스턴스는 <xref:System.Activities.ActivityInstanceState.Executing> 상태에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-118">An instance of an activity starts out in the <xref:System.Activities.ActivityInstanceState.Executing> state.</span></span> <span data-ttu-id="d8108-119">예외가 발생하지 않는 한 실행 중인 모든 자식 활동과 보류 중인 다른 작업(예: <xref:System.Activities.Bookmark> 개체)을 마칠 때까지는 활동 인스턴스가 이 상태로 유지됩니다. 이러한 활동이 완료되면 <xref:System.Activities.ActivityInstanceState.Closed> 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-119">Unless exceptions are encountered, it remains in this state until all child activities are finished executing and any other pending work (<xref:System.Activities.Bookmark> objects, for instance) is completed, at which point it transitions to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="d8108-120">활동 인스턴스의 부모가 자식을 취소하도록 요청할 수 있습니다. 자식을 취소할 수 있으면 <xref:System.Activities.ActivityInstanceState.Canceled> 상태로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-120">The parent of an activity instance can request a child to cancel; if the child is able to be canceled it completes in the <xref:System.Activities.ActivityInstanceState.Canceled> state.</span></span> <span data-ttu-id="d8108-121">실행 중에 예외가 throw되면 런타임에 활동이 <xref:System.Activities.ActivityInstanceState.Faulted> 상태로 전환되고 예외가 활동의 부모 체인으로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-121">If an exception is thrown during execution, the runtime puts the activity into the <xref:System.Activities.ActivityInstanceState.Faulted> state and propagates the exception up the parent chain of activities.</span></span> <span data-ttu-id="d8108-122">다음은 활동의 세 가지 완료 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-122">Following are the three completion states of an activity:</span></span>  
  
-   <span data-ttu-id="d8108-123">**닫힌:** 활동에 작업을 완료 하 여 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-123">**Closed:** The activity has completed its work and exited.</span></span>  
  
-   <span data-ttu-id="d8108-124">**취소:** 활동에 정상적으로 중단 하 여 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-124">**Canceled:** The activity has gracefully abandoned its work and exited.</span></span> <span data-ttu-id="d8108-125">이 상태로 전환될 경우 작업이 명시적으로 롤백되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-125">Work is not explicitly rolled back when this state is entered.</span></span>  
  
-   <span data-ttu-id="d8108-126">**Faulted:** 활동에서 오류가 발생 하 고 해당 작업을 완료 하지 않고 종료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-126">**Faulted:** The activity has encountered an error and has exited without completing its work.</span></span>  
  
 <span data-ttu-id="d8108-127">활동이 지속되거나 언로드되는 경우에는 <xref:System.Activities.ActivityInstanceState.Executing> 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8108-127">Activities remain in the <xref:System.Activities.ActivityInstanceState.Executing> state when they are persisted or unloaded.</span></span>
