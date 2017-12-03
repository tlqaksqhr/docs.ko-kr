---
title: "방법: 워크플로 및 워크플로 서비스에 지속성 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1db45ecad833c4c05ba240569da9c85271e0b69e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="0572c-102">방법: 워크플로 및 워크플로 서비스에 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="0572c-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="0572c-103">이 항목에서는 워크플로 및 워크플로 서비스에 대해 지속성을 사용하도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="0572c-104">워크플로에 대해 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="0572c-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="0572c-105">와 인스턴스 저장소에 연결할 수 있습니다는 **WorkflowApplication** 를 사용 하 여는 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> 의 속성은 <xref:System.Activities.WorkflowApplication> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="0572c-106"><xref:System.Activities.WorkflowApplication.Persist%2A> 메서드는 응용 프로그램에 연결된 인스턴스 저장소에 워크플로를 저장하거나 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="0572c-107"><xref:System.Activities.WorkflowApplication.Unload%2A> 메서드는 인스턴스 저장소에 워크플로를 유지한 다음 메모리에서 인스턴스를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="0572c-108">**부하** 메서드는 워크플로 인스턴스 지 속성 저장소에 저장 된 워크플로 데이터를 사용 하 여 메모리에 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="0572c-109">**Persist** 메서드는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-109">The **Persist** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="0572c-110">워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="0572c-111">워크플로를 지속성 저장소에 유지하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="0572c-112">워크플로 스케줄러를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="0572c-113">**언로드** 메서드는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-113">The **Unload** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="0572c-114">워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="0572c-115">워크플로를 지속성 저장소에 유지하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="0572c-116">워크플로 인스턴스를 메모리에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="0572c-117">두는 **Persist** 및 **언로드** 메서드는 워크플로가 비지 속성 영역이 종료 될 때까지 워크플로가 비지 속성 영역에는 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="0572c-118">비지속성 영역이 완료되면 메서드에서 지속 또는 언로드 작업을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="0572c-119">제한 시간이 경과할 때까지 비지속성 영역이 완료되지 않거나 지속성 프로세스가 너무 오래 걸릴 경우 TimeoutException이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="0572c-120">코드에서 워크플로 서비스에 대해 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="0572c-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="0572c-121">**DurableInstancingOptions** 의 멤버는 <xref:System.ServiceModel.WorkflowServiceHost> 클래스 라는 속성이 **InstanceStore** 와 인스턴스 저장소에 연결 하는 데 사용할 수 있는 **WorkflowServiceHost** .</span><span class="sxs-lookup"><span data-stu-id="0572c-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="0572c-122">경우는 **WorkflowServiceHost** 은 열, 지 속성은 자동으로 경우 사용할 수는 **DurableInstancingOptions.InstanceStore** null이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="0572c-123">서비스 동작을 사용 하 여 워크플로 서비스 호스트에 사용할 구체적인 인스턴스 저장소를 제공 하는 일반적으로 **InstanceStore** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="0572c-124">인스턴스를 sqlworkflowinstancestorebehavior 예를 들어는 **SqlWorkflowInstanceStore**, 구성, 및에 할당 된 **DurableInstancingOptions.InstanceStore**합니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="0572c-125">응용 프로그램 구성 파일을 사용하여 워크플로 서비스에 지속성 허용</span><span class="sxs-lookup"><span data-stu-id="0572c-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="0572c-126">다음 코드를 app.config 또는 web.config 파일에 추가하여 응용 프로그램 구성 파일을 통해 지속성을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0572c-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
