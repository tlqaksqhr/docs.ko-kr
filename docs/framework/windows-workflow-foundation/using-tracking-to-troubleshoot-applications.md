---
title: "추적을 사용하여 응용 프로그램 문제 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bb8971c344ff24120b5f85dceb518b0944bd5feb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="3ea11-102">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3ea11-102">Using Tracking to Troubleshoot Applications</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="3ea11-103">을 사용하면 워크플로 관련 정보를 추적하여 [!INCLUDE[wf2](../../../includes/wf2-md.md)] 응용 프로그램 또는 서비스의 실행에 대한 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-103"> enables you to track workflow-related information to give details into the execution of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] application or service.</span></span> [!INCLUDE[wf2](../../../includes/wf2-md.md)]<span data-ttu-id="3ea11-104"> 호스트는 워크플로 인스턴스 실행 중에 워크플로 이벤트를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-104"> hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="3ea11-105">워크플로에서 오류나 예외가 생성되면 [!INCLUDE[wf2](../../../includes/wf2-md.md)] 추적 세부 정보를 사용하여 처리 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-105">If your workflow generates faults or exceptions, you can use the [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="3ea11-106">WF 추적을 사용한 WF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3ea11-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="3ea11-107">[!INCLUDE[wf2](../../../includes/wf2-md.md)] 활동 처리 내에서 오류를 검색하려면 Faulted 상태의 <xref:System.Activities.Tracking.ActivityStateRecord>를 쿼리하는 추적 프로필을 사용하여 추적을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-107">To detect faults within the processing of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="3ea11-108">해당 쿼리는 다음 코드로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="3ea11-109">오류가 전파되어 오류 처리기(예: <xref:System.Activities.Statements.TryCatch> 활동) 내에서 처리되면 <xref:System.Activities.Tracking.FaultPropagationRecord>를 사용하여 오류를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="3ea11-110"><xref:System.Activities.Tracking.FaultPropagationRecord>는 오류의 소스 활동과 오류 처리기의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="3ea11-111"><xref:System.Activities.Tracking.FaultPropagationRecord>에는 오류에 대한 예외 스택의 형태로 오류 세부 정보가 포함됩니다. <xref:System.Activities.Tracking.FaultPropagationRecord>를 구독하기 위한 쿼리는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="3ea11-112">오류가 워크플로 내에서 처리되지 않으면 워크플로 인스턴스에서 처리되지 않은 예외가 발생하고 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="3ea11-113">처리되지 않은 예외의 세부 정보를 이해하려면 다음 예제에 지정된 대로 추적 프로필에서 `state name="UnhandledException"`인 워크플로 인스턴스 레코드를 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="3ea11-114"><xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> 추적이 활성화된 경우 워크플로 인스턴스에서 처리되지 않은 예외가 발생하면 [!INCLUDE[wf2](../../../includes/wf2-md.md)] 개체가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking has been enabled.</span></span>  
  
 <span data-ttu-id="3ea11-115">이 추적 레코드에는 예외 스택의 형태로 오류 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="3ea11-116">이 레코드에는 오류가 발생하고 그 결과로 처리되지 않은 예외가 발생하게 된 오류 소스(예, 활동)에 대한 세부 정보가 포함됩니다. [!INCLUDE[wf2](../../../includes/wf2-md.md)]에서 오류 이벤트를 구독하려면 추적 참가자를 추가하여 추적을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a [!INCLUDE[wf2](../../../includes/wf2-md.md)], enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="3ea11-117">이 참가자는 `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> 및 `WorkflowInstanceQuery (state="UnhandledException")`를 쿼리하는 추적 프로필을 사용하여 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="3ea11-118">ETW 추적 참가자를 사용하여 추적을 활성화하면 오류 이벤트가 ETW 세션으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="3ea11-119">Event Viewer 이벤트 뷰어를 사용하여 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="3ea11-120">이 노드 아래에서 찾을 수 있습니다 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그에는 Microsoft->-> Windows 응용 프로그램 서버-응용 프로그램->** 분석 채널에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ea11-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea11-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ea11-121">See Also</span></span>  
 [<span data-ttu-id="3ea11-122">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="3ea11-122">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="3ea11-123">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="3ea11-123">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
