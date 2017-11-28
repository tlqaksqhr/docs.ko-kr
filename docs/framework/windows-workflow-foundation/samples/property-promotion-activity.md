---
title: "속성 승격 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd8356927ad7cb4c24cc278fcb901cc543c6d7b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="property-promotion-activity"></a><span data-ttu-id="e37e7-102">속성 승격 활동</span><span class="sxs-lookup"><span data-stu-id="e37e7-102">Property Promotion Activity</span></span>
<span data-ttu-id="e37e7-103">이 샘플에서는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 승격 기능을 워크플로 작성 환경에 직접 통합하는 종단 간 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="e37e7-104">승격 기능의 사용을 단순화하는 워크플로 확장, 워크플로 활동 및 구성 요소의 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="e37e7-105">또한 샘플에는 이 컬렉션을 사용하는 방법을 보여 주는 간단한 워크플로가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e37e7-106">예제는 교육용으로만 제공되므로</span><span class="sxs-lookup"><span data-stu-id="e37e7-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="e37e7-107">프로덕션 환경에서 사용하기에 적합하지 않으며 프로덕션 환경에서 테스트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="e37e7-108">Microsoft에서는 이러한 샘플에 대해 기술 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e37e7-109">필수 조건</span><span class="sxs-lookup"><span data-stu-id="e37e7-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="e37e7-110">초기화된 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="e37e7-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="e37e7-111">샘플 프로젝트</span><span class="sxs-lookup"><span data-stu-id="e37e7-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="e37e7-112">**PropertyPromotionActivity** 프로젝트에는 승격 관련 구성 요소, 워크플로 활동 및 워크플로 확장에 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="e37e7-113">**CounterServiceApplication** 프로젝트를 사용 하는 샘플 워크플로가 포함 되어는 **SqlWorkflowInstanceStorePromotion** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="e37e7-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="e37e7-114"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 데이터베이스에 대해 실행되어야 하는 SQL 스크립트(PropertyPromotionActivitySQLSample.sql)</span><span class="sxs-lookup"><span data-stu-id="e37e7-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="e37e7-115">두 가지 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 프로젝트를 연결하는 솔루션 파일(`PropertyPromotionActivity.sln`)</span><span class="sxs-lookup"><span data-stu-id="e37e7-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="e37e7-116">샘플을 설치하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e37e7-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="e37e7-117">워크플로 지속성 데이터베이스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="e37e7-118">샘플 디렉터리(\WF\Basic\Persistence\PropertyPromotionActivity)로 이동하고 CreateInstanceStore.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="e37e7-119">관리자 권한이 없는 경우 SQL Server 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="e37e7-120">SQL Server Management Studio에서로 이동 **보안**, **로그인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="e37e7-121">마우스 오른쪽 단추로 클릭 **로그인** 새 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="e37e7-122">SQL 역할을 열어 ACL 사용자를 추가 **데이터베이스**, **InstanceStore**, **보안**합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="e37e7-123">마우스 오른쪽 단추로 클릭 **사용자** 선택 **새 사용자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="e37e7-124">설정의 **로그인 이름** 위에서 만든 사용자에 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="e37e7-125">데이터베이스 역할 멤버 자격(예: System.Activities.DurableInstancing.InstanceStoreUsers)에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="e37e7-126">사용자가 이미 있을 수도 있습니다(예: 사용자 dbo).</span><span class="sxs-lookup"><span data-stu-id="e37e7-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="e37e7-127">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 PropertyPromotionActivity.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="e37e7-128">SQL Server Express의 로컬 설치가 아닌 데이터베이스에 인스턴스 저장소를 만든 경우 데이터베이스 연결 문자열을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="e37e7-129">App.config 파일을 변경는 **CounterServiceApplication** 의 값을 설정 하 여는 `connectionString` 특성에 `sqlWorkflowInstanceStorePromotion` 노드 초기화 된 지 속성 데이터베이스를 가리키도록 1 단계에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="e37e7-130">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-130">Build and run the solution.</span></span> <span data-ttu-id="e37e7-131">Counter WF 서비스가 시작되고 워크플로 인스턴스가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="e37e7-132">지속성 데이터베이스의 [dbo].[CounterService] 뷰에서 모든 행을 빠르게 선택합니다. 이 뷰는 1단계에서 CreateInstanceStore.cmd를 실행하여 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="e37e7-133">다음과 유사한 결과 집합이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="e37e7-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e37e7-134">InstanceId</span></span>|<span data-ttu-id="e37e7-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="e37e7-135">CounterValue</span></span>|<span data-ttu-id="e37e7-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="e37e7-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="e37e7-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="e37e7-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="e37e7-138">12</span><span class="sxs-lookup"><span data-stu-id="e37e7-138">12</span></span>|<span data-ttu-id="e37e7-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="e37e7-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="e37e7-140">뷰를 계속 새로 고치면 CounterValue와 CounterValueLastUpdated가 2초마다 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="e37e7-141">이 간격마다 카운터가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="e37e7-142">CounterValue와 CounterValueLastUpdated는 이 워크플로의 승격된 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="e37e7-143">샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="e37e7-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="e37e7-144">샘플 디렉터리(\WF\Basic\Persistence\PropertyPromotionActivity)에서 RemoveInstanceStore.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="e37e7-145">이 샘플 이해</span><span class="sxs-lookup"><span data-stu-id="e37e7-145">Understanding This Sample</span></span>  
 <span data-ttu-id="e37e7-146">이 샘플에는 두 가지 프로젝트와 SQL 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="e37e7-147">**CounterServiceApplication** 간단한 Counter WF 서비스를 호스트 하는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="e37e7-148">`Start` 끝점을 통해 단방향 메시지를 받을 때 워크플로는 0부터 29까지 계산하며 2초마다 카운터 변수를 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="e37e7-149">각 카운터가 증가한 후 워크플로가 유지되고 승격된 속성이 [dbo].[CounterService] 뷰에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="e37e7-150">콘솔 응용 프로그램은 실행될 때 WF 서비스를 호스트하고 메시지를 `Start` 끝점에 보내 Counter WF 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="e37e7-151">**PropertyPromotionActivity** 워크플로 확장명, 워크플로 활동 및 구성 요소를 포함 하는 클래스 라이브러리는 **CounterServiceApplication** 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="e37e7-152">**PropertyPromotionActivitySQLSample.sql** 만들고 추가 보기 [dbo]. [ CounterService] 데이터베이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="e37e7-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="e37e7-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="e37e7-154">SqlWorkflowInstanceStorePromotion 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="e37e7-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="e37e7-155">`SqlWorkflowInstanceStorePromotion` 구성 요소는 `SqlWorkflowInstanceStore` 구성 요소에서 상속하지만 `promotionSets`라는 추가 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="e37e7-156">`promotionSets` 요소를 사용하여 구성을 통해 승격된 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="e37e7-157">이는 샘플에서 사용되는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="e37e7-158">[dbo].[CounterService] 뷰의 정의를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="e37e7-159">워크플로 인스턴스가 유지될 때 구성에 정의된 각 `InstancePromotedProperties`의 `PromotionSet` 뷰에 행이 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="e37e7-160">이 행에는 `PromotionSet`의 승격된 속성이 모두 포함되어 있습니다(열당 하나의 승격된 속성).</span><span class="sxs-lookup"><span data-stu-id="e37e7-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="e37e7-161">이 `PromotionSet`는 `InstanceId, PromotionName` 튜플로 키가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="e37e7-162">이 샘플에서는 이름 특성이 `PromotionSet`인 `CounterService` 하나가 구성에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="e37e7-163">`PromotionName` 열 값은 `PromotionSet` 요소의 이름 특성과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="e37e7-164">`promotedValue` 요소의 순서는 `InstancePromotedProperties` 뷰에서 승격된 속성의 배치와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="e37e7-165">`Count`는 첫 번째 `promotedValue` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="e37e7-166">`Value1` 뷰의 `InstancePromotedProperties` 열에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="e37e7-167">`LastIncrementedAt`는 두 번째 `promotedValue` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="e37e7-168">`Value2` 뷰의 `InstancePromotedProperties` 열에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="e37e7-169">PromoteValue 활동 사용</span><span class="sxs-lookup"><span data-stu-id="e37e7-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="e37e7-170">[!INCLUDE[wf2](../../../../includes/wf2-md.md)] Designer에서 CounterService.xamlx 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-170">Examine the CounterService.xamlx file in the [!INCLUDE[wf2](../../../../includes/wf2-md.md)] Designer.</span></span> <span data-ttu-id="e37e7-171">WF 정의에는 `PromoteValue<DateTime>` 및 `PromoteValue<Int32>`라는 두 가지 특수 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="e37e7-172">`PromoteValue<Int32>` 활동의 `Name` 멤버는 `Count`으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="e37e7-173">이는 구성의 첫 번째 `promotedValue` 요소와 일치하며 `Value`가 `Counter` 워크플로 변수로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="e37e7-174">워크플로가 유지될 때 `Counter` 워크플로 변수는 `Value1` 뷰의 `InstancePromotedProperties` 열에 승격된 속성으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="e37e7-175">`PromoteValue<DateTime>` 활동의 `Name` 멤버는 `LastIncrementedAt`으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="e37e7-176">이는 구성의 두 번째 `promotedValue` 요소와 일치하며 `Value`가 `TimeLastIncremented` 워크플로 변수로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="e37e7-177">즉, 워크플로가 유지될 때 `TimeLastIncremented` 워크플로 변수의 값은 `Value2` 뷰의 `InstancePromotedProperties` 열에 승격된 속성으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="e37e7-178">`PromotedValue` 활동에는 `ClearExistingPromotedData`라는 부울 멤버도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="e37e7-179">이 멤버가 `true`로 설정되면 워크플로의 해당 지점까지 승격된 속성 값이 모두 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="e37e7-180">예를 들어 Sequence 활동이 다음과 같이 정의된 경우</span><span class="sxs-lookup"><span data-stu-id="e37e7-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="e37e7-181">PromoteValue {Name = "Count", 값 = 3을 (를)</span><span class="sxs-lookup"><span data-stu-id="e37e7-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="e37e7-182">PromoteValue {이름 값 "LastIncrementedAt" = = 1-1-2000}</span><span class="sxs-lookup"><span data-stu-id="e37e7-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="e37e7-183">유지</span><span class="sxs-lookup"><span data-stu-id="e37e7-183">Persist</span></span>  
  
