---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b4b1903182cfa20944d919f57ff1e09e07953b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsqlworkflowinstancestoregt"></a><span data-ttu-id="1def2-102">&lt;sqlWorkflowInstanceStore&gt;</span><span class="sxs-lookup"><span data-stu-id="1def2-102">&lt;sqlWorkflowInstanceStore&gt;</span></span>
<span data-ttu-id="1def2-103">구성할 수 있는 서비스 동작인은 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 기능을 워크플로 서비스 인스턴스를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 대 한 상태 정보를 유지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-103">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="1def2-104">이 기능에 대 한 자세한 내용은 참조 하십시오. [SQL 워크플로 인스턴스 저장소](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-104">For more information on this feature, see [SQL Workflow Instance Store](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
<span data-ttu-id="1def2-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1def2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1def2-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1def2-106">\<behaviors></span></span>  
<span data-ttu-id="1def2-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1def2-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="1def2-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="1def2-108">\<behavior></span></span>  
<span data-ttu-id="1def2-109">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="1def2-109">\<sqlWorkflowInstanceStore></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1def2-110">구문</span><span class="sxs-lookup"><span data-stu-id="1def2-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1def2-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1def2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1def2-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1def2-113">특성</span><span class="sxs-lookup"><span data-stu-id="1def2-113">Attributes</span></span>  
  
|<span data-ttu-id="1def2-114">특성</span><span class="sxs-lookup"><span data-stu-id="1def2-114">Attribute</span></span>|<span data-ttu-id="1def2-115">설명</span><span class="sxs-lookup"><span data-stu-id="1def2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1def2-116">connectionString</span><span class="sxs-lookup"><span data-stu-id="1def2-116">connectionString</span></span>|<span data-ttu-id="1def2-117">기본 지 속성 데이터베이스에 연결 하는 데 필요한 연결 문자열을 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-117">A string that contains a connection string used to connect to an underlying persistence database.</span></span>|  
|<span data-ttu-id="1def2-118">connectionStringName</span><span class="sxs-lookup"><span data-stu-id="1def2-118">connectionStringName</span></span>|<span data-ttu-id="1def2-119">데이터베이스 서버에 명명 된 연결 문자열을 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-119">A string that contains a named connection string to the database server.</span></span> <span data-ttu-id="1def2-120">명명된 된 연결 문자열의 예로 "defaultconnectionstring"입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-120">An example of a named connection string is "DefaultConnectionString".</span></span>|  
|<span data-ttu-id="1def2-121">honstLockRenewalPeriod</span><span class="sxs-lookup"><span data-stu-id="1def2-121">honstLockRenewalPeriod</span></span>|<span data-ttu-id="1def2-122">호스트에서 인스턴스에 대한 잠금을 갱신해야 하는 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-122">A Timespan value that specifies the time period in which the host must renew the lock on an instance.</span></span> <span data-ttu-id="1def2-123">호스트에서 지정된 기간 내에 잠금을 갱신하지 않으면 인스턴스 잠금이 해제되어 다른 호스트가 이를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-123">If the host does not renew the lock in the specified time period, the instance is unlocked and may be picked up by another host.</span></span><br /><br /> <span data-ttu-id="1def2-124">워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-124">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="1def2-125">이 특성은 워크플로 인스턴스가 유지 되 고 후 즉시 언로드됩니다 0으로 설정 하는 경우 워크플로가 유휴 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-125">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="1def2-126">언로드 작업이 해제 timespan.maxvalue 효과적으로이 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-126">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="1def2-127">즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-127">Idle workflow instances are never unloaded.</span></span>|  
|<span data-ttu-id="1def2-128">instanceCompletionAction</span><span class="sxs-lookup"><span data-stu-id="1def2-128">instanceCompletionAction</span></span>|<span data-ttu-id="1def2-129">워크플로 인스턴스가 완료되면 워크플로 인스턴스 데이터가 지속성 저장소에 보관되는지 아니면 해당 시점에 삭제되는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-129">A value that specifies whether workflow instance data is kept in the persistence store after the workflow instance completes or if it is deleted at that point.</span></span> <span data-ttu-id="1def2-130">이 값은 <xref:System.Activities.DurableInstancing.InstanceCompletionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-130">This value is of type <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.</span></span><br /><br /> <span data-ttu-id="1def2-131">열거된 동작은 인스턴스에서 해당 작업을 완료하면 지속성 저장소에서 인스턴스 데이터를 삭제하거나 지속성 저장소에서 인스턴스 데이터를 삭제하지 않는 것으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-131">The enumerated actions consist of deleting the instance data from the persistence store or not deleting the instance data from the persistence store, when the instance has completed its operation.</span></span><br /><br /> <span data-ttu-id="1def2-132">완료된 후 인스턴스를 유지하면 지속성 데이터베이스가 빠르게 커지고 데이터베이스 성능에 영향을 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-132">Keeping instances after completion causes the persistence database to grow rapidly and this affects the performance of the database.</span></span> <span data-ttu-id="1def2-133">성능 요구 사항을 충족하는 수준으로 데이터베이스 성능을 유지하려면 이러한 레코드를 주기적으로 삭제하는 데이터베이스 비우기 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-133">You should configure a database purge policy to delete these records periodically to ensure that the performance of the database is at the level that satisfy your performance requirements.</span></span>|  
|<span data-ttu-id="1def2-134">instanceEncodingOption</span><span class="sxs-lookup"><span data-stu-id="1def2-134">instanceEncodingOption</span></span>|<span data-ttu-id="1def2-135">정보를 지속성 저장소에 저장하기 전에 인스턴스 상태 정보를 GZip 알고리즘을 사용하여 압축할지 여부를 지정하는 선택적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-135">An optional value that specifies  whether the instance state information is compressed using the GZip algorithm before the information is saved in the persistence store..</span></span> <span data-ttu-id="1def2-136">이 값은 `System.Activities.DurableInstancing.InstanceEncodingAction` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-136">This value is of type `System.Activities.DurableInstancing.InstanceEncodingAction`.</span></span> <span data-ttu-id="1def2-137">이 속성에 대 한 가능한 값은 "None", "GZip" 데이터 압축 하 고 gzip 알고리즘을 사용 하 여 해당 인스턴스를 지정 하는 없고, 압축을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-137">Possible values for this property are "None", which specifies no compression, and "GZip", which specifies that instance data is compressed and uses the gzip algorithm.</span></span>|  
|<span data-ttu-id="1def2-138">instanceLockedExceptionAction</span><span class="sxs-lookup"><span data-stu-id="1def2-138">instanceLockedExceptionAction</span></span>|<span data-ttu-id="1def2-139">호스트에서 인스턴스를 잠그려고 할 때 현재 다른 호스트에서 해당 인스턴스를 잠근 경우에 throw되는 예외에 대한 응답으로 발생하는 동작을 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-139">A value that specifies the action that occurs in response to an exception that is thrown when the host tries to lock an instance because the instance is currently locked by another host.</span></span> <span data-ttu-id="1def2-140">이 값은 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-140">This value is of type <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.</span></span><br /><br /> <span data-ttu-id="1def2-141">이 필드에 사용할 수 있는 옵션은 None, Basic Retry 및 Aggressive Retry입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-141">The options allowed for this field are: None, Basic Retry, and Aggressive Retry.</span></span> <span data-ttu-id="1def2-142">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-142">The default value is None.</span></span> <span data-ttu-id="1def2-143">다음은 이러한 세 옵션에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-143">The following list provides you with the descriptions for these three options:</span></span><br /><br /> <span data-ttu-id="1def2-144">- 없음</span><span class="sxs-lookup"><span data-stu-id="1def2-144">-   None.</span></span> <span data-ttu-id="1def2-145">서비스 호스트가 인스턴스 잠금을 시도하지 않고 <xref:System.Runtime.DurableInstancing.InstanceLockedException>을 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-145">The service host does not attempt to lock the instance and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller.</span></span><br /><span data-ttu-id="1def2-146">-기본 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-146">-   Basic Retry.</span></span> <span data-ttu-id="1def2-147">서비스 호스트가 선형 다시 시도 간격을 사용하여 인스턴스 잠금을 다시 시도하고 시퀀스의 끝에 예외를 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-147">The service host reattempts to lock the instance with a linear retry interval and passes the exception to the caller at the end of the sequence.</span></span><br /><span data-ttu-id="1def2-148">-적극적인 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-148">-   Aggressive Retry.</span></span> <span data-ttu-id="1def2-149">서비스 호스트에서 지연 간격을 기하급수적으로 증가시켜 인스턴스 잠금을 다시 시도하고 시퀀스 마지막에 <xref:System.Runtime.DurableInstancing.InstanceLockedException>을 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-149">The service host reattempts to lock the instance with an exponentially increasing delay and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller at the end of the sequence.</span></span>|  
|<span data-ttu-id="1def2-150">runnableInstancesDetectionPeriod</span><span class="sxs-lookup"><span data-stu-id="1def2-150">runnableInstancesDetectionPeriod</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="1def2-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1def2-151">Child Elements</span></span>  
 <span data-ttu-id="1def2-152">없음</span><span class="sxs-lookup"><span data-stu-id="1def2-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1def2-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1def2-153">Parent Elements</span></span>  
  
|<span data-ttu-id="1def2-154">요소</span><span class="sxs-lookup"><span data-stu-id="1def2-154">Element</span></span>|<span data-ttu-id="1def2-155">설명</span><span class="sxs-lookup"><span data-stu-id="1def2-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1def2-156">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1def2-156">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1def2-157">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1def2-157">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1def2-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1def2-158">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
 [<span data-ttu-id="1def2-159">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="1def2-159">SQL Workflow Instance Store</span></span>](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
