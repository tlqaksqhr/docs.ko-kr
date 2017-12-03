---
title: "순서도 워크플로"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5975cff014c1d74b9935a7cc95a6b2f25359db5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="flowchart-workflows"></a><span data-ttu-id="21602-102">순서도 워크플로</span><span class="sxs-lookup"><span data-stu-id="21602-102">Flowchart Workflows</span></span>
<span data-ttu-id="21602-103">순서도는 잘 알려진 프로그램 설계용 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="21602-103">A flowchart is a well-known paradigm for designing programs.</span></span> <span data-ttu-id="21602-104">Flowchart 활동은 일반적으로 순차적이 아닌 워크플로를 구현하는 데 사용하지만, `FlowDecision` 노드를 사용하지 않는 경우 순차적 워크플로에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21602-104">The Flowchart activity is typically used to implement non-sequential workflows, but can be used for sequential workflows if no `FlowDecision` nodes are used.</span></span>  
  
## <a name="flowchart-workflow-structure"></a><span data-ttu-id="21602-105">순서도 워크플로 구조</span><span class="sxs-lookup"><span data-stu-id="21602-105">Flowchart Workflow Structure</span></span>  
 <span data-ttu-id="21602-106">Flowchart 활동은 에서 실행되는 활동의 컬렉션을 포함하는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="21602-106">A Flowchart activity is an activity that contains a collection of activities to be executed.</span></span>  <span data-ttu-id="21602-107">순서도에는 변수 값에 따라 포함된 활동 사이의 실행을 연결하는 <xref:System.Activities.Statements.FlowDecision> 및 <xref:System.Activities.Statements.FlowSwitch%601> 같은 흐름 제어 요소도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21602-107">Flowcharts also contain flow control elements such as <xref:System.Activities.Statements.FlowDecision> and <xref:System.Activities.Statements.FlowSwitch%601> that direct execution between contained activities based on the values of variables.</span></span>  
  
## <a name="types-of-flow-nodes"></a><span data-ttu-id="21602-108">흐름 노드 형식</span><span class="sxs-lookup"><span data-stu-id="21602-108">Types of Flow Nodes</span></span>  
 <span data-ttu-id="21602-109">요소가 실행될 때 필요한 흐름 제어 형식에 따라 다양한 형식의 요소가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21602-109">Different types of elements are used depending on the type of flow control required when the element executes.</span></span> <span data-ttu-id="21602-110">다음과 같은 순서도 요소 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21602-110">Types of flowchart elements include:</span></span>  
  
-   <span data-ttu-id="21602-111">`FlowStep` - 순서도에서 실행의 한 단계를 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-111">`FlowStep` - Models one step of execution in the flowchart.</span></span>  
  
-   <span data-ttu-id="21602-112">`FlowDecision` - <xref:System.Activities.Statements.If>와 유사한 부울 조건을 기반으로 실행을 분기합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-112">`FlowDecision` - Branches execution based on a Boolean condition, similar to <xref:System.Activities.Statements.If>.</span></span>  
  
-   <span data-ttu-id="21602-113">`FlowSwitch` – <xref:System.Activities.Statements.Switch%601>과 유사한 전용 스위치를 기반으로 실행을 분기합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-113">`FlowSwitch` – Branches execution based on an exclusive switch, similar to <xref:System.Activities.Statements.Switch%601>.</span></span>  
  
 <span data-ttu-id="21602-114">각 링크에는 자식 활동을 실행하는 데 사용할 수 있는 `Action`을 정의하는 <xref:System.Activities.ActivityAction> 속성과 요소 실행이 완료되었을 때 실행할 현재 요소를 정의하는 하나 이상의 `Next` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21602-114">Each link has an `Action` property that defines a <xref:System.Activities.ActivityAction> that can be used to execute child activities, and one or more `Next` properties that define which element or elements to execute when the current element finishes execution.</span></span>  
  
### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a><span data-ttu-id="21602-115">FlowStep 노드로 기본 활동 시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="21602-115">Creating a Basic Activity Sequence with a FlowStep Node</span></span>  
 <span data-ttu-id="21602-116">두 활동이 차례로 실행되는 기본 시퀀스를 모델링하려면 `FlowStep` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-116">To model a basic sequence in which two activities execute in turn, the `FlowStep` element is used.</span></span> <span data-ttu-id="21602-117">다음 예에서는 두 `FlowStep` 요소를 사용하여 두 활동을 순서대로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-117">In the following example, two `FlowStep` elements are used to execute two activities in sequence.</span></span>  
  
```xml  
<Flowchart>  
  <FlowStep>      
  <Assign DisplayName="Get Name">  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:String">[result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:String">["User"]</InArgument>  
    </Assign.Value>  
  </Assign>  
    <FlowStep.Next>  
      <FlowStep>  
        <WriteLine Text="["Hello, " & result]"/>  
</FlowStep>  
    </FlowStep.Next>  
  </FlowStep>  
</Flowchart>  
```  
  
### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a><span data-ttu-id="21602-118">FlowDecision 노드로 조건부 순서도 만들기</span><span class="sxs-lookup"><span data-stu-id="21602-118">Creating a Conditional Flowchart with a FlowDecision Node</span></span>  
 <span data-ttu-id="21602-119">순서도 워크플로에서 조건부 흐름 노드를 모델링하려면(즉, 기존 순서도의 결정 기호 역할을 하는 링크를 만들려면) <xref:System.Activities.Statements.FlowDecision> 노드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-119">To model a conditional flow node in a flowchart workflow (that is, to create a link that functions as a traditional flowchart's decision symbol), a <xref:System.Activities.Statements.FlowDecision> node is used.</span></span> <span data-ttu-id="21602-120">노드의 <xref:System.Activities.Statements.FlowDecision.Condition%2A> 속성은 조건을 정의하는 식으로 설정되고, <xref:System.Activities.Statements.FlowDecision.True%2A> 및 <xref:System.Activities.Statements.FlowDecision.False%2A> 속성은 식이 <xref:System.Activities.Statements.FlowNode> 또는 `true`로 평가될 경우 실행할 `false` 인스턴스로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="21602-120">The <xref:System.Activities.Statements.FlowDecision.Condition%2A> property of the node is set to an expression that defines the condition, and the <xref:System.Activities.Statements.FlowDecision.True%2A> and <xref:System.Activities.Statements.FlowDecision.False%2A> properties are set to <xref:System.Activities.Statements.FlowNode> instances to be executed if the expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="21602-121">다음 예에서는 <xref:System.Activities.Statements.FlowDecision> 노드를 사용하는 순서도를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21602-121">The following example shows how to define a workflow that uses a <xref:System.Activities.Statements.FlowDecision> node.</span></span>  
  
```xml  
<Flowchart>  
  <FlowStep>  
    <Read Result="[s]"/>  
    <FlowStep.Next>  
      <FlowDecision>  
        <IsEmpty Input="[s]" />  
        <FlowDecision.True>  
    <FlowStep>  
            <Write Text="Empty"/>  
    </FlowStep>  
        </FlowDecision.True>  
        <FlowDecision.False>  
    <FlowStep>  
            <Write Text="Non-Empty"/>  
          </FlowStep>  
        </FlowDecision.False>  
      </FlowDecision>  
    </FlowStep.Next>  
  </FlowStep>  
</Flowchart>  
```  
  
### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a><span data-ttu-id="21602-122">FlowSwitch 노드로 전용 스위치 만들기</span><span class="sxs-lookup"><span data-stu-id="21602-122">Creating an Exclusive Switch with a FlowSwitch Node</span></span>  
 <span data-ttu-id="21602-123">일치하는 값에 따라 전용 경로 하나를 선택하는 순서도를 모델링하려면 <xref:System.Activities.Statements.FlowSwitch%601> 노드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-123">To model a flowchart in which one exclusive path is selected based on a matching value, the <xref:System.Activities.Statements.FlowSwitch%601> node is used.</span></span> <span data-ttu-id="21602-124"><xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 속성은 선택 항목과 비교할 값을 정의하는 <xref:System.Activities.Activity%601>의 형식 매개 변수를 사용하여 <xref:System.Object>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="21602-124">The <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> property is set to a <xref:System.Activities.Activity%601> with a type parameter of <xref:System.Object> that defines the value to match choices against.</span></span> <span data-ttu-id="21602-125"><xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 속성은 조건식과 비교할 키 및 <xref:System.Activities.Statements.FlowNode> 개체의 사전을 정의하며, 지정된 case가 조건식과 일치하는 경우 실행의 흐름을 정의하는 <xref:System.Activities.Statements.FlowNode> 개체 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-125">The <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> property defines a dictionary of keys and <xref:System.Activities.Statements.FlowNode> objects to match against the conditional expression, and a set of <xref:System.Activities.Statements.FlowNode> objects that define how execution should flow if the given case matches the conditional expression.</span></span> <span data-ttu-id="21602-126"><xref:System.Activities.Statements.FlowSwitch%601>도 조건식과 일치하는 case가 없을 때의 실행 흐름을 정의하는 <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21602-126">The <xref:System.Activities.Statements.FlowSwitch%601> also defines a <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> property that defines how execution should flow if no cases match the condition expression.</span></span> <span data-ttu-id="21602-127">다음 예에서는 <xref:System.Activities.Statements.FlowSwitch%601> 요소를 사용하는 워크플로를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21602-127">The following example demonstrates how to define a workflow that uses a <xref:System.Activities.Statements.FlowSwitch%601> element.</span></span>  
  
```xml  
<Flowchart>  
    <FlowSwitch>  
      <FlowStep x:Key="Red">  
        <WriteRed/>  
      </FlowStep>  
      <FlowStep x:Key="Blue">  
        <WriteBlue/>  
      </FlowStep>  
      <FlowStep x:Key="Green">  
        <WriteGreen/>  
      </FlowStep>  
    </FlowSwitch>  
</Flowchart>  
```
