---
title: 사용자 지정 추적
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 559557b34cf284b6dba5b300ef7270ec8d49ca84
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="custom-tracking"></a><span data-ttu-id="78e6a-102">사용자 지정 추적</span><span class="sxs-lookup"><span data-stu-id="78e6a-102">Custom Tracking</span></span>
<span data-ttu-id="78e6a-103">이 샘플에서는 사용자 지정 추적 참가자를 만들고 추적 데이터의 내용을 콘솔에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="78e6a-104">또한 사용자 정의 데이터로 채워진 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="78e6a-105">콘솔 기반 추적 참가자는 코드로 만든 추적 프로필 개체를 사용하여 워크플로에서 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="78e6a-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="78e6a-106">Sample Details</span></span>  
 <span data-ttu-id="78e6a-107">Windows WF (Workflow Foundation) 워크플로 인스턴스의 실행을 추적 하기 위한 추적 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="78e6a-108">추적 런타임은 워크플로 인스턴스를 구현하여 워크플로 수명 주기와 관련된 이벤트, 워크플로 활동의 이벤트 및 사용자 지정 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="78e6a-109">다음 표에서는 추적 인프라의 기본 구성 요소에 대해 자세히 설명합니다</span><span class="sxs-lookup"><span data-stu-id="78e6a-109">The following table details the primary components of the tracking infrastructure.</span></span>  
  
|<span data-ttu-id="78e6a-110">구성 요소</span><span class="sxs-lookup"><span data-stu-id="78e6a-110">Component</span></span>|<span data-ttu-id="78e6a-111">설명</span><span class="sxs-lookup"><span data-stu-id="78e6a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78e6a-112">추적 런타임</span><span class="sxs-lookup"><span data-stu-id="78e6a-112">Tracking runtime</span></span>|<span data-ttu-id="78e6a-113">추적 레코드를 내보낼 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-113">Provides the infrastructure to emit tracking records.</span></span>|  
|<span data-ttu-id="78e6a-114">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="78e6a-114">Tracking participants</span></span>|<span data-ttu-id="78e6a-115">추적 레코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-115">Consumes the tracking records.</span></span> [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="78e6a-116">에는 추적 레코드를 ETW(Windows용 이벤트 추적) 이벤트로 기록하는 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-116"> ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|  
|<span data-ttu-id="78e6a-117">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="78e6a-117">Tracking profile</span></span>|<span data-ttu-id="78e6a-118">추적 참가자가 워크플로 인스턴스에서 내보낸 추적 레코드의 하위 집합을 구독할 수 있도록 하는 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|  
  
 <span data-ttu-id="78e6a-119">다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-119">The following table details the tracking records that the workflow runtime emits.</span></span>  
  
|<span data-ttu-id="78e6a-120">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="78e6a-120">Tracking Record</span></span>|<span data-ttu-id="78e6a-121">설명</span><span class="sxs-lookup"><span data-stu-id="78e6a-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="78e6a-122">워크플로 인스턴스 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="78e6a-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="78e6a-123">워크플로 인스턴스의 수명 주기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="78e6a-124">예를 들어 워크플로가 시작되거나 완료되면 인스턴스 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|  
|<span data-ttu-id="78e6a-125">활동 상태 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="78e6a-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="78e6a-126">활동 실행에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-126">Details activity execution.</span></span> <span data-ttu-id="78e6a-127">이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 throw된 시점 등과 같은 워크플로 활동 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|  
|<span data-ttu-id="78e6a-128">책갈피 다시 시작 레코드</span><span class="sxs-lookup"><span data-stu-id="78e6a-128">Bookmark resumption record.</span></span>|<span data-ttu-id="78e6a-129">워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|  
|<span data-ttu-id="78e6a-130">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="78e6a-130">Custom Tracking Records.</span></span>|<span data-ttu-id="78e6a-131">워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|  
  
 <span data-ttu-id="78e6a-132">추적 참가자는 추적 프로필을 사용하여 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체의 하위 집합을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="78e6a-133">추적 프로필에는 특정 추적 레코드 형식을 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="78e6a-134">추적 프로필은 코드나 구성에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-134">Tracking profiles can be specified in code or in configuration.</span></span>  
  
