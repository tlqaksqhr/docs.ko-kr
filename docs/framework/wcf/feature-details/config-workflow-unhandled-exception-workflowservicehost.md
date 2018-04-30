---
title: '방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="e6067-102">방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성</span><span class="sxs-lookup"><span data-stu-id="e6067-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="e6067-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되는 워크플로 내에서 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정할 수 있도록 하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="e6067-104">이 항목에서는 구성 파일에서 이 동작을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="e6067-105">WorkflowUnhandledExceptionBehavior를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="e6067-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="e6067-106">추가 <`workflowUnhandledException`> 요소에는 <`behavior`> 내에서 요소는 <`serviceBehaviors`> 요소를 사용 하 여는 `action` 특성 예제에 나와 있는 것 처럼 처리 되지 않은 예외가 발생할 때 수행할 동작을 지정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e6067-107">위의 샘플에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="e6067-108">자세한 내용은 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="e6067-109">이 동작은 다음 예제와 같이 코드에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="e6067-110">`action` 특성에는 <`workflowUnhandledException`> 요소는 다음 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="e6067-111">**중단**</span><span class="sxs-lookup"><span data-stu-id="e6067-111">**abandon**</span></span>  
     <span data-ttu-id="e6067-112">유지되는 인스턴스 상태를 변경하지 않고 메모리에서 인스턴스를 중단합니다. 즉, 마지막 유지 지점으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="e6067-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="e6067-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="e6067-114">메모리에서 인스턴스를 중단하고 유지되는 인스턴스가 일시 중단되도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="e6067-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="e6067-115">**cancel**</span></span>  
     <span data-ttu-id="e6067-116">인스턴스에 대한 취소 처리기를 호출하고 메모리에서 인스턴스를 완료합니다. 이 경우 인스턴스가 인스턴스 저장소에서 제거될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="e6067-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="e6067-117">**terminate**</span></span>  
     <span data-ttu-id="e6067-118">메모리에서 인스턴스를 완료하고 인스턴스 저장소에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="e6067-119">에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, 참조 [워크플로 서비스 호스트 확장명](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6067-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6067-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6067-120">See Also</span></span>  
 [<span data-ttu-id="e6067-121">워크플로 서비스 호스트 확장성</span><span class="sxs-lookup"><span data-stu-id="e6067-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="e6067-122">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="e6067-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
