---
title: WCF의 &lt;add&gt;
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 31c2274b4e9f40f503e9cd2e673572f61ef66083
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748190"
---
# <a name="ltaddgt-of-wcf"></a><span data-ttu-id="d8950-102">WCF의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="d8950-102">&lt;add&gt; of WCF</span></span>
<span data-ttu-id="d8950-103">런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자를 직접 구성하고 구성된 방식대로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="d8950-104">여기에는 특정 출력(예: 파일, 콘솔, ETW)에 쓰기, 레코드 처리/집계 또는 필요한 기타 조합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="d8950-105">워크플로 추적 및 추적 참가자에 대 한 자세한 내용은 참조 하십시오. [워크플로 추적 및 트레이싱](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) 및 [추적 참가자](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="d8950-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d8950-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d8950-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d8950-107">\<tracking></span></span>  
<span data-ttu-id="d8950-108">\<참가자 ></span><span class="sxs-lookup"><span data-stu-id="d8950-108">\<participants></span></span>  
<span data-ttu-id="d8950-109">\<add></span><span class="sxs-lookup"><span data-stu-id="d8950-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8950-110">구문</span><span class="sxs-lookup"><span data-stu-id="d8950-110">Syntax</span></span>  
  
```xml
   <tracking>    <participants>       <add name="String"            profileName="String"           type="String" />    </participants> </tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d8950-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d8950-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d8950-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8950-113">특성</span><span class="sxs-lookup"><span data-stu-id="d8950-113">Attributes</span></span>  
  
|<span data-ttu-id="d8950-114">요소</span><span class="sxs-lookup"><span data-stu-id="d8950-114">Element</span></span>|<span data-ttu-id="d8950-115">설명</span><span class="sxs-lookup"><span data-stu-id="d8950-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8950-116">name</span><span class="sxs-lookup"><span data-stu-id="d8950-116">name</span></span>|<span data-ttu-id="d8950-117">추적 참가자의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="d8950-118">profileName</span><span class="sxs-lookup"><span data-stu-id="d8950-118">profileName</span></span>|<span data-ttu-id="d8950-119">추적 참가자가 구독하는 추적 레코드를 정의하는 추적 프로필의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="d8950-120">형식</span><span class="sxs-lookup"><span data-stu-id="d8950-120">type</span></span>|<span data-ttu-id="d8950-121">추적 참가자의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8950-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d8950-122">Child Elements</span></span>  
 <span data-ttu-id="d8950-123">없음</span><span class="sxs-lookup"><span data-stu-id="d8950-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8950-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d8950-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d8950-125">요소</span><span class="sxs-lookup"><span data-stu-id="d8950-125">Element</span></span>|<span data-ttu-id="d8950-126">설명</span><span class="sxs-lookup"><span data-stu-id="d8950-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8950-127">\<participants></span><span class="sxs-lookup"><span data-stu-id="d8950-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="d8950-128">추적 참가자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8950-129">설명</span><span class="sxs-lookup"><span data-stu-id="d8950-129">Remarks</span></span>  
 <span data-ttu-id="d8950-130">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="d8950-131">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="d8950-132">여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="d8950-133">각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="d8950-134">ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="d8950-135">추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="d8950-136">ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="d8950-137">표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8950-138">예제</span><span class="sxs-lookup"><span data-stu-id="d8950-138">Example</span></span>  
 <span data-ttu-id="d8950-139">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="d8950-140">ETW 추적 참가자에서 ETW에 추적 레코드를 작성하기 위해 사용하는 공급자 ID는 `<diagnostics>` 섹션에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="d8950-141">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="d8950-142">이 프로필은 `profileName` 요소의 `<add>` 특성에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-142">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="d8950-143">프로필이 정의되면 추적 참가자가 `<etwTracking>` 서비스 동작에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-143">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="d8950-144">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d8950-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8950-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8950-145">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="d8950-146">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d8950-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d8950-147">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="d8950-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
