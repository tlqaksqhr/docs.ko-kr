---
title: "상태 시스템 워크플로 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 344caacd-bf3b-4716-bd5a-eca74fc5a61d
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 상태 시스템 워크플로
순서도는 잘 알려진 프로그램 개발용 패러다임입니다.<xref:System.Activities.Statements.State>, <xref:System.Activities.Statements.Transition> 및 기타 활동과 함께 <xref:System.Activities.Statements.StateMachine> 활동은 상태 시스템 워크플로 프로그램을 빌드하는 데 사용할 수 있습니다.이 항목에서는 상태 시스템 워크플로를 만드는 방법에 대해 간략하게 설명합니다.  
  
## 상태 시스템 워크플로 서비스 개요  
 상태 시스템 워크플로는 이벤트 구동 방식으로 워크플로를 모델링할 수 있는 모델링 스타일을 제공합니다.<xref:System.Activities.Statements.StateMachine> 활동에는 상태 시스템의 논리를 구성하는 상태 및 전환이 포함되어 있으므로 활동을 사용할 수 있는 모든 위치에서 사용할 수 있습니다.상태 시스템 런타임에는 다음과 같은 클래스가 있습니다.  
  
-   <xref:System.Activities.Statements.StateMachine>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
 상태 시스템 워크플로를 만들기 위해 상태가 <xref:System.Activities.Statements.StateMachine> 활동에 추가되고 상태 간 흐름을 제어하기 위해 전환이 사용됩니다.[초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)의 단계 [방법: 상태 시스템 워크플로 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md)에서의 다음 스크린 샷은 세 가지 상태 및 세 가지 전환을 사용하는 상태 시스템 워크플로를 보여 줍니다.**Initialize Target**은 초기 상태로 워크플로에서 첫 번째 상태를 나타냅니다.이 상태는 **시작** 노드에서 해당 상태로 이끄는 선으로 지정됩니다.워크플로의 최종 상태는 **FinalState**라고 하며 워크플로가 완료되는 지점을 나타냅니다.  
  
 ![완료된 상태 시스템 워크플로](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 상태 시스템 워크플로에는 하나의 초기 상태만 있어야 하며 하나 이상의 최종 상태가 있어야 합니다.최종 상태가 아닌 각 상태에는 적어도 하나 이상의 전환이 있어야 합니다.다음 단원에는 상태 및 전환을 만들고 구성하는 방법에 대해 설명합니다.  
  
## 상태 만들기 및 구성  
 <xref:System.Activities.Statements.State>는 상태 시스템이 처할 수 있는 상태를 나타냅니다.<xref:System.Activities.Statements.State>를 워크플로에 추가하려면 **도구 상자**의 **시스템 상태** 섹션에서 **State** 활동 디자이너를 끌어 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 화면의 <xref:System.Activities.Statements.StateMachine> 활동에 놓습니다.  
  
 ![WF4 정적 컴퓨터 활동](../../../docs/framework/windows-workflow-foundation//media/netframework4platformupdate1statemachineactivities.jpg "NETFramework4PlatformUpdate1StateMachineActivities")  
  
 상태를 **초기 상태**로 구성하려면 상태를 마우스 오른쪽 단추로 클릭하고 **초기 상태로 설정**을 선택합니다.또한 현재 초기 상태가 없을 경우 워크플로의 맨 위에 있는 **시작** 노드에서 원하는 상태로 선을 끌어 지정할 수 있습니다.<xref:System.Activities.Statements.StateMachine> 활동을 Workflow Designer에 놓으면 **State1**이라는 초기 상태로 사전 구성됩니다.상태 시스템 워크플로에는 하나의 초기 상태만 있어야 합니다.  
  
 상태 시스템에서 종료 상태를 나타내는 상태를 최종 상태라고 합니다.최종 상태는 <xref:System.Activities.Statements.State.IsFinal%2A> 속성이 `true`로 설정되어 있고, <xref:System.Activities.Statements.State.Exit%2A> 활동이 없으며, 활동에서 발생되는 전환이 없는 상태입니다.워크플로에 최종 상태를 추가하려면 **도구 상자**의 **상태 시스템** 섹션에서 **FinalState** 활동 디자이너를 끌어 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 화면의 <xref:System.Activities.Statements.StateMachine> 활동에 놓습니다.상태 시스템 워크플로에는 하나 이상의 최종 상태가 있어야 합니다.  
  
### Entry 및 Exit 작업 구성  
 상태에는 <xref:System.Activities.Statements.State.Entry%2A> 및 <xref:System.Activities.Statements.State.Exit%2A> 작업을 사용할 수 있습니다.최종 상태로 구성된 상태에는 진입 작업만 있어야 합니다.워크플로 인스턴스가 특정 상태에 들어가면 진입 작업의 모든 활동이 실행됩니다.진입 작업이 완료되면 상태의 전환에 대한 트리거가 예정됩니다.다른 상태로의 전환이 확정되면 상태가 동일한 상태로 다시 전환되어도 종료 작업의 활동이 실행됩니다.종료 작업이 완료된 후 전환 작업의 활동이 실행된 후 새로운 상태가 전환되고, 해당 진입 작업이 예정됩니다.  
  
> [!NOTE]
>  상태 시스템 워크플로를 디버깅하면 중단점을 루트 상태 시스템 활동 및 상태 시스템 워크플로 내의 상태에 배치할 수 있습니다.중단점은 전환에 직접 배치할 수는 없지만 상태 및 전환 내에 포함된 모든 활동에 배치할 수 있습니다.  
  
## 전환 만들기 및 구성  
 전환이 없을지도 모르는 최종 상태를 제외하고 모든 상태에는 하나 이상의 전환이 있어야 합니다.상태를 상태 시스템 워크플로에 추가한 후에 전환이 추가되거나 상태를 놓을 때 전환이 만들어질 수 있습니다.  
  
 한번에 <xref:System.Activities.Statements.State>를 추가하고 전환을 만들려면 **도구 상자**의 **상태 시스템** 섹션에서 **State** 활동을 끌어 Workflow Designer의 다른 상태 위로 가져갑니다.끌어 온 <xref:System.Activities.Statements.State>를 다른 <xref:System.Activities.Statements.State> 위로 가져가면 <xref:System.Activities.Statements.State> 주위에 삼각형 4개가 표시됩니다.<xref:System.Activities.Statements.State>를 삼각형 4개 중 하나에 놓으면 상태 시스템에 추가되고, 소스 <xref:System.Activities.Statements.State>에서 놓은 대상 <xref:System.Activities.Statements.State>로의 전환이 만들어집니다. 자세한 내용은 [전환 활동 디자이너](../Topic/Transition%20Activity%20Designer.md)를 참조하십시오.  
  
 상태를 추가한 후에 전환을 만들려면 다음과 같은 두 가지 옵션이 있습니다.첫 번째 옵션은 Workflow Designer 화면에서 상태를 끌어 기존 상태 위로 가져간 다음 놓기 지점 중 하나에 놓는 것입니다.이 옵션은 이전 단원에서 설명한 메서드와 매우 비슷합니다.마우스를 원하는 소스 상태 위로 가져가 원하는 대상 상태로 선을 끌 수도 있습니다.  
  
> [!NOTE]
>  상태 시스템에서 하나의 상태는 Workflow Designer를 사용하여 만들어지는 전환을 76개까지 사용할 수 있습니다.디자이너 밖에서 만들어지는 워크플로 상태의 전환에 대한 제한은 시스템 리소스로만 제한됩니다.  
  
 전환에는 <xref:System.Activities.Statements.Transition.Trigger%2A>, <xref:System.Activities.Statements.Transition.Condition%2A> 및 <xref:System.Activities.Statements.Transition.Action%2A>이 포함될 수 있습니다.전환의 소스 상태의 <xref:System.Activities.Statements.State.Entry%2A> 작업이 완료되면 전환의 <xref:System.Activities.Statements.Transition.Trigger%2A>가 예정됩니다.일반적으로 <xref:System.Activities.Statements.Transition.Trigger%2A>는 다른 형식의 이벤트가 발생할 때까지 대기하는 활동이지만, 어떤 활동이 될 수도 있고, 아무 활동도 아닐 수도 있습니다.<xref:System.Activities.Statements.Transition.Trigger%2A> 활동이 완료되면 <xref:System.Activities.Statements.Transition.Condition%2A>이 있을 경우 확인합니다.<xref:System.Activities.Statements.Transition.Trigger%2A> 활동이 없을 경우 <xref:System.Activities.Statements.Transition.Condition%2A>을 바로 확인합니다.조건이 `false`로 확인되면 전환이 취소되고, 해당 상태로부터의 모든 전환에 대해<xref:System.Activities.Statements.Transition.Trigger%2A> 활동이 다시 예정됩니다.현재 전환과 동일한 소스 상태를 공유하는 다른 전환이 있을 경우 해당 <xref:System.Activities.Statements.Transition.Trigger%2A> 작업이 취소되고 다시 예정됩니다.<xref:System.Activities.Statements.Transition.Condition%2A>이 `true`로 확인되거나 조건이 없을 경우 소스 상태의 <xref:System.Activities.Statements.State.Exit%2A> 작업이 실행된 다음 전환의 <xref:System.Activities.Statements.Transition.Action%2A>이 실행됩니다.<xref:System.Activities.Statements.Transition.Action%2A>이 완료되면 제어는 **대상** 상태로 넘어갑니다.  
  
 공용 트리거를 공유하는 전환을 공유 트리거 전환이라고 합니다.공유 트리거 전환 그룹의 각 전환에는 동일한 트리거를 사용하지만 고유한 <xref:System.Activities.Statements.Transition.Condition%2A> 및 Action을 사용합니다.전환에 추가 작업을 추가하고 공유 전환을 만들려면 원하는 전환의 시작을 나타내는 원을 클릭하고 원하는 상태로 끕니다.새 전환은 초기 전환과 동일한 트리거를 공유하지만 고유한 조건과 작업을 사용합니다.공유 전환은 전환 디자이너의 아래쪽에서 **공유 트리거 전환 추가**를 클릭한 다음 **연결할 사용 가능한 상태** 드롭다운에서 원하는 대상 상태를 선택하여 전환 디자이너에서도 만들 수 있습니다.  
  
> [!NOTE]
>  전환의 <xref:System.Activities.Statements.Transition.Condition%2A>가 `False`가 되거나 모든 공유 트리거 전환 조건이 `False`가 되는 경우, 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예정됩니다.  
  
 상태 시스템 워크플로에 대한 자세한 내용은 [방법: 상태 시스템 워크플로 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md), [StateMachine 활동 디자이너](../Topic/StateMachine%20Activity%20Designer.md), [상태 활동 디자이너](../Topic/State%20Activity%20Designer.md), [FinalState 활동 디자이너](../Topic/FinalState%20Activity%20Designer.md) 및 [전환 활동 디자이너](../Topic/Transition%20Activity%20Designer.md)를 참조하십시오.  
  
## 상태 시스템 용어  
 이 단원에서는 이 항목의 전체에서 사용되는 상태 시스템 어휘를 정의합니다.  
  
 상태  
 상태 시스템을 구성하는 기본 단위입니다.상태 시스템은 특정 시간에 한 상태로 있을 수 있습니다.  
  
 진입 작업  
 상태로 들어갈 때 실행되는 활동입니다.  
  
 종료 작업  
 상태를 나갈 때 실행되는 활동입니다.  
  
 전환  
 두 상태 사이의 리디렉션된 관계로, 특정 형식의 이벤트 발생에 대한 상태 시스템의 전체 응답을 나타냅니다.  
  
 공유 전환  
 소스 상태와 하나 이상의 전환이 있는 트리거를 공유하는 전환이지만, 고유한 조건과 작업을 사용합니다.  
  
 트리거  
 전환을 발생시키는 트리거 활동입니다.  
  
 조건  
 전환을 완료하기 위해 트리거가 발생한 후에 `true`로 확인되어야 하는 제한 조건입니다.  
  
 전환 작업  
 특정 전환을 수행할 때 실행되는 활동입니다.  
  
 조건부 전환  
 명시적 조건을 가진 전환입니다.  
  
 자체 전환  
 한 상태에서 자신으로 전환하는 전환입니다.  
  
 초기 상태  
 상태 시스템의 시작점을 나타내는 상태입니다.  
  
 최종 상태  
 상태 시스템의 완료를 나타내는 상태입니다.  
  
## 참고 항목  
 [방법: 상태 시스템 워크플로 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md)   
 [StateMachine 활동 디자이너](../Topic/StateMachine%20Activity%20Designer.md)   
 [상태 활동 디자이너](../Topic/State%20Activity%20Designer.md)   
 [FinalState 활동 디자이너](../Topic/FinalState%20Activity%20Designer.md)   
 [전환 활동 디자이너](../Topic/Transition%20Activity%20Designer.md)