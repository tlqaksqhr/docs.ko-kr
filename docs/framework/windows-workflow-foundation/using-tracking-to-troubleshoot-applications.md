---
title: 추적을 사용하여 응용 프로그램 문제 해결
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: adc9a159b8887b0198cf19891f73fdee2a48437b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="using-tracking-to-troubleshoot-applications"></a>추적을 사용하여 응용 프로그램 문제 해결
Windows WF (Workflow Foundation)를 사용 하는 Windows Workflow Foundation 응용 프로그램 또는 서비스의 실행에 세부 정보를 제공 하는 워크플로 관련 정보를 추적할 수 있습니다. Windows Workflow Foundation 호스트는 워크플로 인스턴스를 실행 하는 동안 워크플로 이벤트를 캡처할 수 있습니다. 워크플로에서 오류나 예외가 생성, 처리 문제 해결 세부 정보를 추적 하는 Windows Workflow Foundation를 사용할 수 있습니다.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>WF 추적을 사용한 WF 문제 해결  
 Windows Workflow Foundation 활동 처리 내에서 오류를 검색 하려면 쿼리 하는 추적 프로필을 사용 하 여 추적을 설정할 수 있습니다는 <xref:System.Activities.Tracking.ActivityStateRecord> Faulted 상태와 함께 합니다. 해당 쿼리는 다음 코드로 지정됩니다.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 오류가 전파되어 오류 처리기(예: <xref:System.Activities.Statements.TryCatch> 활동) 내에서 처리되면 <xref:System.Activities.Tracking.FaultPropagationRecord>를 사용하여 오류를 검색할 수 있습니다. <xref:System.Activities.Tracking.FaultPropagationRecord>는 오류의 소스 활동과 오류 처리기의 이름을 나타냅니다. <xref:System.Activities.Tracking.FaultPropagationRecord>에는 오류에 대한 예외 스택의 형태로 오류 세부 정보가 포함됩니다. <xref:System.Activities.Tracking.FaultPropagationRecord>를 구독하기 위한 쿼리는 다음 예제에 나와 있습니다.  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 오류가 워크플로 내에서 처리되지 않으면 워크플로 인스턴스에서 처리되지 않은 예외가 발생하고 워크플로 인스턴스가 중단됩니다. 처리되지 않은 예외의 세부 정보를 이해하려면 다음 예제에 지정된 대로 추적 프로필에서 `state name="UnhandledException"`인 워크플로 인스턴스 레코드를 쿼리해야 합니다.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 워크플로 인스턴스에서 처리 되지 않은 예외가 발생할 때 한 <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> 개체는 Windows Workflow Foundation 추적이 활성화 된 경우에 내보내집니다.  
  
 이 추적 레코드에는 예외 스택의 형태로 오류 세부 정보가 포함됩니다. 오류가 발생 했으며 처리 되지 않은 예외를 발생 하는 오류 (예를 들어 활동) 원본에 대 한 세부 정보를가지고 있습니다. Windows Workflow Foundation에서 오류 이벤트를 구독할 추적 참가자를 추가 하 여 추적을 사용 합니다. 이 참가자는 `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> 및 `WorkflowInstanceQuery (state="UnhandledException")`를 쿼리하는 추적 프로필을 사용하여 구성합니다.  
  
 ETW 추적 참가자를 사용하여 추적을 활성화하면 오류 이벤트가 ETW 세션으로 내보내집니다. Event Viewer 이벤트 뷰어를 사용하여 이벤트를 볼 수 있습니다. 이 노드 아래에서 찾을 수 있습니다 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그에는 Microsoft->-> Windows 응용 프로그램 서버-응용 프로그램->** 분석 채널에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Server App Fabric 모니터링](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [App Fabric로 응용 프로그램 모니터링](http://go.microsoft.com/fwlink/?LinkId=201275)
