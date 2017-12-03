---
title: "워크플로 유지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 769197b3f59c68c79f94c71c49ba4b1f4f98da2c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="workflow-persistence"></a><span data-ttu-id="7ea68-102">워크플로 유지</span><span class="sxs-lookup"><span data-stu-id="7ea68-102">Workflow Persistence</span></span>
<span data-ttu-id="7ea68-103">워크플로 지속성은 프로세스 또는 컴퓨터 정보에 독립적인 영구 워크플로 인스턴스 상태 캡처입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="7ea68-104">이 작업은 시스템 오류가 발생한 경우에 워크플로 인스턴스에 대한 잘 알려진 복구 지점을 제공하거나, 현재 작업 중이 아닌 워크플로 인스턴스를 언로드하여 메모리를 보존하거나, 워크플로 인스턴스의 상태를 서버 팜의 한 노드에서 다른 노드로 이동하기 위해 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="7ea68-105">지속성은 프로세스의 신속성, 확장성, 오류 복구, 효율적인 메모리 관리를 가능하게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="7ea68-106">지속성 프로세스는 유지 지점을 식별하고, 저장할 데이터를 수집하며, 마지막으로 지속성 공급자에게 실제 데이터 저장소를 위임하는 과정으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="7ea68-107">워크플로에 대 한 지 속성을 사용 하려면 인스턴스 저장소와 연결 해야는 **WorkflowApplication** 또는 **WorkflowServiceHost** 에서 설명한 것 처럼 [하는 방법:에 대 한 지 속성을 사용 하도록 설정 워크플로 및 워크플로 서비스](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="7ea68-108">**WorkflowApplication** 및 **WorkflowServiceHost** 연결 된 인스턴스 저장소를 사용 하 여에 지 속성 저장소에 워크플로 인스턴스를 로드 하 고 워크플로 인스턴스를 유지를 사용 하도록 설정 하려면 지 속성 저장소에 저장 된 워크플로 인스턴스 데이터를 기반으로 하는 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="7ea68-109">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 와 함께 제공 되는 **SqlWorkflowInstanceStore** 에 유지할 수 있도록 데이터 및 메타 데이터를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 대 한 워크플로 인스턴스에 대 한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="7ea68-110">참조 [SQL 워크플로 인스턴스 저장소](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="7ea68-111">워크플로 인스턴스 관련 정보와 함께 응용 프로그램별 데이터를 저장하고 로드하려면 <xref:System.Activities.Persistence.PersistenceParticipant> 클래스를 확장하는 지속성 참석자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="7ea68-112">지속성 참석자는 지속성 프로세스에 참여하여 serialize 가능한 사용자 지정 데이터를 지속성 저장소에 저장하고, 인스턴스 저장소의 데이터를 메모리로 로드하며, 지속성 트랜잭션에서 추가 논리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="7ea68-113">자세한 내용은 참조 [지 속성 참가자](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="7ea68-114">Windows Server AppFabric은 지속성의 구성 프로세스를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7ea68-115">[Windows Server App Fabric로 지 속성 개념](http://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="7ea68-115"> [Persistence Concepts with Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="7ea68-116">암시적 유지 지점</span><span class="sxs-lookup"><span data-stu-id="7ea68-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="7ea68-117">다음 목록에는 인스턴스 저장소가 워크플로에 연결되어 있을 때 워크플로가 유지되는 조건에 대한 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="7ea68-118">경우는 **TransactionScope** 활동이 완료 된 또는 **TransactedReceiveScope** 활동을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="7ea68-119">워크플로 인스턴스가 유휴 상태가 되 고 **WorkflowIdleBehavior** 워크플로 호스트에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="7ea68-120">이 문제가 발생 예를 들어 메시징 활동을 사용 하 여 또는 **지연** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="7ea68-121">WorkflowApplication 유휴 상태가 되 고 **PersistableIdle** 응용 프로그램의 속성이로 설정 되어 **PersistableIdleAction.Persist**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="7ea68-122">워크플로 인스턴스를 유지하거나 언로드하도록 호스트 응용 프로그램에 지시할 경우</span><span class="sxs-lookup"><span data-stu-id="7ea68-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="7ea68-123">워크플로 인스턴스가 종료되거나 완료되는 경우</span><span class="sxs-lookup"><span data-stu-id="7ea68-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="7ea68-124">경우는 **Persist** 활동에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea68-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="7ea68-125">이전 버전의 Windows Workflow Foundation을 사용하여 개발된 워크플로 인스턴스에서 상호 운용 가능한 방식으로 실행되는 동안 유지 지점을 발견한 경우</span><span class="sxs-lookup"><span data-stu-id="7ea68-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ea68-126">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7ea68-126">In This Section</span></span>  
  
-   [<span data-ttu-id="7ea68-127">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="7ea68-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="7ea68-128">인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="7ea68-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="7ea68-129">지속성 참석자</span><span class="sxs-lookup"><span data-stu-id="7ea68-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="7ea68-130">지속성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7ea68-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="7ea68-131">비지속형 워크플로 인스턴스</span><span class="sxs-lookup"><span data-stu-id="7ea68-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="7ea68-132">워크플로 일시 중지 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="7ea68-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
