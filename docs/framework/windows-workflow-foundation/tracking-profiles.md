---
title: 추적 프로필
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 4f70964ea7e2456f82aeac4bfb9aedfdb239d58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519986"
---
# <a name="tracking-profiles"></a><span data-ttu-id="d10e6-102">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d10e6-102">Tracking Profiles</span></span>
<span data-ttu-id="d10e6-103">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>  
  
## <a name="tracking-profiles"></a><span data-ttu-id="d10e6-104">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d10e6-104">Tracking Profiles</span></span>  
 <span data-ttu-id="d10e6-105">워크플로 인스턴스에 내보낼 추적 정보를 지정하는 데 사용되는 추적 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="d10e6-106">프로필을 지정하지 않으면 모든 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="d10e6-107">프로필을 지정하면 프로필에 지정된 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="d10e6-108">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="d10e6-109">이와 반대로 이후에 세부 실행 흐름을 다시 작성할 수 있을 정도로 상세한 결과 이벤트를 포함하는 아주 자세한 프로필을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="d10e6-110">추적 프로필은 표준 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 구성 파일 내에 XML 요소로 표시되거나 코드로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-110">Tracking profiles manifest themselves as XML elements within a standard [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration file or specified in code.</span></span> <span data-ttu-id="d10e6-111">다음 예제에서는 추적 참가자가 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 및 `Started` 워크플로 이벤트를 구독할 수 있도록 하는 구성 파일의 `Completed` 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <tracking>    
      <trackingProfile name="Sample Tracking Profile">  
        <workflow activityDefinitionId="*">  
          <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                <state name="Started"/>  
                <state name="Completed"/>  
              </states>  
            </workflowInstanceQuery>  
          </workflowInstanceQueries>  
        </workflow>  
      </trackingProfile>          
    </profiles>  
  </tracking>  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d10e6-112">다음 예제에서는 코드를 사용하여 만든 동일한 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-112">The following example shows the equivalent tracking profile created using code.</span></span>  
  
```csharp  
TrackingProfile profile = new TrackingProfile()  
{  
    Name = "CustomTrackingProfile",  
    Queries =   
    {  
        new WorkflowInstanceQuery()  
        {  
            // Limit workflow instance tracking records for started and  
            // completed workflow states.  
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },  
        }  
    }  
};  
```  
  
 <span data-ttu-id="d10e6-113">추적 레코드는 <xref:System.Activities.Tracking.ImplementationVisibility> 특성을 사용하여 추적 프로필의 표시 모드를 통해 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="d10e6-114">복합 활동은 구현을 구성하는 다른 활동을 포함하는 최상위 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="d10e6-115">표시 모드는 구현을 구성하는 활동을 추적할지 여부를 지정하기 위하여 워크플로 활동 내의 복합 활동에서 내보내는 추적 레코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span>  <span data-ttu-id="d10e6-116">표시 모드는 추적 프로필 수준에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="d10e6-117">워크플로의 개별 활동에 대한 추적 레코드 필터링은 추적 프로필 내에서 쿼리에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="d10e6-118">자세한 내용은 참조는 **추적 프로필 쿼리 형식** 이 문서의 섹션.</span><span class="sxs-lookup"><span data-stu-id="d10e6-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>  
  
 <span data-ttu-id="d10e6-119">추적 프로필의 `implementationVisibility` 특성은 두 가지 표시 모드(`RootScope` 및 `All`)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="d10e6-120">복합 활동이 워크플로의 루트가 아닌 경우 `RootScope` 모드를 사용하면 활동의 구현을 구성하는 활동에 대한 추적 레코드가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span>  <span data-ttu-id="d10e6-121">즉, 다른 활동을 사용하여 구현되는 활동이 워크플로에 추가되고 `implementationVisibility`가 RootScope로 설정된 경우에는 해당 복합 활동의 최상위 활동만 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="d10e6-122">활동이 워크플로의 루트인 경우 활동 구현이 워크플로 자체이고 구현 단계를 구성하는 활동에 대한 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="d10e6-123">모두 모드에서는 루트 활동과 모든 복합 활동에 대해 모든 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>  
  
 <span data-ttu-id="d10e6-124">예를 들어 *MyActivity* 는 구현할 수 있는 두 개의 활동을 포함 하는 복합 활동 *Activity1* 및 *Activity2*합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span>  <span data-ttu-id="d10e6-125">이 작업을 워크플로에 추가 된 추적 프로필과 추적을 사용 하도록 시점과 `implementationVisibility` 로 설정 `RootScope`에 대해서만 추적 레코드가 내보내집니다 *MyActivity*합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span>  <span data-ttu-id="d10e6-126">그러나 활동에 대 한 레코드가 내보내지지 않습니다 *Activity1* 및 *Activity2*합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="d10e6-127">그러나 경우는 `implementationVisisbility` 로 설정 된 추적 프로필에 대 한 특성 `All`, 뿐만 아니라에 대 한 추적 레코드가 내보내집니다 다음 *MyActivity*, 있지만 대해서도 *Activity1* 및  *Activity2*합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-127">However, if the `implementationVisisbility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="d10e6-128">`implementationVisibility` 플래그가 적용되는 추적 레코드 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>  
  