4.  <span data-ttu-id="e37e7-184">PromoteValue {Name = "Count", 값 = 4, ClearExistingPromotedData = true}</span><span class="sxs-lookup"><span data-stu-id="e37e7-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="e37e7-185">유지</span><span class="sxs-lookup"><span data-stu-id="e37e7-185">Persist</span></span>  
  
 <span data-ttu-id="e37e7-186">두 번째 유지에서 `Count`의 승격된 값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="e37e7-187">그러나 승격 된 값에 대 한 `LastIncrementedAt` 됩니다 `NULL`합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="e37e7-188">4단계에서 `ClearExistingPromotedData`가 `true`로 설정되지 않은 경우 두 번째 유지 후에 Count의 승격된 값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="e37e7-189">이에 따라 `LastIncrementedAt`의 승격된 값은 여전히 1-1-2000입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="e37e7-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="e37e7-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="e37e7-191">이 클래스 라이브러리에는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 승격 기능의 사용을 단순화하는 다음 공용 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="e37e7-192">PromoteValue 클래스</span><span class="sxs-lookup"><span data-stu-id="e37e7-192">PromoteValue Class</span></span>  
 <span data-ttu-id="e37e7-193">이 클래스는 한 속성을 승격합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-193">This class promotes one property.</span></span> <span data-ttu-id="e37e7-194">승격된 속성의 이름은 구성에 있는 `promotedValue` 요소의 이름 특성과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="e37e7-195">이 활동은 Workflow Designer에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="e37e7-196">사용 예를 보려면 CounterServiceApplication을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e37e7-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="e37e7-197">ClearExistingPromotedData(Bool)</span><span class="sxs-lookup"><span data-stu-id="e37e7-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="e37e7-198">이 활동 전에 승격된 모든 값을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="e37e7-199">Name(string)</span><span class="sxs-lookup"><span data-stu-id="e37e7-199">Name (string)</span></span>  
 <span data-ttu-id="e37e7-200">이 속성을 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-200">The name that represents this property.</span></span> <span data-ttu-id="e37e7-201">이름 특성을 일치 해야이 \<promotedValue >는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="e37e7-202">값 (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="e37e7-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="e37e7-203">열에 저장할 변수/값입니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="e37e7-204">PromoteValues 클래스</span><span class="sxs-lookup"><span data-stu-id="e37e7-204">PromoteValues Class</span></span>  
 <span data-ttu-id="e37e7-205">여러 속성을 승격합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-205">Promotes multiple properties.</span></span> <span data-ttu-id="e37e7-206">승격된 속성의 이름은 구성에 있는 `promotedValue` 요소의 모든 이름 특성과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="e37e7-207">`PromoteValue` 활동과 유사하게 사용할 수 있지만 여러 속성을 동시에 승격할 수 있다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="e37e7-208">이 활동은 Workflow Designer에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="e37e7-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="e37e7-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="e37e7-210">`SqlWorkflowInstanceStoreBehavior`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="e37e7-211">이 파생 클래스는 사용자 지정 지속성 참가자(이 라이브러리의 일부이기도 함)를 워크플로 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="e37e7-212">이전의 두 가지 워크플로 활동의 구현은 이 사용자 지정 지속성 참가자에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="e37e7-213">이 클래스 라이브러리에는 이전의 승격 활동에서 사용되는 사용자 지정 지속성 참가자와 `ConfigurationElement`에 대한 `SqlWorkflowInstanceStorePromotionElement` 구현도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="e37e7-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="e37e7-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="e37e7-215">이 SQL 파일에서는 CounterService 승격이 설정된 모든 인스턴스를 쿼리하기 위한 `[dbo].[CounterService]` 뷰뿐만 아니라 `[InstancePromotedProperties]` 뷰도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e37e7-216">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e37e7-217">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e37e7-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e37e7-218">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="e37e7-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e37e7-219">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e37e7-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="e37e7-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e37e7-220">See Also</span></span>  
 [<span data-ttu-id="e37e7-221">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="e37e7-221">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
