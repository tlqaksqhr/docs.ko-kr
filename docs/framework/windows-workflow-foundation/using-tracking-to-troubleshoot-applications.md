---
title: 추적을 사용하여 응용 프로그램 문제 해결
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: ee9aaaae80f213f026a222ac1754ae8b4fdf2d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517045"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="1c136-102">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1c136-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="1c136-103">Windows WF (Workflow Foundation)를 사용 하는 Windows Workflow Foundation 응용 프로그램 또는 서비스의 실행에 세부 정보를 제공 하는 워크플로 관련 정보를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="1c136-104">Windows Workflow Foundation 호스트는 워크플로 인스턴스를 실행 하는 동안 워크플로 이벤트를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="1c136-105">워크플로에서 오류나 예외가 생성, 처리 문제 해결 세부 정보를 추적 하는 Windows Workflow Foundation를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="1c136-106">WF 추적을 사용한 WF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1c136-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="1c136-107">Windows Workflow Foundation 활동 처리 내에서 오류를 검색 하려면 쿼리 하는 추적 프로필을 사용 하 여 추적을 설정할 수 있습니다는 <xref:System.Activities.Tracking.ActivityStateRecord> Faulted 상태와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="1c136-108">해당 쿼리는 다음 코드로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="1c136-109">오류가 전파되어 오류 처리기(예: <xref:System.Activities.Statements.TryCatch> 활동) 내에서 처리되면 <xref:System.Activities.Tracking.FaultPropagationRecord>를 사용하여 오류를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="1c136-110"><xref:System.Activities.Tracking.FaultPropagationRecord>는 오류의 소스 활동과 오류 처리기의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="1c136-111"><xref:System.Activities.Tracking.FaultPropagationRecord>에는 오류에 대한 예외 스택의 형태로 오류 세부 정보가 포함됩니다. <xref:System.Activities.Tracking.FaultPropagationRecord>를 구독하기 위한 쿼리는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="1c136-112">오류가 워크플로 내에서 처리되지 않으면 워크플로 인스턴스에서 처리되지 않은 예외가 발생하고 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="1c136-113">처리되지 않은 예외의 세부 정보를 이해하려면 다음 예제에 지정된 대로 추적 프로필에서 `state name="UnhandledException"`인 워크플로 인스턴스 레코드를 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="1c136-114">워크플로 인스턴스에서 처리 되지 않은 예외가 발생할 때 한 <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> 개체는 Windows Workflow Foundation 추적이 활성화 된 경우에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="1c136-115">이 추적 레코드에는 예외 스택의 형태로 오류 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="1c136-116">오류가 발생 했으며 처리 되지 않은 예외를 발생 하는 오류 (예를 들어 활동) 원본에 대 한 세부 정보를가지고 있습니다. Windows Workflow Foundation에서 오류 이벤트를 구독할 추적 참가자를 추가 하 여 추적을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="1c136-117">이 참가자는 `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> 및 `WorkflowInstanceQuery (state="UnhandledException")`를 쿼리하는 추적 프로필을 사용하여 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="1c136-118">ETW 추적 참가자를 사용하여 추적을 활성화하면 오류 이벤트가 ETW 세션으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="1c136-119">Event Viewer 이벤트 뷰어를 사용하여 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="1c136-120">이 노드 아래에서 찾을 수 있습니다 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그에는 Microsoft->-> Windows 응용 프로그램 서버-응용 프로그램->** 분석 채널에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c136-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c136-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c136-121">See Also</span></span>  
 [<span data-ttu-id="1c136-122">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="1c136-122">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="1c136-123">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="1c136-123">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
