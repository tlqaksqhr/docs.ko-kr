---
title: '&lt;etwTracking&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 6defccdd6a81a1c00a4b65fa9214c86e6cccbea2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltetwtrackinggt"></a><span data-ttu-id="8721c-102">&lt;etwTracking&gt;</span><span class="sxs-lookup"><span data-stu-id="8721c-102">&lt;etwTracking&gt;</span></span>
<span data-ttu-id="8721c-103">사용 하 여 ETW 추적을 사용할 수 있도록 허용 하는 서비스 동작은 <xref:System.Activities.Tracking.EtwTrackingParticipant>합니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-103">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="8721c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8721c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8721c-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8721c-105">\<behaviors></span></span>  
<span data-ttu-id="8721c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8721c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8721c-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8721c-107">\<behavior></span></span>  
<span data-ttu-id="8721c-108">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="8721c-108">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8721c-109">구문</span><span class="sxs-lookup"><span data-stu-id="8721c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8721c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8721c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8721c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8721c-112">특성</span><span class="sxs-lookup"><span data-stu-id="8721c-112">Attributes</span></span>  
  
|<span data-ttu-id="8721c-113">특성</span><span class="sxs-lookup"><span data-stu-id="8721c-113">Attribute</span></span>|<span data-ttu-id="8721c-114">설명</span><span class="sxs-lookup"><span data-stu-id="8721c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8721c-115">profileName</span><span class="sxs-lookup"><span data-stu-id="8721c-115">profileName</span></span>|<span data-ttu-id="8721c-116">이 동작과 연결된 추적 프로필의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8721c-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8721c-117">Child Elements</span></span>  
 <span data-ttu-id="8721c-118">없음</span><span class="sxs-lookup"><span data-stu-id="8721c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8721c-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8721c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8721c-120">요소</span><span class="sxs-lookup"><span data-stu-id="8721c-120">Element</span></span>|<span data-ttu-id="8721c-121">설명</span><span class="sxs-lookup"><span data-stu-id="8721c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8721c-122">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8721c-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8721c-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8721c-124">설명</span><span class="sxs-lookup"><span data-stu-id="8721c-124">Remarks</span></span>  
 <span data-ttu-id="8721c-125">이 구성 요소를 서비스의 동작 구성에 추가하는 경우 워크플로 서비스에서 추적 참가자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="8721c-126">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="8721c-127">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8721c-128">예제</span><span class="sxs-lookup"><span data-stu-id="8721c-128">Example</span></span>  
 <span data-ttu-id="8721c-129">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="8721c-130">ETW 추적 참가자에서 ETW에 추적 레코드를 쓰기 위해 사용 하는 공급자 Id에 정의 된  **\<진단 >** 섹션.</span><span class="sxs-lookup"><span data-stu-id="8721c-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="8721c-131">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="8721c-132">이 정의한는 **profileName** 특성에는  **\<추가 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="8721c-133">추적 참가자에 추가 되 고, 정의 되 면는  **\<etwTracking >** 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="8721c-134">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8721c-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8721c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8721c-135">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="8721c-136">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8721c-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8721c-137">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="8721c-137">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