-   <span data-ttu-id="d10e6-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="d10e6-129">ActivityStateRecord</span></span>  
  
-   <span data-ttu-id="d10e6-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="d10e6-130">FaultPropagationRecord</span></span>  
  
-   <span data-ttu-id="d10e6-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="d10e6-131">CancelRequestedRecord</span></span>  
  
-   <span data-ttu-id="d10e6-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="d10e6-132">ActivityScheduledRecord</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d10e6-133">활동 구현에서 내보내는 CustomTrackingRecords는 implementationVisibility 설정에 의해 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>  
  
 <span data-ttu-id="d10e6-134">`implementationVisibility` 기능은 코드의 추적 프로필에서 다음과 같이 <xref:System.Activities.Tracking.ImplementationVisibility.RootScope>로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>  
  
```  
TrackingProfile sampleTrackingProfile = new TrackingProfile()  
{  
    Name = "Sample Tracking Profile",  
    ImplementationVisibility = ImplementationVisibility.RootScope  
};  
```  
  
 <span data-ttu-id="d10e6-135">`implementationVisibility` 기능은 구성 파일의 추적 프로필에서 다음과 같이 <xref:System.Activities.Tracking.ImplementationVisibility.All>로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>  
  
```xml  
<tracking>  
      <profiles>  
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">  
          <workflow activityDefinitionId="*">  
...  
         </workflow>  
        </trackingProfile>  
      </profiles>  
</tracking>  
```  
  
 <span data-ttu-id="d10e6-136">추적 프로필의 `ImplementationVisibility` 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="d10e6-137">기본적으로 이 값은 `RootScope`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="d10e6-138">또한 이 특성 값은 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-138">The values for this attribute are also case-sensitive.</span></span>  
  
### <a name="tracking-profile-query-types"></a><span data-ttu-id="d10e6-139">추적 프로필 쿼리 형식</span><span class="sxs-lookup"><span data-stu-id="d10e6-139">Tracking Profile Query Types</span></span>  
 <span data-ttu-id="d10e6-140">추적 프로필은 특정 추적 레코드에 대한 워크플로 런타임을 쿼리할 수 있는 추적 레코드에 대한 선언적 구독으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="d10e6-141"><xref:System.Activities.Tracking.TrackingRecord> 개체의 다양한 클래스를 구독할 수 있는 여러 쿼리 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="d10e6-142">추적 프로필은 구성이나 코드를 통해 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="d10e6-143">가장 일반적인 쿼리 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-143">Here are the most common query types:</span></span>  
  
