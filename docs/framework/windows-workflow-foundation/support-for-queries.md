---
title: "쿼리 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4f338f9ae5cc6967885d0518eb573d9f9535fc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="support-for-queries"></a><span data-ttu-id="7fba9-102">쿼리 지원</span><span class="sxs-lookup"><span data-stu-id="7fba9-102">Support for Queries</span></span>
<span data-ttu-id="7fba9-103">SQL 워크플로 인스턴스 저장소는 잘 알려진 속성 집합을 저장소에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="7fba9-104">사용자는 이러한 속성을 기반으로 인스턴스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="7fba9-105">다음은 잘 알려진 일부 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-105">The following list contains some of these well-known properties:</span></span>  
  
-   <span data-ttu-id="7fba9-106">**사이트 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-106">**Site Name.**</span></span> <span data-ttu-id="7fba9-107">서비스를 포함하는 웹 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-107">Name of the Web site that contains the service.</span></span>  
  
-   <span data-ttu-id="7fba9-108">**응용 프로그램 상대 경로입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-108">**Relative Application Path.**</span></span> <span data-ttu-id="7fba9-109">웹 사이트에 상대적인 응용 프로그램 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-109">Path of the application relative to the Web site.</span></span>  
  
-   <span data-ttu-id="7fba9-110">**상대적인 서비스 경로입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-110">**Relative Service Path.**</span></span> <span data-ttu-id="7fba9-111">응용 프로그램에 상대적인 서비스 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-111">Path of the service relative to the application.</span></span>  
  
-   <span data-ttu-id="7fba9-112">**서비스 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-112">**Service Name.**</span></span> <span data-ttu-id="7fba9-113">서비스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-113">Name of the service.</span></span>  
  
-   <span data-ttu-id="7fba9-114">**서비스 Namespace입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-114">**Service Namespace.**</span></span> <span data-ttu-id="7fba9-115">서비스에 사용되는 네임스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-115">Name of the namespace that the service uses.</span></span>  
  
-   <span data-ttu-id="7fba9-116">**현재 컴퓨터입니다.**</span><span class="sxs-lookup"><span data-stu-id="7fba9-116">**Current Machine.**</span></span>  
  
-   <span data-ttu-id="7fba9-117">**마지막 컴퓨터**합니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-117">**Last Machine**.</span></span> <span data-ttu-id="7fba9-118">워크플로 서비스 인스턴스가 마지막으로 실행된 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fba9-119">워크플로 서비스 호스트를 사용하는 자체 호스팅 시나리오의 경우 마지막 네 속성만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="7fba9-120">워크플로 응용 프로그램 시나리오의 경우 마지막 속성만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="7fba9-121">워크플로 런타임에서 처음 세 속성에 대한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="7fba9-122">에 대 한 값을 제공 하는 워크플로 서비스 호스트는 **Suspend Reason** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="7fba9-123">에 대 한 값을 제공 하는 자체 SQL 워크플로 인스턴스 저장소는 **Last Updated Machine** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="7fba9-124">또한 SQL 워크플로 인스턴스 저장소 기능을 사용하면 사용자 지정 속성을 지정하여 지속성 데이터베이스에 값을 저장한 다음 쿼리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="7fba9-125">사용자 지정 확장에 대 한 자세한 내용은 참조 [저장소 확장성](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-125">For more information about custom promotions, see [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="7fba9-126">보기</span><span class="sxs-lookup"><span data-stu-id="7fba9-126">Views</span></span>  
 <span data-ttu-id="7fba9-127">인스턴스 저장소에는 다음 뷰가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-127">The instance store contains the following views.</span></span> <span data-ttu-id="7fba9-128">참조 [지 속성 데이터베이스 스키마](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-128">See [Persistence Database Schema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="7fba9-129">Instances 뷰</span><span class="sxs-lookup"><span data-stu-id="7fba9-129">The Instances View</span></span>  
 <span data-ttu-id="7fba9-130">인스턴스 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-130">The Instances view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="7fba9-131">**ID**</span><span class="sxs-lookup"><span data-stu-id="7fba9-131">**Id**</span></span>  
  
2.  <span data-ttu-id="7fba9-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="7fba9-132">**PendingTimer**</span></span>  
  
3.  <span data-ttu-id="7fba9-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="7fba9-133">**CreationTime**</span></span>  
  
4.  <span data-ttu-id="7fba9-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="7fba9-134">**LastUpdatedTime**</span></span>  
  
5.  <span data-ttu-id="7fba9-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="7fba9-135">**ServiceDeploymentId**</span></span>  
  
6.  <span data-ttu-id="7fba9-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="7fba9-136">**SuspensionExceptionName**</span></span>  
  
7.  <span data-ttu-id="7fba9-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="7fba9-137">**SuspensionReason**</span></span>  
  
8.  <span data-ttu-id="7fba9-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="7fba9-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="7fba9-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="7fba9-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="7fba9-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="7fba9-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="7fba9-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="7fba9-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="7fba9-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="7fba9-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="7fba9-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="7fba9-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="7fba9-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="7fba9-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="7fba9-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="7fba9-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="7fba9-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="7fba9-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="7fba9-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="7fba9-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="7fba9-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="7fba9-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="7fba9-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="7fba9-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="7fba9-150">ServiceDeployments 뷰</span><span class="sxs-lookup"><span data-stu-id="7fba9-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="7fba9-151">ServiceDeployments 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="7fba9-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="7fba9-152">**SiteName**</span></span>  
  
2.  <span data-ttu-id="7fba9-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="7fba9-153">**RelativeServicePath**</span></span>  
  
3.  <span data-ttu-id="7fba9-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="7fba9-154">**RelativeApplicationPath**</span></span>  
  
4.  <span data-ttu-id="7fba9-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="7fba9-155">**ServiceName**</span></span>  
  
5.  <span data-ttu-id="7fba9-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="7fba9-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="7fba9-157">InstancePromotedProperties 뷰</span><span class="sxs-lookup"><span data-stu-id="7fba9-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="7fba9-158">InstancePromotedProperties 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="7fba9-159">승격 된 속성에 대 한 자세한 내용은 참조는 [저장소 확장성](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="7fba9-159">For details on promoted properties, see the [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) topic.</span></span>  
  
1.  <span data-ttu-id="7fba9-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="7fba9-160">**InstanceId**</span></span>  
  
2.  <span data-ttu-id="7fba9-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="7fba9-161">**EncodingOption**</span></span>  
  
3.  <span data-ttu-id="7fba9-162">**Promotionname은**</span><span class="sxs-lookup"><span data-stu-id="7fba9-162">**PromotionName**</span></span>  
  
4.  <span data-ttu-id="7fba9-163">**Value #** (필드 범위 **Value1** 를 **Value64**).</span><span class="sxs-lookup"><span data-stu-id="7fba9-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
