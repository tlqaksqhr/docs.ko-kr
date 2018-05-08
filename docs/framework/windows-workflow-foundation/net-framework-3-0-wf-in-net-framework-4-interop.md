---
title: .NET Framework 4에서 Interop 활동과 함께 .NET Framework 3.0 WF 활동 사용
ms.date: 03/30/2017
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
ms.openlocfilehash: 8110c86ab8bf5c557dbf8eb361d4ead2e256a3b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>.NET Framework 4에서 Interop 활동과 함께 .NET Framework 3.0 WF 활동 사용
<xref:System.Activities.Statements.Interop> 활동은 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로에서 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)](WF 3.5) 활동을 래핑하는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)](WF 4.5) 활동입니다. WF 3 활동은 단일 리프 활동이거나 전체 활동 트리입니다. [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동의 실행(취소 및 예외 처리 포함)과 지속성은 실행 중인 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 인스턴스의 컨텍스트 내에서 발생합니다.  
  
> [!NOTE]
>  <xref:System.Activities.Statements.Interop> 워크플로 프로젝트에 없는 경우 활동은 워크플로 디자이너 도구 상자에 나타나지 않습니다 해당 **대상 프레임 워크** 으로 설정 **.NET Framework 4.5**합니다.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Interop 활동에서 WF 3 활동 사용을 위한 기준  
 WF 3 활동을 <xref:System.Activities.Statements.Interop> 활동 내에서 성공적으로 실행하려면 다음 기준을 충족해야 합니다.  
  
-   WF 3 활동이 <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType>에서 파생되어야 합니다.  
  
-   WF 3 활동이 `public`으로 선언되어야 하며 `abstract`가 될 수 없습니다.  
  
-   WF 3 활동에 공용 기본 생성자가 있어야 합니다.  
  
-   <xref:System.Activities.Statements.Interop> 작업이 지원하는 인터페이스 형식의 제한 사항 때문에 <xref:System.Workflow.Activities.HandleExternalEventActivity> 및 <xref:System.Workflow.Activities.CallExternalMethodActivity>를 직접 사용할 수는 없지만 워크플로 통신 작업 도구(WCA.exe)를 사용하여 만든 파생 작업을 사용할 수 있습니다. 참조 [Windows Workflow Foundation 도구](http://go.microsoft.com/fwlink/?LinkId=178889) 대 한 자세한 내용은 합니다.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Interop 활동에서 WF 3 활동 구성  
 상호 운용 경계에서 WF 3 활동을 구성하여 데이터를 주고 받으려면 WF 3 활동의 속성 및 메타데이터 속성을 <xref:System.Activities.Statements.Interop> 활동에서 노출해야 합니다. WF 3 활동의 메타데이터 속성(예: <xref:System.Workflow.ComponentModel.Activity.Name%2A>)은 <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A> 컬렉션을 통해 노출됩니다. 이 컬렉션은 WF 3 활동의 메타데이터 속성 값을 정의하는 데 사용되는 이름-값 쌍의 컬렉션입니다. 메타데이터 속성은 <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata> 플래그가 설정되는 종속성 속성에 의해 지원되는 속성입니다.  
  
 WF 3 활동 속성은 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 컬렉션을 통해 노출됩니다. 이 컬렉션은 이름-값 쌍의 집합이며 각 값은 WF 3 활동 속성의 인수를 정의하는 데 사용되는 <xref:System.Activities.Argument> 개체입니다. 모든 속성으로 노출은 WF 3 활동 속성의 방향을 유추할 수 없기 때문에 프로그램 <xref:System.Activities.InArgument> / <xref:System.Activities.OutArgument> 쌍입니다. 속성의 활동 용도에 따라 <xref:System.Activities.InArgument> 항목, <xref:System.Activities.OutArgument> 항목 또는 둘 모두를 제공할 수 있습니다. 컬렉션에서 <xref:System.Activities.InArgument> 항목에 필요한 이름은 WF 3 활동에 정의된 속성 이름입니다. 예상된 이름과 <xref:System.Activities.OutArgument> 는 컬렉션의에서 항목에는 연결 속성 및 문자열 "Out"의 이름입니다.  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Interop 활동에서 WF 3 활동 사용 제한  
 WF 3 시스템 제공 활동은 <xref:System.Activities.Statements.Interop> 활동에서 직접 래핑될 수 없습니다. <xref:System.Workflow.Activities.DelayActivity>와 같은 일부 WF 3 활동에서는 유사한 WF 4.5 활동이 있기 때문이고, 다른 활동에서는 활동 기능이 지원되지 않기 때문입니다. 많은 WF 3 시스템 제공 활동은 <xref:System.Activities.Statements.Interop> 활동에 의해 래핑되는 워크플로 내에서 사용될 수 있지만, 다음과 같은 제한 사항이 적용됩니다.  
  
1.  <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Receive>는 <xref:System.Activities.Statements.Interop> 활동에서 사용할 수 없습니다.  
  
2.  <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity> 및 <xref:System.Workflow.Activities.WebServiceFaultActivity>는 <xref:System.Activities.Statements.Interop> 활동에서 사용할 수 없습니다.  
  
3.  <xref:System.Workflow.Activities.InvokeWorkflowActivity>는 <xref:System.Activities.Statements.Interop> 활동에서 사용할 수 없습니다.  
  
4.  <xref:System.Workflow.ComponentModel.SuspendActivity>는 <xref:System.Activities.Statements.Interop> 활동에서 사용할 수 없습니다.  
  
5.  보정 관련 활동은 <xref:System.Activities.Statements.Interop> 활동에서 사용할 수 없습니다.  
  
 <xref:System.Activities.Statements.Interop> 활동에서 WF 3 활동을 사용하는 것과 관련하여 이해해야 할 몇 가지 동작이 있습니다.  
  
1.  <xref:System.Activities.Statements.Interop> 활동에 포함된 WF 3 활동은 <xref:System.Activities.Statements.Interop> 활동을 실행하면 초기화됩니다. WF 4.5에는 워크플로 인스턴스를 실행하기 전에 이를 초기화하는 단계가 없습니다.  
  
2.  WF 4.5 런타임은 트랜잭션이 시작되는 위치(<xref:System.Activities.Statements.Interop> 활동 내부 또는 외부)에 상관없이 트랜잭션이 시작될 때 워크플로 인스턴스 상태를 검사하지 않습니다.  
  
3.  <xref:System.Activities.Statements.Interop> 활동 내의 활동에 대한 WF 3 추적 레코드가 WF 4.5 추적 참가자에게 <xref:System.Activities.Tracking.InteropTrackingRecord> 개체로 제공됩니다. <xref:System.Activities.Tracking.InteropTrackingRecord>는 <xref:System.Activities.Tracking.CustomTrackingRecord>의 파생 항목입니다.  
  
4.  WF 3 사용자 지정 활동은 WF 3 워크플로 런타임에서와 동일한 방식으로 상호 운용 환경에서 워크플로 큐를 사용하여 데이터에 액세스할 수 있습니다. 이때 사용자 지정 활동 코드를 변경할 필요가 없습니다. 호스트에서 데이터는 <xref:System.Activities.Bookmark>를 다시 시작하여 WF 3 워크플로 큐에 배치됩니다. 책갈피 이름은 <xref:System.IComparable> 워크플로 큐 이름의 문자열 형식입니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 4.5 워크플로에서 .NET Framework 3.0 또는 .NET Framework 3.5 작업 사용](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)