-   <span data-ttu-id="d10e6-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - 앞에서 설명한 `Started` 및 `Completed`와 같은 워크플로 인스턴스 수명 주기 변경 내용을 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="d10e6-145"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
     <span data-ttu-id="d10e6-146">구독 가능한 상태는 <xref:System.Activities.Tracking.WorkflowInstanceStates> 클래스에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>  
  
     <span data-ttu-id="d10e6-147">다음 예제에서는 `Started`를 사용하여 <xref:System.Activities.Tracking.WorkflowInstanceQuery> 인스턴스에 대한 워크플로 인스턴스 수준 추적 레코드를 구독하는 데 사용되는 구성 또는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <workflowInstanceQueries>  
        <workflowInstanceQuery>  
          <states>  
            <state name="Started"/>  
          </states>  
        </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new WorkflowInstanceQuery()  
            {  
                States = { WorkflowInstanceStates.Started}                                                                     
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="d10e6-148"><xref:System.Activities.Tracking.ActivityStateQuery> - 워크플로 인스턴스를 구성하는 활동에 대한 수명 주기 변경 내용을 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="d10e6-149">예를 들어 다음 워크플로 인스턴스 내에서 "전자 메일 보내기" 활동이 완료 될 때마다 추적 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="d10e6-150">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.ActivityStateRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="d10e6-151">구독하기 위해 사용 가능한 상태는 <xref:System.Activities.Tracking.ActivityStates>에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>  
  
     <span data-ttu-id="d10e6-152">다음 예제에서는 <xref:System.Activities.Tracking.ActivityStateQuery> 활동에 대해 `SendEmailActivity`를 사용하는 활동 상태 추적 레코드를 구독하는 데 사용되는 구성과 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>  
  
    ```xml  
    <activityStateQueries>  
      <activityStateQuery activityName="SendEmailActivity">  
        <states>  
          <state name="Closed"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new ActivityStateQuery()  
            {                              
                ActivityName = "SendEmailActivity",  
                States = { ActivityStates.Closed }  
            }  
        }  
    };  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d10e6-153">여러 activityStateQuery 요소에 동일한 이름을 사용할 경우 마지막 요소의 상태만 추적 프로필에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>  
  
-   <span data-ttu-id="d10e6-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - 이 쿼리를 사용하여 부모 활동에 의해 실행이 예약된 활동을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d10e6-155">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.ActivityScheduledRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>  
  
     <span data-ttu-id="d10e6-156">다음 예제에서는 `SendEmailActivity`를 사용하여 예약된 <xref:System.Activities.Tracking.ActivityScheduledQuery> 자식 활동 관련 레코드를 구독하는 데 사용되는 구성과 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <activityScheduledQueries>  
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
     </activityScheduledQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new ActivityScheduledQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="d10e6-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - 활동에서 발생하는 오류 처리를 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d10e6-158">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.FaultPropagationRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>  
  
     <span data-ttu-id="d10e6-159">다음 예제에서는 <xref:System.Activities.Tracking.FaultPropagationQuery>를 사용하여 오류 전파 관련 레코드를 구독하는 데 사용되는 구성과 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <faultPropagationQueries>  
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />  
    </faultPropagationQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new FaultPropagationQuery()  
            {  
                FaultSourceActivityName = "SendEmailActivity",  
                FaultHandlerActivityName = "NotificationsFaultHandler"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="d10e6-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - 부모 활동에 의한 자식 활동 취소 요청을 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d10e6-161">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.CancelRequestedRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>  
  
     <span data-ttu-id="d10e6-162">구성 및 레코드를 구독 하는 데 사용 되는 코드를 사용 하 여 활동 취소 관련 <xref:System.Activities.Tracking.CancelRequestedQuery> 다음 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <cancelRequestedQueries>  
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
    </cancelRequestedQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CancelRequestedQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="d10e6-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - 코드 활동에서 정의한 이벤트를 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="d10e6-164">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>  
  
     <span data-ttu-id="d10e6-165">다음 예제에서는 <xref:System.Activities.Tracking.CustomTrackingQuery>를 사용하여 사용자 지정 추적 레코드 관련 레코드를 구독하는 데 사용되는 구성과 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <customTrackingQueries>  
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />  
    </customTrackingQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CustomTrackingQuery()   
            {  
                Name = "EmailAddress",  
                ActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="d10e6-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - 워크플로 인스턴스 내의 책갈피 다시 시작을 추적하려면 이 쿼리 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d10e6-167">이 쿼리는 <xref:System.Activities.Tracking.TrackingParticipant>가 <xref:System.Activities.Tracking.BookmarkResumptionRecord> 개체를 구독하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>  
  
     <span data-ttu-id="d10e6-168">다음 예제에서는 <xref:System.Activities.Tracking.BookmarkResumptionQuery>를 사용하여 책갈피 다시 시작 관련 레코드를 구독하는 데 사용되는 구성과 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <bookmarkResumptionQueries>  
      <bookmarkResumptionQuery name="SentEmailBookmark" />  
    </bookmarkResumptionQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new BookmarkResumptionQuery()  
            {  
                Name = "sentEmailBookmark"  
            }  
        }  
    };  
    ```  
  
### <a name="annotations"></a><span data-ttu-id="d10e6-169">주석</span><span class="sxs-lookup"><span data-stu-id="d10e6-169">Annotations</span></span>  
 <span data-ttu-id="d10e6-170">주석을 사용하여 빌드 시간 후에 구성될 수 있는 값으로 추적 레코드에 임의 태그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="d10e6-171">예를 들어 "Mail Server" 이라는 태그가 지정 되어야 하는 여러 워크플로에 걸쳐 여러 추적 레코드를 할 수 = = "Mail Server1"입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="d10e6-172">이렇게 하면 나중에 추적 레코드를 쿼리할 때 이 태그를 사용하여 모든 레코드를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
 <span data-ttu-id="d10e6-173">이렇게 하려면 다음 예제와 같이 추적 쿼리에 주석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="d10e6-174">추적 프로필을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="d10e6-174">How to Create a Tracking Profile</span></span>  
 <span data-ttu-id="d10e6-175">추적 쿼리 요소를 사용하면 XML 구성 파일 또는 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 코드를 통해 추적 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]code.</span></span>  <span data-ttu-id="d10e6-176">다음은 구성 파일을 사용하여 만든 추적 프로필의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-176">Here is an example of a tracking profile created using a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>  
    <profiles>  
      <trackingProfile name="Sample Tracking Profile ">  
        <workflow activityDefinitionId="*">  
          <!--Specify the tracking profile query elements to subscribe for tracking records-->  
        </workflow>  
      </trackingProfile>  
    </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