### <a name="custom-tracking-participant"></a><span data-ttu-id="78e6a-135">사용자 지정 추적 참가자</span><span class="sxs-lookup"><span data-stu-id="78e6a-135">Custom Tracking Participant</span></span>  
 <span data-ttu-id="78e6a-136">추적 참가자 API를 사용하면 워크플로 런타임에서 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체를 처리하기 위한 사용자 지정 논리를 포함할 수 있는 사용자 제공 추적 참가자를 사용하여 추적 런타임을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>  
  
 <span data-ttu-id="78e6a-137">추적 참가자를 기록하려면 사용자가 <xref:System.Activities.Tracking.TrackingParticipant>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="78e6a-138">특히 사용자 지정 참가자는 <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="78e6a-139">이 메서드는 워크플로 런타임에서 <xref:System.Activities.Tracking.TrackingRecord>를 내보낼 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>  
  
```csharp  
public abstract class TrackingParticipant  
{  
    protected TrackingParticipant();  
  
    public virtual TrackingProfile TrackingProfile { get; set; }  
    public abstract void Track(TrackingRecord record, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="78e6a-140">전체 추적 참가자는 ConsoleTrackingParticipant.cs 파일에서 구현되며, 다음 코드 예제는 사용자 지정 추적 참가자를 위한 <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>  
  
```csharp  
protected override void Track(TrackingRecord record, TimeSpan timeout)  
{  
    ...             
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;  
    if (workflowInstanceRecord != null)  
    {  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " Workflow InstanceID: {0} Workflow instance state: {1}",  
            record.InstanceId, workflowInstanceRecord.State));  
    }  
  
    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;  
    if (activityStateRecord != null)  
    {  
        IDictionary<String, object> variables = activityStateRecord.Variables;  
        StringBuilder vars = new StringBuilder();  
  
        if (variables.Count > 0)  
        {  
            vars.AppendLine("\n\tVariables:");  
            foreach (KeyValuePair<string, object> variable in variables)  
            {     
                vars.AppendLine(String.Format(  
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));  
            }  
        }  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",  
                activityStateRecord.Activity.Name, activityStateRecord.State,  
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));  
    }  
  
    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;  
  
    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))  
    {  
        ...  
    }  
    Console.WriteLine();  
  
}  
```  
  
 <span data-ttu-id="78e6a-141">다음 코드 예제에서는 워크플로 호출자에 콘솔 참가자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-141">The following code example adds the console participant to the workflow invoker.</span></span>  
  
```csharp  
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()  
{  
    ...  
    // The tracking profile is set here, refer to Program.CS  
...  
}  
  
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());  
invoker.Extensions.Add(customTrackingParticipant);  
```  
  
### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="78e6a-142">사용자 지정 추적 레코드 내보내기</span><span class="sxs-lookup"><span data-stu-id="78e6a-142">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="78e6a-143">이 샘플에서는 사용자 지정 워크플로 활동에서 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 기능도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-143">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>  
  
-   <span data-ttu-id="78e6a-144"><xref:System.Activities.Tracking.CustomTrackingRecord> 개체가 만들어지고, 레코드와 함께 내보낼 사용자 정의 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-144">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>  
  
-   <span data-ttu-id="78e6a-145"><xref:System.Activities.Tracking.CustomTrackingRecord> 의 추적 메서드를 호출 하 여 내보내집니다는 <xref:System.Activities.ActivityContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>  
  
 <span data-ttu-id="78e6a-146">다음 예제에서는 사용자 지정 활동에서 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-146">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>  
  
```csharp  
// Create the Custom Tracking Record  
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")  
{  
    Data =   
    {  
        {"OrderId", 200},  
        {"OrderDate", "20 Aug 2001"}  
    }  
};  
  
// Emit custom tracking record  
context.Track(customRecord);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="78e6a-147">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="78e6a-147">To use this sample</span></span>  
  
1.  <span data-ttu-id="78e6a-148">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CustomTrackingSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-148">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomTrackingSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="78e6a-149">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="78e6a-150">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-150">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="78e6a-151">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-151">The samples may already be installed on your computer.</span></span> <span data-ttu-id="78e6a-152">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="78e6a-152">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="78e6a-153">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="78e6a-153">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="78e6a-154">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78e6a-154">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="78e6a-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78e6a-155">See Also</span></span>  
 [<span data-ttu-id="78e6a-156">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="78e6a-156">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
