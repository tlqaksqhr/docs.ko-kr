---
title: ".NET Framework 4에서 Interop 활동과 함께 .NET Framework 3.0 WF 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# .NET Framework 4에서 Interop 활동과 함께 .NET Framework 3.0 WF 활동 사용
 <xref:System.Activities.Statements.Interop> 활동은 한 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4.5) 활동을 래핑하는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] (WF 3.5) 활동을 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로. WF 3 활동은 단일 리프 활동이거나 전체 활동 트리입니다. [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동의 실행(취소 및 예외 처리 포함)과 지속성은 실행 중인 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 인스턴스의 컨텍스트 내에서 발생합니다.  
  
> [!NOTE]
>   <xref:System.Activities.Statements.Interop> 워크플로 프로젝트에 없는 경우 활동이 워크플로 디자이너 도구 상자에 나타나지 않습니다 해당 **대상 프레임 워크** 설정이로 **.NET Framework 4.5**합니다.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Interop 활동에서 WF 3 활동 사용을 위한 기준  
 내에서 성공적으로 실행 하는 WF 3 활동에 대 한는 <xref:System.Activities.Statements.Interop> 활동, 다음 기준을 충족 해야 합니다.  
  
-   WF 3 활동에서 파생 되어야 <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>합니다.  
  
-   WF 3 활동이 `public`으로 선언되어야 하며 `abstract`가 될 수 없습니다.  
  
-   WF 3 활동에 공용 기본 생성자가 있어야 합니다.  
  
-   인터페이스의 제한으로 인해 형식에 <xref:System.Activities.Statements.Interop> 활동에서 지원할 수 있는 <xref:System.Workflow.Activities.HandleExternalEventActivity> 및 <xref:System.Workflow.Activities.CallExternalMethodActivity> 를 직접 사용 되는 파생 작업을 수 워크플로 통신 작업 도구 (WCA.exe)를 사용 하 여 만든 사용할 수 없습니다. 참조 [Windows Workflow Foundation 도구](http://go.microsoft.com/fwlink/?LinkId=178889) 대 한 자세한 내용은 합니다.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Interop 활동에서 WF 3 활동 구성  
 구성 하 고 상호 운용 경계에서 WF 3 활동, 내부 및 외부로 데이터를 전달, WF 3 활동의 속성 및 메타 데이터 속성에서 노출 된 <xref:System.Activities.Statements.Interop> 활동입니다. WF 3 활동의 메타 데이터 속성 (예: <xref:System.Workflow.ComponentModel.Activity.Name%2A>)를 통해 노출 되는 <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A> 컬렉션. 이 컬렉션은 WF 3 활동의 메타데이터 속성 값을 정의하는 데 사용되는 이름-값 쌍의 컬렉션입니다. 메타 데이터 속성은 종속성 속성을 받으며 속성은 <xref:System.Workflow.ComponentModel.DependencyPropertyOptions> 플래그가 설정 되어 있습니다.  
  
 WF 3 활동의 속성을 통해 노출 되는 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 컬렉션입니다. 이름-값 쌍의 집합을 설정 하는 각 값이이 이것이 <xref:System.Activities.Argument> 개체를 한 WF 3 활동의 속성에 대 한 인수를 정의 하는 데 사용 합니다. 모든 속성으로 노출은 WF 3 활동 속성의 방향을 유추할 수 없기 때문에 <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument> 쌍입니다. 속성을 활동의 사용에 따라 제공 하려는 <xref:System.Activities.InArgument> 항목을 한 <xref:System.Activities.OutArgument> 항목 또는 둘 다. 예상된 이름과 <xref:System.Activities.InArgument> WF 3 활동에 정의 된 컬렉션의 항목은 속성의 이름입니다. 예상된 이름과 <xref:System.Activities.OutArgument> 는 컬렉션의에서 항목에는 연결 문자열 "Out" 및 속성의 이름입니다.  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Interop 활동에서 WF 3 활동 사용 제한  
 WF 3 시스템 제공 활동에서 직접 래핑될 수 없습니다는 <xref:System.Activities.Statements.Interop> 활동입니다. 일부 WF 3 활동에 대 한 예: <xref:System.Workflow.Activities.DelayActivity>, 에서는 유사한 WF 4.5 활동이 있기 때문에 이것이 합니다. 다른 활동에서는 활동 기능이 지원되지 않기 때문입니다. 많은 WF 3 시스템 제공 활동에 의해 래핑된 워크플로 내에서 사용할 수는 <xref:System.Activities.Statements.Interop> 는 다음과 같은 제한이 활동:  
  
1.  <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Receive> 에 사용할 수 없는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
2.  <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity>, 및 <xref:System.Workflow.Activities.WebServiceFaultActivity> 내에서 사용할 수는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
3.  <xref:System.Workflow.Activities.InvokeWorkflowActivity> 내에서 사용할 수 있는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
4.  <xref:System.Workflow.ComponentModel.SuspendActivity> 내에서 사용할 수 있는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
5.  보정 관련 활동 내에서 사용할 수 있는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
 또한 몇 가지 할 가지 동작이 있습니다 사용과 관련 된 활동에서 WF 3 활동을 이해 하는 <xref:System.Activities.Statements.Interop> 활동:  
  
1.  WF 3 활동 내에 포함 된 프로그램 <xref:System.Activities.Statements.Interop> 활동 하면 초기화는 <xref:System.Activities.Statements.Interop> 활동이 실행 됩니다. WF 4.5에는 워크플로 인스턴스를 실행하기 전에 이를 초기화하는 단계가 없습니다.  
  
2.  WF 4.5 런타임은 트랜잭션이 시작 되는 위치에 상관 없이 트랜잭션이 시작 될 때 워크플로 인스턴스 상태를 검사 하지 않습니다 (내부 또는 외부 프로그램 <xref:System.Activities.Statements.Interop> 활동).  
  
3.  WF 3 추적 레코드가 활동에 대 한 <xref:System.Activities.Statements.Interop> WF 4.5 추적 참가자에 게 제공 됩니다 <xref:System.Activities.Tracking.InteropTrackingRecord> 개체입니다. <xref:System.Activities.Tracking.InteropTrackingRecord> 파생 <xref:System.Activities.Tracking.CustomTrackingRecord>합니다.  
  
4.  WF 3 사용자 지정 활동은 WF 3 워크플로 런타임에서와 동일한 방식으로 상호 운용 환경에서 워크플로 큐를 사용하여 데이터에 액세스할 수 있습니다. 이때 사용자 지정 활동 코드를 변경할 필요가 없습니다. 다시 시작 하 여 데이터는 WF 3 워크플로 큐에 배치 된 호스트에는 <xref:System.Activities.Bookmark>합니다. 책갈피 이름은 문자열 형식으로는 <xref:System.IComparable> 워크플로 큐의 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)