> [!WARNING]
>  <span data-ttu-id="d10e6-177">워크플로 서비스 호스트를 사용하는 WF의 경우 일반적으로 구성 파일을 사용하여 추적 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="d10e6-178">추적 프로필 및 추적 쿼리 API를 사용하여 코드를 통해 추적 프로필을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>  
  
 <span data-ttu-id="d10e6-179">XML 구성 파일로 구성된 프로필은 동작 확장을 사용하여 추적 참가자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="d10e6-180">이 특성은 추가 WorkflowServiceHost에 이후 섹션에 설명 된 대로 [워크플로에 대 한 추적 구성](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="d10e6-181">호스트에서 내보내는 추적 레코드의 자세한 정도는 추적 프로필의 구성 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="d10e6-182">추적 참가자는 쿼리를 추적 프로필에 추가하여 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="d10e6-183">모든 추적 레코드를 구독 하려면 추적 프로필 사용 하 여 모든 추적 쿼리를 지정 해야 "\*" 각 쿼리의 이름 필드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>  
  
 <span data-ttu-id="d10e6-184">다음은 추적 프로필의 일반적인 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d10e6-184">Here are some of the common examples of tracking profiles.</span></span>  
  
-   <span data-ttu-id="d10e6-185">워크플로 인스턴스 레코드 및 오류를 가져오는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d10e6-185">A tracking profile to obtain workflow instance records and faults.</span></span>  
  
```xml  
<trackingProfile name="Instance and Fault Records">  
  <workflow activityDefinitionId="*">  
    <workflowInstanceQueries>  
      <workflowInstanceQuery>  
        <states>  
          <state name="*" />  
        </states>  
      </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    <activityStateQueries>  
      <activityStateQuery activityName="*">  
        <states>  
          <state name="Faulted"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  </workflow>  
</trackingProfile>  
```  
  
1.  <span data-ttu-id="d10e6-186">모든 사용자 지정 추적 레코드를 가져오는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d10e6-186">A tracking profile to obtain all custom tracking records.</span></span>  
  
```xml  
<trackingProfile name="Instance_And_Custom_Records">  
  <workflow activityDefinitionId="*">  
    <customTrackingQueries>  
      <customTrackingQuery name="*" activityName="*" />  
    </customTrackingQueries>  
  </workflow>  
</trackingProfile>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d10e6-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d10e6-187">See Also</span></span>  
 [<span data-ttu-id="d10e6-188">SQL 추적</span><span class="sxs-lookup"><span data-stu-id="d10e6-188">SQL Tracking</span></span>](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)  
 [<span data-ttu-id="d10e6-189">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="d10e6-189">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="d10e6-190">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="d10e6-190">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
