---
title: "워크플로의 &lt;system.serviceModel&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97247abe629d12b6c60d8157786b9b82e9e14f4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="f1ef9-102">워크플로의 &lt;system.serviceModel&gt;</span><span class="sxs-lookup"><span data-stu-id="f1ef9-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="f1ef9-103">이 구성 섹션에는 모든 워크플로 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ef9-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1ef9-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName="String"   
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>    
     <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
     </participants>   
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1ef9-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1ef9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f1ef9-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1ef9-107">특성</span><span class="sxs-lookup"><span data-stu-id="f1ef9-107">Attributes</span></span>  
 <span data-ttu-id="f1ef9-108">없음</span><span class="sxs-lookup"><span data-stu-id="f1ef9-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1ef9-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1ef9-109">Child Elements</span></span>  
  
|<span data-ttu-id="f1ef9-110">요소</span><span class="sxs-lookup"><span data-stu-id="f1ef9-110">Element</span></span>|<span data-ttu-id="f1ef9-111">설명</span><span class="sxs-lookup"><span data-stu-id="f1ef9-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1ef9-112">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f1ef9-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="f1ef9-113">이 섹션에서는 정의 **serviceBehaviors** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="f1ef9-114">컬렉션의 각 요소는 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="f1ef9-115">각 동작 요소는 고유한으로 식별 되 **이름** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="f1ef9-116">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="f1ef9-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="f1ef9-117">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="f1ef9-118">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 참조 하십시오. [워크플로 추적 및 트레이싱](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) 및 [워크플로에 대 한 추적 구성](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1ef9-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1ef9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f1ef9-120">요소</span><span class="sxs-lookup"><span data-stu-id="f1ef9-120">Element</span></span>|<span data-ttu-id="f1ef9-121">설명</span><span class="sxs-lookup"><span data-stu-id="f1ef9-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1ef9-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1ef9-122">\<configuration></span></span>|<span data-ttu-id="f1ef9-123">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
